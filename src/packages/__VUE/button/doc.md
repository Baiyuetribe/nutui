# Button 按钮

### 介绍

按钮用于触发一个操作，如提交表单。

### 安装

``` javascript
import { createApp } from 'vue';
import { Button } from '@nutui/nutui';

const app = createApp();
app.use(Button);
```

## 代码演示

### 按钮类型

按钮支持 `default`、`primary`、`info`、`warning`、`danger`、`success` 六种类型，默认为 `default`。

```html
<nut-button type="primary">主要按钮</nut-button>
<nut-button type="info">信息按钮</nut-button>
<nut-button type="default">默认按钮</nut-button>
<nut-button type="danger">危险按钮</nut-button>
<nut-button type="warning">警告按钮</nut-button>
<nut-button type="success">成功按钮</nut-button>
```

### 朴素按钮

通过 `plain` 属性将按钮设置为朴素按钮，朴素按钮的文字为按钮颜色，背景为白色。

```html
<nut-button plain type="primary">朴素按钮</nut-button>
<nut-button plain type="info">朴素按钮</nut-button>
```

### 禁用状态

通过 `disabled` 属性来禁用按钮，禁用状态下按钮不可点击。

```html
<nut-button disabled type="primary">禁用状态</nut-button>
<nut-button plain disabled type="info">禁用状态</nut-button>
<nut-button plain disabled type="primary">禁用状态</nut-button>
```

### 按钮形状

通过 `shape` 属性设置按钮形状，支持圆形、方形按钮，默认为圆形。

```html
<nut-button shape="square" type="primary">方形按钮</nut-button>
<nut-button type="info">圆形按钮</nut-button>
```

### 加载状态

```html
<nut-button loading></nut-button>
<nut-button loading>加载中</nut-button>
```

### 图标按钮

```html
  <nut-button shape="square" plain type="primary" icon="star-fill"></nut-button>
  <nut-button shape="square" type="primary" icon="star">收藏</nut-button>
```

### 按钮尺寸

支持 `large`、`normal`、`small` 三种尺寸，默认为 `normal`。

```html
<nut-button size="large" type="primary">大号按钮</nut-button>
<nut-button type="primary">普通按钮</nut-button>
<nut-button size="small" type="primary">小型按钮</nut-button>
```

### 块级元素

按钮在默认情况下为行内块级元素，通过 `block` 属性可以将按钮的元素类型设置为块级元素，常用来实现通栏按钮。

```html
<nut-button block type="primary">块级元素</nut-button>
```

### 自定义颜色
通过 color 属性可以自定义按钮的颜色。
```html
<nut-button color="#7232dd">单色按钮</nut-button>
<nut-button color="#7232dd" plain>单色按钮</nut-button>
<nut-button color="linear-gradient(to right, #ff6034, #ee0a24)">
  渐变色按钮
</nut-button>
```
## API

### Props

| 参数         | 说明                             | 类型   | 默认值           |
|--------------|----------------------------------|--------|------------------|
| type         | 类型，可选值为 `primary` `info` `warning` `danger` `success` | String |`default`         |
| size        | 尺寸，可选值为 `large` `small`  | String | `normal`      |
| shape         | 形状，可选值为 `square` | String | `round`             |
| color | 按钮颜色，支持传入 linear-gradient 渐变色     | String | - |
| plain          | 	是否为朴素按钮                       | Boolean | `false`             |
| disabled          | 	是否禁用按钮                       | Boolean | `false`              |
| block          | 是否为块级元素                        | Boolean | `false`               |
| icon          | 按钮图标，同Icon组件name属性                        | String | -     |
| loading          | 按钮loading状态                        | Boolean | `false`               |

### Events

| 事件名 | 说明           | 回调参数     |
|--------|----------------|--------------|
| click  | 点击按钮时触发 | event: MouseEvent |

