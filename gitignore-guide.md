# .gitignore 文件说明与前端开发推荐配置

`.gitignore` 文件用于指定 Git 在版本控制时忽略的文件和目录，避免将不必要的本地文件提交到远程仓库中。以下是 `.gitignore` 的基本语法说明，以及前端项目中推荐的忽略规则配置。

---

## 一、基本语法说明

- `#`：注释行。
- `*.log`：忽略所有 `.log` 文件。
- `!important.log`：不过滤 `important.log` 文件（即使前面有规则匹配）。
- `/build`：仅忽略根目录下的 `build` 文件夹。
- `build/`：忽略所有 `build` 目录（不限于根目录）。
- `build`：忽略所有 `build` 目录或文件。
- `**/temp`：忽略任意目录下的 `temp` 文件夹。
- `*.ts`：忽略所有 `.ts` 结尾的文件。

---

## 二、前端开发推荐配置（React / Vue / Vite / TypeScript 通用）

```gitignore
# node modules
node_modules/

# build output
dist/
build/

# system files
.DS_Store
Thumbs.db

# log files
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*

# environment files
.env
.env.*
!.env.example

# editor directories and files
.vscode/
.idea/
*.suo
*.ntvs*
*.njsproj
*.sln

# local coverage reports
coverage/

# cache files
.cache/
.next/
out/
.husky/_/
turbo/

# TypeScript
*.tsbuildinfo

# lint cache
.eslintcache

# test coverage
nyc_output/

# Optional: ignore generated lock files if using specific package manager
# yarn.lock
# package-lock.json
# pnpm-lock.yaml
```

---

## 三、根据开发工具适配补充

### 1. 使用 Vite 的项目：
```gitignore
.vite
```

### 2. 使用 React Native 的项目：
```gitignore
android/
ios/
*.keystore
```

### 3. 使用 Storybook 的项目：
```gitignore
storybook-static/
```

---

## 四、建议

- 永远不要忽略关键的配置文件（例如 `tsconfig.json`、`package.json`、`.prettierrc` 等）。
- 使用 `.env.example` 提供环境变量的模版，但忽略真实 `.env` 文件。
- 避免将 IDE 的配置文件（如 `.idea/`、`.vscode/`）加入仓库。

以上 `.gitignore` 配置可根据具体项目类型进行定制，确保提交的内容最小且干净。建议团队共享 `.gitignore` 标准以统一开发环境管理。