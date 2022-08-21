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

### compilerOptions
type: Object
编译选项配置

#### target
type: string
编译目标代码指定 ES 标准

`es3` `es5` `es6` `es2015` `es2016` `es2017` `es2018` `esnext` 

#### module
type: string
编译目标使用模块化标准

`amd` `commonjs` `es2015` `es6` `esnext` `none` `system` `umd`
常用标准
`commonjs`  node
`es6`       `es6`

#### lib
type: Array
编译目标环境

`DOM` `ES2015` `ES2016` ....

常用环境
`DOM`     浏览器环境
`ES2015`  ES 标准

node 环境需要安装 `@types/node`
```bash
yarn add @types/node -D
```

#### outDir
type: string
编译出口文件夹

#### outFile
type: string
编译出口文件


### include
type: Array
编译人口文件夹

### files
type: Array
编译人口文件