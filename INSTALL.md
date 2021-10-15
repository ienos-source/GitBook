# 安装指南



## 安装 Node.js







## 安装 GitBook

```
npm install gitbook-cli -g
```

校验 gitbook 是否安装成功

```
gitbook -V
```

初始化目录（创建 SUMMARY.md 和 README.md）

```
gitbook init {directory}
```

### 遇到的问题 

在执行  `gitbook init`  出现 TypeError: cb.apply is not a function 错误，其中报错信息包含 polyfills.js 的本地路径。需要修改 js 中的代码


- 进入编辑模式

```
sudo vim {polyfill.js}
```

- 注释下面代码

```
//fs.stat = statFix(fs.stat)
//fs.fstat = statFix(fs.fstat)
//fs.lstat = statFix(fs.lstat)
```

后面再次执行 `gitbook init` 出现了另外一个错误 TypeError [ERR_INVALID_ARG_TYPE]: The "data" argument must be of type string or an instance of Buffer, TypedArray, or DataView. Received an instance of Promise

需要下载 [Node.js_v12](https://nodejs.org/dist/latest-v12.x/) 然后安装，再次执行 `gitbook init` 顺利执行

### 其他指令

- `gitbook serve`  本地预览默认端口 4000
- `gitbook build` 生成静态页面