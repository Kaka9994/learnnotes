---
title: cocos 基础
date: 2021-04-13 19:03:00
tags: cocos

---



## 坐标系

| 坐标系       | 朝向     | 原点             |
| ------------ | -------- | ---------------- |
| 节点坐标系   | 锚点决定 | x轴向右，y轴向上 |
| 纹理uv坐标系 | 左上角   | u轴向右，v轴向下 |
| 屏幕坐标系   | 左上角   | x轴向右，y轴向下 |
| GL坐标系     | 左上角   | x轴向右，y轴向上 |
| 世界坐标系   | 左下角   | x轴向右，y轴向上 |



##  Cocos内置装饰器

1. 类装饰器

   ```javascript
   // 声明成cc.Class类
   //
   // 值类型：Object
   // 默认值：定义的原型对象
   ccclass: any,
   
   // 允许当前组件在编辑器模式下运行。
   // 默认情况下，所有组件都只会在运行时执行，也就是说它们的生命周期回调在编辑器模式下并不会触发。
   //
   // 值类型：Boolean
   // 默认值：false
   executeInEditMode: false,
     
   // 允许当前组件在编辑器模式下运行。
   // 默认情况下，所有组件都只会在运行时执行，也就是说它们的生命周期回调在编辑器模式下并不会触发。
   //
   // 值类型：Boolean
   // 默认值：false
   executeInEditMode: false,
   
   // requireComponent 参数用来指定当前组件的依赖组件。
   // 当组件添加到节点上时，如果依赖的组件不存在，引擎将会自动将依赖组件添加到同一个节点，防止脚本出错。
   // 该选项在运行时同样有效。
   // 
   // 值类型：Function （必须是继承自 cc.Component 的构造函数，如 cc.Sprite）
   // 默认值：null
   requireComponent: null,
   
   // 脚本生命周期回调的执行优先级。
   // 小于 0 的脚本将优先执行，大于 0 的脚本将最后执行。
   // 该优先级只对 onLoad, onEnable, start, update 和 lateUpdate 有效，对 onDisable 和 onDestroy 无效。
   //
   // 值类型：Number
   // 默认值：0
   executionOrder: 0,
   
   // 当本组件添加到节点上后，禁止同类型（含子类）的组件再添加到同一个节点，
   // 防止逻辑发生冲突。
   // 
   // 值类型：Boolean
   // 默认值：false
   disallowMultiple: false,
   
   // menu 用来将当前组件添加到组件菜单中，方便用户查找。
   // 
   // 值类型：String （如 "Rendering/Camera"）
   // 默认值：""
   menu: "",
   
   // 当设置了 "executeInEditMode" 以后，playOnFocus 可以用来设定选中当前组件所在的节点时，
   // 编辑器的场景刷新频率。
   // playOnFocus 如果设置为 true，场景渲染将保持 60 FPS，如果为 false，场景就只会在必要的时候进行重绘。
   // 
   // 值类型：Boolean
   // 默认值：false
   playOnFocus: false,
   
   // 自定义当前组件在 **属性检查器** 中渲染时所用的网页 url。
   // 
   // 值类型：String
   // 默认值：""
   inspector: "",
   
   // 自定义当前组件在编辑器中显示的图标 url。
   // 
   // 值类型：String
   // 默认值：""
   icon: "",
   
   // 指定当前组件的帮助文档的 url，设置过后，在 **属性检查器** 中就会出现一个帮助图标，
   // 用户点击将打开指定的网页。
   // 
   // 值类型：String
   // 默认值：""
   help: "",
   ```

2. 属性装饰器

   ```javascript
   // 指定当前属性的信息，以下是属性可设置的参数
   // type: any													限定属性的数据类型，默认值 undefined
   // visible: boolean|(() => boolean)   在 属性检查器 中显示或隐藏，默认值 取决于属性命是否带_
   // displayName: string                在 属性检查器 中显示为另一个名字，默认值 undefined
   // tooltip: string                    在 属性检查器 中添加属性的 Tooltip，默认值 undefined
   // multiline: boolean                 在 属性检查器 中使用多行文本框，默认值 false
   // readonly: boolean                  在 属性检查器 中只读，默认值 false
   // min: number												限定数值在编辑器中输入的最小值，默认值 undefined
   // max: number												限定数值在编辑器中输入的最大值，默认值 undefined
   // step: number												指定数值在编辑器中调节的步长，默认值 undefined
   // range: number[]										一次性设置 min, max, step，默认值 undefined
   // slide: boolean											在 属性检查器 中显示为滑动条，默认值 false
   // serializable: boolean              序列化该属性，默认值 true
   // formerlySerializedAs: string       指定之前序列化所用的字段名，默认值 undefined
   // editorOnly: boolean                在导出项目前剔除该属性，默认值 false
   // override: boolean                  当重写父类属性时需要定义该参数为 true，默认值 false
   // animatable: boolean                该属性是否能被 动画编辑器 修改，默认值 undefined
   // 
   // 值类型：Object
   // 默认值：null
   property
   ```

   