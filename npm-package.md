## packages will be used in react
* **React**: 包含react实现核心代码，包括数据流up-down，虚拟dom的实现（render方法是操作虚拟dom而非显示在页面的dom结构）
      
* **React-dom**: 与react一起导入，reader方法是将react的虚拟dom渲染至页面上:   
`reader（<componentA>, document.getElementById('app-root')）`
* **react-router**: 主要是`<Router>`标签：
    + `<Router>`:有3个methods分别是：`<Router component>`  `<Router reader>`  `<Router children>`既选择符合path时加载的内容，多用component形式
    +  `Props`：所有的 render method 无一例外都将被传入 match,history,location
* **react-router-dom**: 在v4.0后从react-router中抽离出来,包含了React-Router的api并且有自己特有的api（`<Link>`,`<BrowswerRouter>`）等
[了解详情](https://blog.csdn.net/sinat_17775997/article/details/69218382)
* **react-redux**:
* **react-router-redux**: React Router 和 Redux 的集成
