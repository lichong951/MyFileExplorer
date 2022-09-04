## 开发环境配置
**VScode + nw + nwjs-builder-phoenix**

开发 & 打包整体配置如下：

```
{
  "name": "myfile-explorer",
  "version": "1.0.0",
  "description": "",
  "main": "index.html",
  "window": {
    "toolbar": false,
    "show": true,
    "width": 1000,
    "height": 600,
	  "min_width": 800,
   	 "min_height": 500
  },
  "scripts": {
    "start": "nw .",
    "dist": "build --tasks mac-x64 --mirror https://npm.taobao.org/mirrors/nwjs/ ."
  },
  "author": "",
  "license": "ISC",
  "build": {
    "nwVersion": "0.41.2"
  },
  "devDependencies": {
    "nw": "^0.67.1",
    "nwjs-builder-phoenix": "^1.15.0"
  }
}

```
### 开发运行
先安装
`npm i`

主要是下载安装

```
"devDependencies": {
    "nw": "^0.67.1",
    "nwjs-builder-phoenix": "^1.15.0"
  }
  
```
运行：`npm run start`

## 打包设置
打包命令：`npm run dist`
win（x86 & x64）、Linux（x86 & x64）、Mac（x64）平台打包配置如下：

```

"dist": "build --tasks win-x86,win-x64,linux-x86,linux-x64,mac-x64 --mirror https://dl.nwjs.io/ .",

```

本工程是在macOS下进行开发因此打包配置如下：
`build --tasks mac-x64 --mirror https://npm.taobao.org/mirrors/nwjs/ `

打包过程如下：

```
localhost:MyFileExplorer lichong$ npm run dist
Debugger attached.

> myfile-explorer@1.0.0 dist
> build --tasks mac-x64 --mirror https://npm.taobao.org/mirrors/nwjs/ .

Debugger attached.
Starting building tasks... { tasks: [ [ 'mac', 'x64' ] ], concurrent: false }
Building for mac, x64 starts...
Fetching NW.js binary... { platform: 'mac', arch: 'x64', version: '0.41.2', flavor: 'normal' }
Building targets...
Building directory target starts...
Building directory target ends within 12.92s.
Building for mac, x64 ends within 13.99s.
Waiting for the debugger to disconnect...
Waiting for the debugger to disconnect...
localhost:MyFileExplorer lichong$ 
```

打包好的文件存放在dist目录下面 运行安装包为“dist/myfile-explorer-1.0.0-mac-x64/myfile-explorer.app”


  