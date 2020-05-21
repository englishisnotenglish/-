### phaser介绍
参考资源相关：
* [api文档地址](https://photonstorm.github.io/phaser3-docs/index.html)
* [样例地址](https://phaser.io/examples/v3)
* [phaser3初识](https://aotu.io/notes/2018/12/23/phaser3/index.html)

主要的三个部分
* [Game](https://photonstorm.github.io/phaser3-docs/Phaser.Game.html)全局控制器，适合设置全局属性和一些配置，尽量避免访问game实例，多使用secne提供的方法，类似SPA里面router作用。
* [Scene](https://photonstorm.github.io/phaser3-docs/Phaser.Scene.html)作用就是类似route，可以简化理解成一个页面，功能就是一个游戏场景
* [Config](https://photonstorm.github.io/phaser3-docs/Phaser.Types.html)生成示例能做的配置项目


#### scene
* scene主要的三个方法 [api查看](https://photonstorm.github.io/phaser3-docs/Phaser.Scene.html#toc0__anchor)
    * preload 资源预加载在create之前执行
    * create 创建方法
    * update 类似requestAnimationFrame写了的话在帧频率间隔调用
    * scene内置了很多对象，对对象的名称都有简化，比如input :Phaser.Input.InputPlugin，scene.input就可以直接使用事件系统

常用功能介绍
* loader 资源加载 [api查看](https://photonstorm.github.io/phaser3-docs/Phaser.Loader.LoaderPlugin.html),几个常用的加载方式
    * image 图片
    * spritesheet 雪碧图精灵，适合每个精灵尺寸都一样
    * atlas 雪碧图精灵 + json，按照json的配置去读取资源，适合精灵大小尺寸不一
    * 其他资源加载可以参照api文档，根据情况使用

* input 事件系统 [api查看](https://photonstorm.github.io/phaser3-docs/Phaser.Input.Events.html#toc0__anchor)
    * 事件系统可以给scene添加，类似于给document添加事件
    * 也可以给精灵添加，类似于给元素添加事件，给精灵添加事件需要设置精灵（To receive this event, the Game Object must have been set as interactive. See GameObject.setInteractive for more details.）就是精灵需要调用setInteractive方法
    * 具体使用参照文档
    
* sprite 精灵对象和image对象，作用都是给场景添加物件，大部分情况下，没有太大区别 [精灵api查看](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.Sprite.html)   [图片api查看](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.Image.html)
    * 他们主要的区别在于The main difference between an Image and a Sprite is that you cannot animate an Image as they do not have the Animation component.Image更适合静态。

* 动画相关
    * [Animation](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.Components.Animation.html)更适合逐帧动画，依次播放图片，形成动画.[使用示例](https://labs.phaser.io/edit.html?src=src/animation/animation%20data.js&v=3.22.0)
    * [Tween](https://photonstorm.github.io/phaser3-docs/Phaser.Tweens.Tween.html)更适合精细控制，类似于css Transform属性，可以精细化控制动画。[使用示例](https://phaser.io/examples/v3/view/tweens/immediate-stop-a-tween)

* 绘制相关,只列举几个常用的
    * DOMElement 可以绘制DOM元素到场景中[api](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.DOMElement.html)
    * Graphics基本图形，比如原型，矩形，之类的，语法类似canvas[api](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.Graphics.html)
    * Curve，绘制曲线[api](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.Curve.html)
    * 其他绘制类型可以参考GameObjects列表,
 * todo camera相关，具体开发demo
