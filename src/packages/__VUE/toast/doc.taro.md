# Toast 吐司

轻提示。

### 介绍

用于轻提示。

### 安装

``` javascript
import { createApp } from 'vue';
import { Toast } from '@nutui/nutui';

const app = createApp();
app.use(Toast);
```

## 代码示例

``` html
<nut-toast :msg="page.state.msg" v-model:visible="page.state.show" :type="page.state.type" @closed="page.methods.onClosed" :cover="page.state.cover" />
<nut-cell title="Text 文字提示" is-link @click="page.methods.openToast('text','网络失败，请稍后再试~')"></nut-cell>
<nut-cell title="Success 成功提示" is-link @click="page.methods.openToast('success','成功提示')"></nut-cell>
<nut-cell title="Error 失败提示" is-link @click="page.methods.openToast('fail','失败提示')"></nut-cell>
<nut-cell title="Warning 警告提示" is-link @click="page.methods.openToast('warn','警告提示')"></nut-cell>
<nut-cell title="Loading 加载提示" is-link @click="page.methods.openToast('loading','加载中')"></nut-cell>
<nut-cell title="Loading 带白色背景遮罩" is-link @click="page.methods.openToast('loading','加载中',true)"></nut-cell>
```
``` javascript
import { reactive } from 'vue';
export default {
  setup() {
    const page = {
      state: reactive({
        msg: 'toast',
        type: 'text',
        show: false,
        cover: false
      }),
      methods: {
        openToast: (type: string, msg: string, cover: boolean = false) => {
          page.state.show = true;
          page.state.msg = msg;
          page.state.type = type;
          page.state.cover = cover;
        },
        onClosed: () => console.log('closed')
      }
    };
    return {
      page
    };
  }
};
```
### 基本用法


### API
| 方法名        | 说明         | 参数            | 返回值     |
|---------------|--------------|-----------------|------------|
| Toast.text    | 展示文字提示 | options/message | toast 实例 |
| Toast.success | 展示成功提示 | options/message | toast 实例 |
| Toast.fail    | 展示失败提示 | options/message | toast 实例 |
| Toast.warn    | 展示警告提示 | options/message | toast 实例 |
| Toast.hide    | 关闭提示     | force:boolean   | void       |
| Toast.loading | 展示加载提示 | options/message | toast 实例 |

## Props

| 字段                   | 说明                                                                          | 类型          | 默认值                        |
|------------------------|-------------------------------------------------------------------------------|---------------|-------------------------------|
| msg                    | 消息文本内容,支持传入HTML                                                     | String/VNode  | ""                            |
| duration               | 展示时长（毫秒）<br>值为 0 时，toast 不会自动消失（loading类型默认为0）       | Number        | 2000                          |
| center                 | 是否展示在页面中部（为false时展示在底部）                                     | Boolean       | true                          |
| bottom                 | 距页面底部的距离（像素），center为false时生效                                 | Number        | 30                            |
| text-align-center      | 多行文案是否居中                                                              | Boolean       | true                          |
| bg-color               | 背景颜色（透明度）                                                            | String        | "rgba(0, 0, 0, 0.8)"          |
| custom-class           | 自定义类名                                                                    | String        | ""                            |
| icon                   | 自定义图标，**对应icon组件，支持图片链接**                                    | String        | ""                            |
| size                   | 文案尺寸，**small**/**base**/**large**三选一                                  | String        | "base"                        |
| cover                  | 是否显示遮罩层，loading类型默认显示                                           | Boolean       | loading类型true/其他类型false |
| cover-color            | 遮罩层颜色，默认透明                                                          | String        | "rgba(0,0,0,0)"               |
| loading-rotate         | loading图标是否旋转，仅对loading类型生效                                      | Boolean       | true                          |
| on-close               | 关闭时触发的事件                                                              | function      | null                          |
| close-on-click-overlay | 是否在点击遮罩层后关闭提示                                                    | Boolean       | false                         |
| toast-style            | 提示框style                                                                   | object        | {}                            |
| toast-class            | 提示框class                                                                   | String        | ""                            |

