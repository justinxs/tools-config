
# TypeScript `tsconfig.json` 配置项详解（基于最新版本）

`tsconfig.json` 是 TypeScript 项目的核心配置文件，用于告诉编译器如何处理和转换 TypeScript 代码。本文基于 **TypeScript 5.x**，详细介绍每个配置项的含义和用途。

---

## 顶层字段（Top-level Options）

### `compilerOptions`
> 编译器选项的主要配置对象，包含所有控制编译行为的参数。

### `include`
- **类型**: `string[]`
- **说明**: 指定要包含在编译中的文件或目录模式（支持 glob）。
- **示例**:
  ```json
  "include": ["src/**/*"]
  ```

### `exclude`
- **类型**: `string[]`
- **说明**: 指定从编译中排除的文件或目录。
- **默认**: `["node_modules", "bower_components", "jspm_packages"]`
- **示例**:
  ```json
  "exclude": ["dist", "node_modules"]
  ```

### `files`
- **类型**: `string[]`
- **说明**: 明确列出要编译的文件列表，仅编译这些文件。

### `extends`
- **类型**: `string`
- **说明**: 继承另一个 tsconfig 文件的配置。
- **示例**:
  ```json
  "extends": "@tsconfig/node20/tsconfig.json"
  ```

### `references`
- **类型**: `{ path: string }[]`
- **说明**: 项目引用配置，支持多项目结构。

---

## `compilerOptions` 配置详解

### 🔧 编译输出控制

| 选项 | 类型 | 说明 |
|------|------|------|
| `outDir` | `string` | 输出文件夹路径 |
| `outFile` | `string` | 将多个文件合并为一个输出（仅支持某些模块系统） |
| `rootDir` | `string` | 输入文件的根路径 |
| `removeComments` | `boolean` | 移除输出文件中的注释 |
| `noEmit` | `boolean` | 不生成输出文件 |
| `emitDeclarationOnly` | `boolean` | 只输出 `.d.ts` 类型声明文件 |

---

### 📦 模块系统相关

| 选项 | 类型 | 说明 |
|------|------|------|
| `module` | `string` | 模块系统，如 `commonjs`, `esnext`, `nodenext` |
| `moduleResolution` | `string` | 模块解析策略，如 `node`, `classic` |
| `baseUrl` | `string` | 模块导入基准路径 |
| `paths` | `object` | 模块路径别名映射 |
| `rootDirs` | `string[]` | 虚拟根目录列表 |
| `typeRoots` | `string[]` | 类型定义目录列表 |
| `types` | `string[]` | 指定要包含的类型定义包名列表 |

---

### 🧠 语言特性控制

| 选项 | 类型 | 说明 |
|------|------|------|
| `target` | `string` | 输出 JS 的版本，如 `ES2021`, `ESNext` |
| `lib` | `string[]` | 编译时包含的库，如 `DOM`, `ES2020` |
| `jsx` | `string` | JSX 支持方式：`react`, `preserve`, `react-jsx` |
| `experimentalDecorators` | `boolean` | 启用装饰器语法 |
| `emitDecoratorMetadata` | `boolean` | 输出类型元数据供装饰器使用 |

---

### ✅ 严格类型检查

| 选项 | 类型 | 说明 |
|------|------|------|
| `strict` | `boolean` | 启用所有严格类型检查 |
| `noImplicitAny` | `boolean` | 禁止隐式 any 类型 |
| `strictNullChecks` | `boolean` | 启用 null/undefined 严格检查 |
| `strictFunctionTypes` | `boolean` | 严格检查函数参数协变 |
| `strictBindCallApply` | `boolean` | 严格检查 `bind`, `call`, `apply` |
| `alwaysStrict` | `boolean` | 自动加 `'use strict'` |
| `noImplicitThis` | `boolean` | 禁止 `this` 为隐式 any |
| `useUnknownInCatchVariables` | `boolean` | `catch` 中变量类型为 `unknown` |

---

### 🧹 代码质量/错误检查

| 选项 | 类型 | 说明 |
|------|------|------|
| `noUnusedLocals` | `boolean` | 报告未使用的局部变量 |
| `noUnusedParameters` | `boolean` | 报告未使用的函数参数 |
| `noImplicitReturns` | `boolean` | 检查函数是否所有路径都有返回值 |
| `noFallthroughCasesInSwitch` | `boolean` | 检查 switch 中的 fallthrough |
| `allowUnreachableCode` | `boolean` | 允许不可达代码 |

---

### 🌐 互操作性和运行时行为

| 选项 | 类型 | 说明 |
|------|------|------|
| `allowJs` | `boolean` | 允许编译 `.js` 文件 |
| `checkJs` | `boolean` | 检查 `.js` 文件中的类型 |
| `esModuleInterop` | `boolean` | 开启 CommonJS 的兼容性默认导入 |
| `forceConsistentCasingInFileNames` | `boolean` | 文件大小写必须一致 |
| `resolveJsonModule` | `boolean` | 允许导入 `.json` 文件 |
| `isolatedModules` | `boolean` | 每个文件作为独立模块（适用于 Babel） |

---

### 🧪 实验选项（部分 5.x 新增）

| 选项 | 类型 | 说明 |
|------|------|------|
| `verbatimModuleSyntax` | `boolean` | 保留原始的导入/导出语法 |
| `moduleDetection` | `"auto" \| "legacy" \| "force"` | 文件是否视为模块的判断方式 |
| `allowImportingTsExtensions` | `boolean` | 允许带 `.ts` 后缀的导入语句 |
| `useDefineForClassFields` | `boolean` | 使用 `define` 而不是赋值初始化类字段 |

---

## 示例配置

```json
{
  "compilerOptions": {
    "target": "ES2021",
    "module": "ESNext",
    "moduleResolution": "node",
    "strict": true,
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "skipLibCheck": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src"],
  "exclude": ["node_modules", "dist"]
}
```

---

## 附加建议

- 使用 [`@tsconfig`](https://github.com/tsconfig/bases) 提供的基础配置可以简化复杂配置。
- 配置可以组合使用，如 `"extends": "@tsconfig/node-lts/tsconfig.json"`。
