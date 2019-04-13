#REACT

# react 生命周期
创建
componentWillMount —— 组件挂载前触发；
render —— 创建一棵由 React 元素组成的树；
componentDidMount —— 组件挂载后触发，此时页面已经存在DOM，建议在此处发起请求等操作，完成数据初始化；
更新
componentWillReceiveProps —— 组件将要接受到上级的Props，此处可以通过props修改 state 的值；
shouldComponentUpdate —— React优化的重要API，决定该组件是否应该更新，当该组件继承 PureComponent 时，shouldComponentUpdate 会对 props 与 state 做一个浅比较，来决定是否更新；
componentWillUpate —— 组件即将出发更新
render —— 创建一棵由 React 元素组成的树；
componentDidUpdate —— 组件更新完毕
卸载
componentWillUnmount —— 组件即将被销毁，在此处可以清理定时器、取消RxJS的订阅行为等，防止内存溢出。
React V16后，因为引入了 Fiber 机制，之前的部分API可能会被反复调用，所以React对生命周期的API进行了部分调整。
创建

componentWillMount static getDerivedFromProps(nextProps, state) —— 新的API是一个静态方法，返回一个对象来更新state，如果返回null则不更新任何内容
render
componentDidMount
更新

componentWillReceiveProps static getDerivedFromProps
shouldComponentUpdate
componentWillUpate
render
getSnapshotBeforeUpdate —— 在最近一次渲染输出（提交到 DOM 节点）之前调用，它使得组件能在发生更改之前从 DOM 中捕获一些信息（例如，滚动位置）。此生命周期的任何返回值将作为参数传递给 componentDidUpdate()。
componentDidUpdate
卸载
componentWillUnmount


























