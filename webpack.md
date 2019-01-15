### webpack dll 对比commonchunks
* commonchunks提取公用模块，但是在每次打包时会重新打包，例如react/react-router等基本不改变的三方库会造成重复打包，影响打包时间
* webpack自带的dll模块，将静态模块剔除，通过DllReferencePlugin模块引入dll模块实现静态模块不重复打包使用的优势。   
webpack.dll.js文件配置entry：vendor: string[] | string,内容为dll的模块，outpout中path表示输出的文件路径(此处设置为./build), plugin中配置dll:   
`new webpack.DllPlugin({`  
&emsp;`path: path.resolve(__dirname, './build/manifest.json'),`  
&emsp;`name: '[name]',`  
`}),`  
其中path文件manifest.json表示dll模块及其对应的id名，在webpack.dev.js中通过dllreferenceplugin引入，实现dev和prod环境直接引用  
`new webpack.DllReferencePlugin({`   
&emsp;`manifest: require(path.resolve(__dirname, './build/manifest.json'))`  
`}),`  
manifest的路径就是dllplugin中输出的path。  
* index.html中，通过手动引入三方的manifest库即可: 
路径为dllplugin配置的outputpath+entry的chunksname：build/vendors.js  
`<script type="text/javascript" src="/build/vendors.js"></script>`

### 未完待续 。。。
