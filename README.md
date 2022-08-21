# 前言

该项目用于学习 TypeScript

## 安装

```bash
# 全局安装
yarn global add typescript

# 项目安装
yarn add typescript
```

## 命令行编译

demo01
```typescript
let hello:string = 'Hello World'
```

编译 ts 文件
```bash
tsc src/demo01/index.ts
```

## configure
生成 TypeScript 配置文件
```bash
tsc --init
```

### 注意
如果使用 tsc 命令编译代码时使用命令行编译，则不调 tsconfig.json 配置。如:
```bash
tsc src/demo01/index.ts
```

### compilerOptions

> type: Object

编译选项配置

#### target
> type: string

编译目标代码指定 ES 标准

`es3` `es5` `es6` `es2015` `es2016` `es2017` `es2018` `esnext` 

#### module
> type: string

编译目标使用模块化标准

`amd` `commonjs` `es2015` `es6` `esnext` `none` `system` `umd`
常用标准
`commonjs`  node
`es6`       `es6`

#### lib
> type: Array

编译目标环境

`DOM` `ES2015` `ES2016` ....

> 常用环境

1. `DOM`     浏览器环境
2. `ES2015`  ES 标准
3. node 环境需要安装 `@types/node`
```bash
yarn add @types/node -D
```

#### outDir
> type: string

编译出口文件夹

#### outFile
> type: string

编译出口文件


### include
> type: Array

编译人口文件夹

### files
> type: Array

编译人口文件

## 简化开发流程

### ts-node
将 ts 代码在内存中完成编译，同时运行，并且不生成代码。

> 安装
```bash
yarn add ts-node -D
```
> 注意
使用 ts-node 编译时使用命令行编译，同时也调用 tsconfig.json 配置。
```bash
ts-node src/demo01/index.js
```

### nodemon
监测文件变化后，执行命令。

> 安装
```bash
yarn add nodemon -D
```

### 设置项目脚本命令
添加到 package.json
```json
"scripts": {
    // nodemon --watch : 只监控当前文件夹下的文件
    // nodemon -e : 监控文件扩展名
    // nodemon --exec : 当前项目文件发生改变执行后面命令
    // ts-node ssrc/demo01/index.ts : 执行当前命令可以在内存中编译同时运行 ts 代码，并且不生成编译后代码。
    "dev": "nodemon --watch src -e ts --exec ts-node src/demo01/index.ts",
    // 编译当前项目代码。
    "build": "tsc"
  },
```

## 运行

```bash
# 克隆当前仓库
git clone https://github.com/xhconceit/ts.git

# 安装依赖
yarn

# 开发模式下运行项目
yarn dev

# 打包项目
yarn build

```