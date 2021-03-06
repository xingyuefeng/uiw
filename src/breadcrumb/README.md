Breadcrumb 面包屑
===

显示当前页面的路径，快速返回之前的任意页面。

```jsx
import { Breadcrumb } from 'uiw';
```

### 基础用法

适用广泛的基础用法，在 `Breadcrumb` 中使用 `Breadcrumb.Item` 标签表示从首页开始的每一级。

<!--DemoStart,bgWhite,codePen--> 
```js
import { Breadcrumb } from 'uiw';

ReactDOM.render(
  <Breadcrumb>
    <Breadcrumb.Item>首页</Breadcrumb.Item>
    <Breadcrumb.Item separator=">">活动管理</Breadcrumb.Item>
    <Breadcrumb.Item>活动列表</Breadcrumb.Item>
    <Breadcrumb.Item active>活动详情</Breadcrumb.Item>
  </Breadcrumb>,
  _mount_
);
```
<!--End-->

### 自定义分隔符

使用 `separator=">"` 可以自定义分隔符，分隔符也可以是图标。

<!--DemoStart,bgWhite,codePen--> 
```js
import { Breadcrumb } from 'uiw';

ReactDOM.render(
  <div>
    <Breadcrumb>
      <Breadcrumb.Item><a href="#">Home</a></Breadcrumb.Item>
      <Breadcrumb.Item separator=">"><a href="#">Library</a></Breadcrumb.Item>
      <Breadcrumb.Item active>Data</Breadcrumb.Item>
    </Breadcrumb>
    <Divider />
    <Breadcrumb separator="#">
      <Breadcrumb.Item><a href="#">Home</a></Breadcrumb.Item>
      <Breadcrumb.Item separator={<span>+</span>}><a href="#">Home</a></Breadcrumb.Item>
      <Breadcrumb.Item separator={<Icon type="home" verticalAlign="baseline" />}><a href="#">Icon</a></Breadcrumb.Item>
      <Breadcrumb.Item separator=">"><a href="#">Library</a></Breadcrumb.Item>
      <Breadcrumb.Item active>Data</Breadcrumb.Item>
    </Breadcrumb>
  </div>,
  _mount_
);
```
<!--End-->

### 带有图标和连接的

图标放在文字前面。注意文字要使用 `span` 包裹起来，图标 `<Icon />` 需要跟 `span` 同级。`Breadcrumb.Item` 定义 `href` 参数的话，`Item` 上的参数就全部是超链原始属性。

<!--DemoStart,bgWhite,codePen--> 
```js
import { Breadcrumb } from 'uiw';

const stylIcon = { marginRight: 3, top: 2, display: 'inline-flex' }

ReactDOM.render(
  <div>
    <Breadcrumb>
      <Breadcrumb.Item>
        <a href="#"><Icon style={stylIcon} type="home"/></a>
      </Breadcrumb.Item>
      <Breadcrumb.Item separator=">">
        <a href="#"><Icon style={stylIcon} type="apple"/>Library</a>
      </Breadcrumb.Item>
      <Breadcrumb.Item separator=">">
        <a href="#"><Icon style={stylIcon} type="pie-chart"/>Chart</a>
      </Breadcrumb.Item>
      <Breadcrumb.Item separator="">
        <a href="#"><Icon style={{...stylIcon, marginRight: 0}} type="star-on"/> Chart</a>
      </Breadcrumb.Item>
      <Breadcrumb.Item separator="" active>Data</Breadcrumb.Item>
    </Breadcrumb>
  </div>,
  _mount_
);
```
<!--End-->

## Breadcrumb

| 参数 | 说明 | 类型 | 默认值 |
|--------- |-------- |--------- |-------- |
| style | 样式 | String | - |
| className | 样式名称 | String | `w-breadcrumb` |
| separator | 分隔符自定义，定义所有子组件的分隔符。 | String | `/` |

## Breadcrumb.Item

| 参数 | 说明 | 类型 | 默认值 |
|--------- |-------- |--------- |-------- |
| className | 样式名称 | String | `w-breadcrumb-itme` |
| separator | 分隔符自定义，子组件可以单独定义不同的分隔符。 | String | - |
| active | 激活。 | String | - |

