---
*Flutter 150+ widget 系列示例，持续更新ing~~，更新顺序为按A-Z排序，目前代码中已包含150+个示例。*<br>
*[查看代码](https://github.com/memtopia/flutter_rampup_demo_app) 或者 [查看web完整示例](https://memtopia.github.io)*<br>
*目前有部分widget在web端还有问题，如想查看更完整的例子Android 和 iOS用户可同步代码后编译安装到手机上查看*

---


AnimatedAlign， 带动画版本的Align<br>

AnimatedAlign的参数
* 【child】child节点
* 【alignment】Alignment类型，控制对齐方式，支持topLeft,topCenter,topRight,centerLeft,center,centerRight,bottomLeft,bottomCenter,bottomRight
* 【curve】Curves 类型很多，具体效果请看[Curves](https://api.flutter-io.cn/flutter/animation/Curves-class.html)
* 【duration】一个动画周期的持续时间
* 【onEnd】动画结束的无参回调

部分代码

```dart
Column(
  mainAxisSize: MainAxisSize.min,
  children: <Widget>[
    Container(
      height: 200.0,
      width: 200.0,
      color: Colors.red.withOpacity(0.4),
      child: AnimatedAlign(
        alignment: _alignment,
        curve: Curves.ease,
        duration: Duration(seconds: 1),
        child: FlutterLogo(
          size: 60,
        ),
        onEnd: (){print("动画结束");},
      ),
    ),
    RaisedButton(
      onPressed: () {
        setState(() {
          _alignment = _alignment == Alignment.topRight ? Alignment.bottomLeft : Alignment.topRight;
        });
      },
      child: Text(
        "Click me",
      ),
    )
  ],
)

```
![Align](https://github.com/memtopia/flutter_rampup/raw/master/images/AnimatedAlign.gif)


点击按钮后，带动画的改变FlutterLogo的对齐方式
