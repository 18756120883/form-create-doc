# Cascader 多级联动

::: tip 省市区联动json数据

[https://github.com/xaboy/form-create/tree/master/district](https://github.com/xaboy/form-create/tree/master/district)

:::

#### [在线预览](https://jsrun.pro/EehKp/edit)

#### Maker
```js
maker.cascader('所在区域','address',['陕西省','西安市','新城区']).props({
        data:window.province
})
```

#### JSON
```json
{
    type:"cascader",
    title:"所在区域",
    field:"address",
    value:['陕西省','西安市','新城区'],
    props:{
        data:[{
            value: 'beijing',
            label: '北京',
            children: [
                {
                    value: 'gugong',
                    label: '故宫'
                },
                {
                    value: 'tiantan',
                    label: '天坛'
                },
                {
                    value: 'wangfujing',
                    label: '王府井'
                }
            ]
        }, {
            value: 'jiangsu',
            label: '江苏',
            children: [
                {
                    value: 'nanjing',
                    label: '南京',
                    children: [
                        {
                            value: 'fuzimiao',
                            label: '夫子庙',
                        }
                    ]
                },
                {
                    value: 'suzhou',
                    label: '苏州',
                    children: [
                        {
                            value: 'zhuozhengyuan',
                            label: '拙政园',
                        },
                        {
                            value: 'shizilin',
                            label: '狮子林',
                        }
                    ]
                }
            ]
        }]
    }
}
```

参考:[iview2.x](http://v2.iviewui.com/components/cascader#API) | [iview3.x](https://www.iviewui.com/components/cascader#API)

**value**: `Array`

#### props


| 属性             | 说明                                                         | 类型     | 默认值                     |
| :--------------- | :----------------------------------------------------------- | :------- | :------------------------- |
| data             | 可选项的数据源，格式参照示例说明                             | Array    | []                         |
| render-format    | 选择后展示的函数，用于自定义显示格式                         | Function | label => label.join(' / ') |
| disabled         | 是否禁用选择器                                               | Boolean  | false                      |
| clearable        | 是否支持清除                                                 | Boolean  | true                       |
| placeholder      | 输入框占位符                                                 | String   | 请选择                     |
| trigger          | 次级菜单展开方式，可选值为 `click` 或 `hover`                | String   | click                      |
| change-on-select | 当此项为 true 时，点选每级菜单选项值都会发生变化，具体见上面的示例 | Boolean  | false                      |
| size             | 输入框大小，可选值为`large`和`small`或者不填                 | String   | -                          |
| load-data        | 动态获取数据，数据源需标识 loading                           | Function | -                          |
| filterable       | 是否支持搜索                                                 | Boolean  | false                      |
| not-found-text   | 当搜索列表为空时显示的内容                                   | String   | 无匹配数据                 |
| transfer         | 是否将弹层放置于 body 内，在 Tabs、带有 fixed 的 Table 列内使用时，建议添加此属性，它将不受父级样式影响，从而达到更好的效果 | Boolean  | false                      |
| element-id       | 给表单元素设置 `id`，详见 Form 用法。                        | String   | -                          |

#### on 事件

| 事件名            | 说明                                                         | 返回值              |
| :---------------- | :----------------------------------------------------------- | :------------------ |
| on-change         | 选择完成后的回调，返回值 value 即已选值 value，selectedData 为已选项的具体数据 | value, selectedData |
| on-visible-change | 展开和关闭弹窗时触发                                         | 显示状态，Boolean   |
