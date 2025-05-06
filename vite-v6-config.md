
# 📘 Vite v6 配置项完整列表

> ⚠️ 本文基于 Vite 官方文档整理，适用于 Vite v6 版本。

---

## 🔧 通用配置项（Shared Options）

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `root` | `string` | `process.cwd()` | 项目根目录。 |
| `base` | `string` | `'/'` | 公共基础路径。 |
| `mode` | `string` | `'development'` | 指定环境模式。 |
| `publicDir` | `string` | `'public'` | 作为静态资源服务的文件夹。 |
| `cacheDir` | `string` | `'node_modules/.vite'` | 存储缓存文件的目录。 |
| `plugins` | `Plugin[]` | `[]` | 插件数组。 |
| `resolve` | `ResolveOptions` | `{}` | 模块解析配置。 |
| `define` | `Record<string, string>` | `{}` | 全局常量替换。 |
| `css` | `CSSOptions` | `{}` | CSS 相关配置。 |
| `json` | `JSONOptions` | `{}` | JSON 文件处理配置。 |
| `esbuild` | `ESBuildOptions` | `{}` | esbuild 转换选项。 |
| `assetsInclude` | `string | RegExp | (string | RegExp)[]` | `[]` | 指定额外的静态资源处理。 |
| `logLevel` | `'info' | 'warn' | 'error' | 'silent'` | `'info'` | 调整控制台输出的级别。 |
| `clearScreen` | `boolean` | `true` | 是否清除屏幕。 |
| `envDir` | `string` | `root` | 用于加载 `.env` 文件的目录。 |
| `envPrefix` | `string | string[]` | `'VITE_'` | 环境变量前缀。 |
| `appType` | `'spa' | 'mpa' | 'custom'` | `'spa'` | 应用类型。 |
| `customLogger` | `Logger` | `undefined` | 使用自定义 logger。 |
| `experimental` | `ExperimentalOptions` | `{}` | 实验性配置项。 |
| `future` | `FutureOptions` | `{}` | 启用未来的重大变更。 |

---

## ⚙️ 构建配置项（Build Options）

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `target` | `string | string[]` | `'modules'` | 构建的目标环境。 |
| `outDir` | `string` | `'dist'` | 输出目录。 |
| `assetsDir` | `string` | `'assets'` | 生成静态资源的存放路径。 |
| `assetsInlineLimit` | `number` | `4096` | 小于此阈值的资源将内联为 base64 编码。 |
| `cssCodeSplit` | `boolean` | `true` | 是否启用 CSS 代码拆分。 |
| `cssTarget` | `string | string[]` | `undefined` | 为 CSS 的压缩设置目标环境。 |
| `cssMinify` | `boolean` | `true` | 是否压缩 CSS。 |
| `sourcemap` | `boolean | 'inline' | 'hidden'` | `false` | 是否生成 source map 文件。 |
| `rollupOptions` | `RollupOptions` | `{}` | 自定义底层的 Rollup 打包配置。 |
| `commonjsOptions` | `CommonJSOptions` | `{}` | 传递给 `@rollup/plugin-commonjs` 的选项。 |
| `dynamicImportVarsOptions` | `DynamicImportVarsOptions` | `{}` | 传递给 `@rollup/plugin-dynamic-import-vars` 的选项。 |
| `manifest` | `boolean` | `false` | 是否生成 manifest 文件。 |
| `ssrManifest` | `boolean` | `false` | 是否生成 SSR 的 manifest 文件。 |
| `ssr` | `boolean` | `false` | 是否生成面向 SSR 的构建。 |
| `minify` | `'esbuild' | 'terser' | false` | `'esbuild'` | 使用的压缩工具。 |
| `terserOptions` | `TerserOptions` | `{}` | 传递给 Terser 的更多 minify 选项。 |
| `write` | `boolean` | `true` | 是否将构建后的文件写入磁盘。 |
| `emptyOutDir` | `boolean` | `true` | 构建时是否清空输出目录。 |
| `copyPublicDir` | `boolean` | `true` | 构建阶段是否将 `publicDir` 目录中的所有文件复制到 `outDir`。 |
| `reportCompressedSize` | `boolean` | `true` | 是否启用 gzip 压缩大小报告。 |
| `chunkSizeWarningLimit` | `number` | `500` | 触发警告的 chunk 大小（以 kB 为单位）。 |
| `watch` | `RollupWatchOptions` | `null` | 启用 Rollup 的监听器。 |
| `polyfillModulePreload` | `boolean` | `true` | 是否自动注入模块预加载 polyfill。 |
| `lib` | `LibraryOptions` | `undefined` | 库模式配置。 |
| `minifyInternalExports` | `boolean` | `true` | 是否对内部导出进行最小化。 |
| `modulePreload` | `ModulePreloadOptions` | `{}` | 模块预加载相关配置。 |
| `ssrEmitAssets` | `boolean` | `false` | 在 SSR 构建期间，是否输出静态资源。 |
| `emitAssets` | `boolean` | `true` | 在非客户端的构建过程中，是否输出静态资源。 |

---

## 🌐 开发服务器配置项（Server Options）

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `host` | `string | boolean` | `'localhost'` | 指定服务器主机名。 |
| `port` | `number` | `5173` | 指定服务器端口。 |
| `strictPort` | `boolean` | `false` | 如果指定的端口已在使用中，则退出。 |
| `https` | `boolean | HttpsOptions` | `false` | 启用 HTTPS。 |
| `open` | `boolean | string` | `false` | 是否自动打开浏览器。 |
| `proxy` | `Record<string, string | ProxyOptions>` | `{}` | 配置代理。 |
| `cors` | `boolean | CorsOptions` | `false` | 启用 CORS。 |
| `headers` | `OutgoingHttpHeaders` | `{}` | 自定义响应头。 |
| `hmr` | `boolean | HmrOptions` | `true` | 热模块替换配置。 |
| `watch` | `WatchOptions` | `{}` | 文件系统监听配置。 |
| `middlewareMode` | `boolean | 'ssr' | 'html'` | `false` | 中间件模式配置。 |
| `fs` | `FileSystemServeOptions` | `{}` | 文件系统访问控制配置。 |
| `origin` | `string` | `undefined` | 开发服务器的 origin。 |
| `preTransformRequests` | `boolean` | `false` | 是否在请求之前进行转换。 |
| `force` | `boolean` | `false` | 强制优化器忽略缓存并重新构建。 |

---

## 🔍 预览服务器配置项（Preview Options）

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `port` | `number` | `4173` | 预览服务器端口。 |
| `host` | `string | boolean` | `'localhost'` | 预览服务器主机名。 |
| `strictPort` | `boolean` | `false` | 如果指定的端口已在使用中，则退出。 |
| `https` | `boolean | HttpsOptions` | `false` | 启用 HTTPS。 |
| `open` | `boolean | string` | `false` | 是否自动打开浏览器。 |
| `proxy` | `Record<string, string | ProxyOptions>` | `{}` | 配置代理。 |
| `cors` | `boolean | CorsOptions` | `false` | 启用 CORS。 |
| `headers` | `OutgoingHttpHeaders` | `{}` | 自定义响应头。 |

---

## 📦 依赖预构建配置项（Dep Optimization Options）

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `optimizeDeps.include` | `string[]` | `[]` | 强制预构建的依赖。 |
| `optimizeDeps.exclude` | `string[]` | `[]` | 排除的依赖。 |
| `optimizeDeps.esbuildOptions` | `ESBuildOptions` | `{}` | 传递给 esbuild 的配置。 |
| `optimizeDeps.force` | `boolean` | `false` | 强制重新预构建。 |
| `optimizeDeps.disabled` | `boolean` | `false` | 禁用依赖预构建。 |

---

## 🧪 测试配置项（Vitest Options）

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `test` | `VitestOptions` | `{}` | 配置 Vitest 测试选项。 |

## 🧪 `experimental` 配置项

| 配置项 | 类型 | 说明 |
|--------|------|------|
| `environments` | `Record<string, { entry: string, env?: Record<string, string> }>` | 定义多个环境，每个环境可以指定不同的入口文件和环境变量。 |
| `renderBuiltUrl` | `(filename: string, context: { type: 'asset' | 'public' | 'script' | 'style', hostId: string, hostType: 'js' | 'css' }) => string \| { runtime: string }` | 自定义构建后资源的 URL，适用于 CDN 部署等场景。 |

### 示例配置

```ts
export default defineConfig({
  experimental: {
    environments: {
      client: {
        entry: 'src/entry-client.tsx',
        env: { SSR: 'false' }
      },
      server: {
        entry: 'src/entry-server.tsx',
        env: { SSR: 'true' }
      }
    },
    renderBuiltUrl(filename, { type }) {
      if (type === 'asset') {
        return `/cdn/assets/${filename}`;
      }
      return filename;
    }
  }
});
```

---