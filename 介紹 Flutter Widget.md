# 介紹 Flutter Widget 
## 目錄 Menu
[Toc]



##  說明 Illustration

1. 本篇提供作為參考複習筆記，如若需要教學，可以前往 [Youtube : The Net Ninja](https://www.youtube.com/watch?v=1ukSR1GRtMU&list=PL4cUxeGkcC9jLYyp2Aoh6hcWuxFDX6PBJ) 學習
2. 本篇參考 [Flutter API](https://api.flutter.dev/) , [Youtube : The Net Ninja](https://www.youtube.com/watch?v=1ukSR1GRtMU&list=PL4cUxeGkcC9jLYyp2Aoh6hcWuxFDX6PBJ) , 以及自身經驗，如若有誤，可以 <a href='mailto: yuenho092590@gmail.com'>寄信給我</a>
3. 本篇的 「 舉例示範 」 皆有 **import 'package:flutter/material.dart';**
   而 「 顯示結果 」 使用模擬機為 Google Pixel XL , 系統版本為 Android 11.0



## A. 介面 Scaffold Widget
### I. [Scaffold](https://api.flutter.dev/flutter/material/Scaffold-class.html)
* 描述 Description : 有基本設計層面框架的介面 Class
* 建構式 Constructor :
```
const Scaffold({
	Key? key,
	PreferredSizeWidget? appBar, 
	Widget? body, 
	Widget? floatingActionButton,
	FloatingActionButtonLocation? floatingActionButtonLocation,
	FloatingActionButtonAnimator? floatingActionButtonAnimator, 
	List<Widget>? persistentFooterButtons,
	Widget? drawer,
	DrawerCallback? onDrawerChanged,
	Widget? endDrawer,
	DrawerCallback? onEndDrawerChanged, 
	Widget? bottomNavigationBar, 
	Widget? bottomSheet, 
	Color? backgroundColor, 
	bool? resizeToAvoidBottomInset, 
	bool primary, 
	DragStartBehavior drawerDragStartBehavior, 
	bool extendBody, 
	bool extendBodyBehindAppBar, 
	Color? drawerScrimColor, double? 
	drawerEdgeDragWidth, 
	bool drawerEnableOpenDragGesture, 
	bool endDrawerEnableOpenDragGesture, 
	String? restorationId
})
```
* 要求的建構式參數 Required Constructor Parameters: None
* 其他可加的建構式參數 Other Constructor Parameters :
  1. App標題條 appBar
  2. 內容 body  ( Widget )
  3. 按鈕 floatingActionButton 
  4. ...
* 舉例示範 Example : 
``` java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(title: Text('AppBar')),
        body: Center(child: Text('Body')),
        floatingActionButton:
            FloatingActionButton(child: Text('Button'), onPressed: () {})),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/MCST8kh.png =40%x)
#### a. 建構式參數 Constructor Parameters 'appbar' : [AppBar](https://api.flutter.dev/flutter/material/AppBar-class.html)
* 描述 Description : 常當作 App 標題 Class
* 建構式 Constructor :
```
const AppBar({
	Key? key,
	Widget? leading,
	bool automaticallyImplyLeading,
	Widget? title,
	List<Widget>? actions,
	Widget? flexibleSpace,
	PreferredSizeWidget? bottom,
	double? elevation,
	Color? shadowColor,
	ShapeBorder? shape,
	Color? backgroundColor,
	Color? foregroundColor,
	Brightness? brightness,
	IconThemeData? iconTheme,
	IconThemeData? actionsIconTheme,
	TextTheme? textTheme,
	bool primary,
	bool? centerTitle,
	bool excludeHeaderSemantics,
	double? titleSpacing,
	double toolbarOpacity,
	double bottomOpacity,
	double? toolbarHeight,
	double? leadingWidth,
	bool? backwardsCompatibility,
	TextStyle? toolbarTextStyle,
	TextStyle? titleTextStyle,
	SystemUiOverlayStyle? systemOverlayStyle
	})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 標題 title
  2. 置中 centerTitle
  3. 背景顏色 backgroundColor 
  4. 陰影 elevation
  5. ...
* 補充 Supplement : 
  1. 參數 appBar 可以放的類別 Widget Class :
  **AppBar, CupertinoTabBar, ObstructingPreferredSizeWidget, PreferredSize, TabBar**
* 舉例示範 Example : 
``` java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
          appBar: AppBar(
    title: Text('AppBar'),
    centerTitle: true,                           // bool 值
    backgroundColor: Colors.purple[300],
  ))));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/oPv3iUt.png =40%x)
#### b. 建構式參數 Constructor Parameters 'floatingActionButton' : 按鈕 [FloatingActionButton](https://api.flutter.dev/flutter/material/FloatingActionButton-class.html)
* 描述 Description : 圓形按鈕 Class
* 建構式 Constructor :
```
const FloatingActionButton({
	Key? key,
	Widget? child,
	String? tooltip,
	Color? foregroundColor,
	Color? backgroundColor,
	Color? focusColor,
	Color? hoverColor,
	Color? splashColor,
	Object? heroTag,
	double? elevation,
	double? focusElevation,
	double? hoverElevation,
	double? highlightElevation,
	double? disabledElevation,
	required VoidCallback? onPressed,
	MouseCursor? mouseCursor,
	bool mini,
	ShapeBorder? shape,
	Clip clipBehavior,
	FocusNode? focusNode,
	bool autofocus,
	MaterialTapTargetSize? materialTapTargetSize,
	bool isExtended
	})
```
* 要求的建構式參數 Required : 按下後執行的程式 onPressed
* 其他可加的建構式參數 Other Constructor Parameters : 內容 child, 背景顏色 backgroundColor
* 補充 Supplement : 
  1. 參數 floatingActionButton 可以放任何 Widget Class
  2. 位置在右下角
* 舉例示範 Example :
``` java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,                          
      backgroundColor: Colors.purple[300],
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},                          // VoidCallBack ( void function )
      child: Text('Button'),
      backgroundColor: Colors.purple[500],
    ),
  )));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/OM6sKyp.png =40%x)



## B. 文字 Text Widget
### I. [Text](https://api.flutter.dev/flutter/widgets/Text-class.html)
* 描述 Description : 文字 Widget 
* 建構式 Constructor :
``` 
const Text(
    String data, {
    Key? key,
    TextStyle? style,
    StrutStyle? strutStyle,
    TextAlign? textAlign,
    TextDirection? textDirection,
    Locale? locale,
    bool? softWrap,
    TextOverflow? overflow,
    double? textScaleFactor,
    int? maxLines,
    String? semanticsLabel,
    TextWidthBasis? textWidthBasis,
    TextHeightBehavior? textHeightBehavior
})
``` 
* 要求的建構式參數 Required Constructor Parameters : 
  1. 字串 data
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 樣式 style  ( TextStyle )
  2. ...

* 舉例示範 Example code :
```java= 
void main() {
  runApp(MaterialApp(
    home: Scaffold(
      body: Center(child: Text('Text Widget')),
    ),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/tnR12pY.png =40%x)
#### a. 建構式參數 Constructor Parameters 'style' : [TextStyle](https://api.flutter.dev/flutter/painting/TextStyle-class.html)
* 描述 Description : 文字樣式 Class
* 建構式 Constructor : 
```
const TextStyle({
    bool inherit,
    Color? color,
    Color? backgroundColor,
    double? fontSize,
    FontWeight? fontWeight,
    FontStyle? fontStyle,
    double? letterSpacing,
    double? wordSpacing,
    TextBaseline? textBaseline,
    double? height,
    TextLeadingDistribution? leadingDistribution,
    Locale? locale,
    Paint? foreground,
    Paint? background,
    List<Shadow>? shadows,
    List<FontFeature>? fontFeatures,
    TextDecoration? decoration,
    Color? decorationColor,
    TextDecorationStyle? decorationStyle,
    double? decorationThickness,
    String? debugLabel,
    String? fontFamily,
    List<String>? fontFamilyFallback,
    String? package
})
```
* 要求的建構式參數 Required Constructor Parameters :  None
* 其他可加的建構式參數 Other Constructor Parameters :
  1. 顏色 color, 
  2. 大小 fontSize, 
  3. 粗細 fontWeight, 
  4. 字體 fontFamily, 
  5. 字距 letterSpacing 
  6. ...
* 提醒 Reminder :  字體須從 pubspec.yaml 先引進
```java= 
// pubspec.yaml

fonts:
- family: Nunito                           // 字體名
	fonts:
    - asset: fonts/Nunito-Regular.ttf      // 字體來源(於fonts檔案夾中的ttf檔)
```
* 舉例示範 Example :
```java= 
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        body: Center(
      child: Text('Text Widget',
          style: TextStyle(
            color: Colors.purple[400],
            fontSize: 30.0,
            letterSpacing: 2.0,
            fontWeight: FontWeight.bold,
            fontFamily: 'Nunito', // 字體需先從yaml引進
          )),
    )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/dMF8Xju.png =40%x)



## C. 顏色 Color Class
### I. [Color](https://api.flutter.dev/flutter/dart-ui/Color-class.html)
* 描述 Description : 顏色 class
* 建構式 Constructor : 
  1. [Color](https://api.flutter.dev/flutter/dart-ui/Color/Color.html)
     * 描述 Description : 利用**16 進位制**指定顏色 - 0xAARRGGBB 
     ( 其中 A - 不透明度 alpha , R - 紅 red, G - 綠 green, B - 藍 blue ，皆各為 0 ~ 2 <sup>8</sup> - 1 )
     * 建構式 Constructor : 
     ```
     const Color(int value)
     ```
     * 要求的建構式參數 Required Constructor Parameters : 
       1. 值 value ( 0 ~ 2<sup>32</sup> - 1 ) 
     * 其他可加的參數 Other Parameters : None
     * 舉例示範 Example : 
     ```java=
     void main() {
       runApp(MaterialApp(
           home: Scaffold(
          appBar: AppBar(
           title: Text('AppBar'),
           centerTitle: true, 
           backgroundColor: Color(0xFFFF9000),
         ),
         floatingActionButton: FloatingActionButton(
           onPressed: () {}, 
           child: Text('Button'),
           backgroundColor: Color(0xFFFF9000),
         ),
       )));
     }
     ```
     * 顯示結果 Result : 
       ![](https://i.imgur.com/lur0RKn.png =40%x)
  2. [Color.fromARGB](https://api.flutter.dev/flutter/dart-ui/Color/Color.fromARGB.html)
     * 描述 Description : 利用 " 不透明度 alpha , 紅 red, 綠 green, 藍 blue " 去指定想要的顏色
     * 建構式 Constructor : 
    　```
    　const Color.fromARGB(int a, int r, int g, int b)
   　 ```
     * 要求的參數 Required Parameters : 
       1. 不透明度 Alpha   ( 0 - 255 )
       2. 紅 Red          ( 0 - 255 )
       3. 綠 Green        ( 0 - 255 )
       4. 藍 Blue         ( 0 - 255 )
     * 其他可加的參數 Other Parameters : None
     * 舉例示範 Example : 
     ```java=
     void main() {
         runApp(MaterialApp(
             home: Scaffold(
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true, 
               backgroundColor: Color.fromARGB(150, 200, 0, 100),
             ),
             floatingActionButton: FloatingActionButton(
               onPressed: () {}, 
               child: Text('Button'),
               backgroundColor: Color.fromARGB(150, 200, 0, 100),
             ),
           )));
     }
     ```
     * 顯示結果 Result : 
       ![](https://i.imgur.com/UkxQapn.png =40%x)
  3. [Color.fromRGBO](https://api.flutter.dev/flutter/dart-ui/Color/Color.fromRGBO.html)
     * 描述 Description : 利用 " 紅 red, 綠 green, 藍 blue, 不透明度 opacity " 去指定想要的顏色
     * 方法 Method : 
     ```
     const Color.fromRGBO(int r, int g, int b, double opacity)
     ```
     * 要求的參數 Required Parameters : 
       1. 紅 Red           ( 0 - 255 )
       2. 綠 Green         ( 0 - 255 )
       3. 藍 Blue          ( 0 - 255 )
       4. 不透明度 Opacity  ( 0 - 1 )
     * 其他的參數 Other Parameters : None
     * 舉例示範 Example : 
     ```java=
     void main() {
       runApp(MaterialApp(
           home: Scaffold(
         appBar: AppBar(
           title: Text('AppBar'),
           centerTitle: true,
           backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
         ),
         floatingActionButton: FloatingActionButton(
           onPressed: () {}, 
           child: Text('Button'),
           backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
         ),
       )));
     }
     ```
     * 顯示結果 Result : 
     ![](https://i.imgur.com/XR9u2qJ.png =40%x)


### II. [Colors](https://api.flutter.dev/flutter/material/Colors-class.html)
* 描述 Description : 擁有多種基本顏色, 使用在文字顏色、背景顏色 ...
* 參考 Reference : 參考 [Flutter 顏色網站](https://api.flutter.dev/flutter/material/Colors-class.html)
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Colors.pink[100],
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {}, 
      child: Text('Button'),
      backgroundColor: Colors.pink[100],
    ),
  )));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/1g1NfG0.png =40%x)



## D. 置中 Center Widget

### I. [Center](https://api.flutter.dev/flutter/widgets/Center-class.html)
* 描述 Description : 使其內容 child 置中的 Widget
* 建構式 Constructor : 
```
const Center({
    Key? key, 
    double? widthFactor,
    double? heightFactor, 
    Widget? child
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 內容 child ( Widget )
  2. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Colors.pink[100],
    ),
    body: Center(
      child: Text('Text Widget'),
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Text('Button'),
      backgroundColor: Colors.pink[100],
    ),
  )));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/5ZdWOnM.png =40%x)



## E. 圖片 Image Widget
### I. [Image](https://api.flutter.dev/flutter/widgets/Image-class.html)
* 描述 Description : 圖片 Widget
* 建構式 Constructor : 
```
const Image({
    Key? key,
    required ImageProvider<Object> image,
    ImageFrameBuilder? frameBuilder,
    ImageLoadingBuilder? loadingBuilder,
    ImageErrorWidgetBuilder? errorBuilder,
    String? semanticLabel,
    bool excludeFromSemantics,
    double? width,
    double? height,
    Color? color,
    BlendMode? colorBlendMode,
    BoxFit? fit,
    AlignmentGeometry alignment,
    ImageRepeat repeat,
    Rect? centerSlice,
    bool matchTextDirection,
    bool gaplessPlayback,
    bool isAntiAlias,
    FilterQuality filterQuality
})
```

* 要求的建構式參數 Required Constructor Parameters : 
  1. 圖片 image
  2. ...
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 寬 width
  2. 高 height
  3. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
    body: Center(
      child: Image(
          image: NetworkImage('https://i.imgur.com/Gso5E3C.jpg'), width: 300.0),
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Text('Button'),
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
  )));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/p2hXTDp.png =40%x)
#### a. 建構式參數 Constructor Parameter 'image' - 1 :  [AssetImage](https://api.flutter.dev/flutter/painting/AssetImage-class.html)
* 描述 Description : 為圖片提供者 ( ImageProvider ), 用於一些 Widgets 需要圖片時
* 建構式 Constructor : 
```
const AssetImage(
    String assetName, {
    AssetBundle? bundle,
    String? package
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 字串 str =>  本地圖片位置  ( 需先從 pubspec.yaml 引進 ) 
```java=
// pubspec.yaml

assets:
 - images/photo.jpg                     // 資料夾../檔名.副檔名
``` 
* 其他可加的建構式參數 Other Constructor Parameters : ...
* 提醒 Reminder : 此 **並非** Widget, 不得替代 Image.asset
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
    body: Center(
      child: Image(image: AssetImage('images/photo.jpg')),
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Text('Button'),
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
  )));
}
```
* 顯示結果 Results : 
  ![](https://i.imgur.com/V55o025.jpg =40%x)
#### b. 建構式參數 Constructor Parameter 'image' - 2 :  [NetworkImage](https://api.flutter.dev/flutter/painting/NetworkImage-class.html)
* 描述 Description : 為圖片提供者 ( ImageProvider ), 用於一些 Widgets 需要圖片時
* 建構式 Constructor : 
```
const NetworkImage(
    String url, {
    double scale, 
    Map<String, String>? headers
})
```
* 要求的建構式參數 Required Parameters : 
  1. 字串 str =>  雲端網址 
* 其他可加的建構式參數 Other Constructor Parameters : ...
* 提醒 Reminder : 此 **並非** Widget, 不得替代 Image.network
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
    body: Center(
      child: Image(
          image: NetworkImage('https://i.imgur.com/Gso5E3C.jpg'))
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Text('Button'),
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
  )));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/V55o025.jpg =40%x)
### II. [Image.asset](https://api.flutter.dev/flutter/widgets/Image/Image.asset.html)
* 描述 Description : 圖片 Widget
* 建構式 Constructor : 
```
Image.asset(
    String name,{
    Key? key,
    AssetBundle? bundle,
    ImageFrameBuilder? frameBuilder,
    ImageErrorWidgetBuilder? errorBuilder,
    String? semanticLabel,
    bool excludeFromSemantics,
    double? scale,
    double? width,
    double? height,
    Color? color,
    BlendMode? colorBlendMode,
    BoxFit? fit,
    AlignmentGeometry alignment,
    ImageRepeat repeat,
    Rect? centerSlice,
    bool matchTextDirection,
    bool gaplessPlayback,
    bool isAntiAlias,
    String? package,
    FilterQuality filterQuality,
    int? cacheWidth,
    int? cacheHeight
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 字串 name =>  本地圖片位置  ( 需先從 pubspec.yaml 引進 )
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 寬 width
  2. 高 height
  3. ...
```java=
// pubspec.yaml
  assets:
   - images/photo.jpg
``` 
* 其他可加的建構式參數 Other Constructor Parameters : ...
* 舉例示範 Example :
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
    body: Center(
      child: Image.asset(
        'images/photo.jpg',
        width: 300.0,
      ),
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Text('Button'),
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
  )));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/Nyv3Xf2.png =40%x)
```java=
Image.asset('assets/day.png')
```
### III. [Image.network](https://api.flutter.dev/flutter/widgets/Image/Image.network.html)
* 描述 Description : 圖片 Widget
* 要求的建構式參數 Required Constructor Parameters : 字串 str =>  雲端圖片網址
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 寬 width
  2. 高 height
  3. ...
* 舉例示範 Example :
```java=
void main() {
  runApp(MaterialApp(
      home: Scaffold(
    appBar: AppBar(
      title: Text('AppBar'),
      centerTitle: true,
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
    body: Center(
      child: Image.network(
        'https://i.imgur.com/Gso5E3C.jpg',
        width: 300.0,
      ),
    ),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Text('Button'),
      backgroundColor: Color.fromRGBO(200, 150, 100, 0.5),
    ),
  )));
}
```
* 顯示結果 Result :
  ![](https://i.imgur.com/Nyv3Xf2.png =40%x)



## F. 頭像 Avatar Widget
### I. [CircleAvatar](https://api.flutter.dev/flutter/material/CircleAvatar-class.html)
* 描述 Description : 圓形頭像 ( 圖片 ) Widget
* 建構式 Constructor : 
```
CircleAvatar({
    Key? key, 
    Widget? child, 
    Color? backgroundColor, 
    ImageProvider<Object>? backgroundImage, 
    ImageProvider<Object>? foregroundImage, 
    ImageErrorListener? onBackgroundImageError, 
    ImageErrorListener? onForegroundImageError, 
    Color? foregroundColor, 
    double? radius, 
    double? minRadius, 
    double? maxRadius
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 內容 child
  2. 背景顏色 backgroundColor
  3. 背景圖片 backgroundImage
  4. 半徑 radius
  5. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Center(
          child: CircleAvatar(
            radius: 80.0,
            backgroundImage: NetworkImage('https://i.imgur.com/Gso5E3C.jpg'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 結果顯示 Result : 
  ![](https://i.imgur.com/xQ3THM2.png =40%x)



## G. 圖標 Icon Widget
### I. [Icon](https://api.flutter.dev/flutter/widgets/Icon-class.html)
* 描述 Description : 圖標 Widget
* 建構式 Constructor : 
```
const Icon(
    IconData? icon, {
    Key? key,
    double? size,
    Color? color,
    String? semanticLabel,
    TextDirection? textDirection
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 圖標 icon
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 大小 size
  2. 顏色 color
  3. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
            child: Icon(
          Icons.local_cafe,
          size: 200.0,
          color: Colors.brown,
        )),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/ayT4Kih.png =40%x)
#### a. 建構式參數 Constructor Parameter 'icon' : [Icons](https://api.flutter.dev/flutter/material/Icons-class.html)
* 描述 Description : 擁有多種基本圖標, 使用在按鈕、內容...
* 參考 Reference : 參考 [Flutter 圖標網站](https://api.flutter.dev/flutter/material/Icons-class.html#constants)
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(child: Icon(Icons.local_atm, size: 200.0)),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/WbvHsWf.png =40%x)




## H. 按鈕 Button Widget
### I. [TextButton](https://api.flutter.dev/flutter/material/TextButton-class.html) 
* 描述 Description : 沒有陰影、邊界的平坦按鈕 Widget Class
* 建構式 Construct: 
```
const TextButton({
    Key? key,
    required VoidCallback? onPressed,
    VoidCallback? onLongPress,
    ButtonStyle? style,
    FocusNode? focusNode,
    bool autofocus = false,
    Clip clipBehavior = Clip.none,
    required Widget child
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 按下後執行的程式 onPressed
  2. 內容 child  ( Widget )
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 按鈕樣式 style
  2. ...
* 補充 Supplement : 
  YouTube上教學影片中，有些會教到舊的按鈕 ( 已經被棄用，無法使用 ) !
  **如若看到 FlatButton ,  請改用 TextButton**
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: TextButton(
            onPressed: () {},
            child: Text('TextButton'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking 
    ![](https://i.imgur.com/EGK2Kg5.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/UbCKj47.png =40%x)
#### a. 延伸 Extend - 加上圖標的按鈕 TextButton with Icon : [TextButton.icon](https://api.flutter.dev/flutter/material/TextButton/TextButton.icon.html)
* 描述 Description : 同時擁有icon以及label的按鈕 Widget
* 建構式 Constructor : 
```
TextButton.icon({
    Key? key,
    required VoidCallback? onPressed,
    VoidCallback? onLongPress,
    ButtonStyle? style,
    FocusNode? focusNode,
    bool? autofocus,
    Clip? clipBehavior,
    required Widget icon,
    required Widget label
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 按下後執行的程式 onPressed
  2. 圖標 icon
  3. 標籤 label
* 其他要加的建構式參數 Other Constructor Parameters : 
  1. 樣式 style
  2. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: TextButton.icon(
            onPressed: () {},
            icon: Icon(Icons.airplay),
            label: Text('Airplay'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/G5trvTR.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/5T5HwjU.png =40%x)


#### b. Construct Parameter 'style' : [TextButton.styleFrom](https://api.flutter.dev/flutter/material/TextButton/styleFrom.html)
* 描述 Description : TextButton 的按鈕樣式 class
* 方法 Method : 
```
ButtonStyle styleFrom({
    Color? primary,
    Color? onSurface,
    Color? backgroundColor,
    Color? shadowColor,
    double? elevation,
    TextStyle? textStyle,
    EdgeInsetsGeometry? padding,
    Size? minimumSize,
    Size? fixedSize,
    BorderSide? side,
    OutlinedBorder? shape,
    MouseCursor? enabledMouseCursor,
    MouseCursor? disabledMouseCursor,
    VisualDensity? visualDensity,
    MaterialTapTargetSize? tapTargetSize,
    Duration? animationDuration,
    bool? enableFeedback,
    AlignmentGeometry? alignment,
    InteractiveInkFeatureFactory? splashFactory
})
```
* 要求的參數 Required Parameters : None
* 其他可加的參數 Other Parameters : 
  1. 主顏色 primary ( 內容顏色, 按下後的顏色... )
  2. 背景顏色 backgroundColor
  3. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: TextButton(
            onPressed: () {},
            child: Text('TextButton'),
            style: TextButton.styleFrom(primary: Colors.brown),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/vtZjYQp.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/dwfBKzy.png =40%x)
### II. [ElevatedButton](https://api.flutter.dev/flutter/material/ElevatedButton-class.html)
* 描述 Description : 有背景顏色 ( 預設 : 藍色 ) 、陰影的按鈕 Widget
* 建構式 Constructor : 

```
const ElevatedButton({
    Key? key,
    required VoidCallback? onPressed,
    VoidCallback? onLongPress,
    ButtonStyle? style,
    FocusNode? focusNode,
    bool autofocus = false,
    Clip clipBehavior = Clip.none,
    required Widget? child
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 按下後執行的程式 onPressed
  2. 內容 child 
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 樣式 style
  2. ...
* 補充 Supplement : 
  YouTube上教學影片中，有些會教到舊的按鈕 ( 已經被棄用，無法使用 ) !
  **如若看到 RaisedButton ,  請改用 ElevatedButton**
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: ElevatedButton(
            onPressed: () {},
            child: Text('ElevatedButton'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/WWOmDiF.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/eUGCQIw.png =40%x)
#### a. 延伸 Extend - 加上圖標的按鈕 ElevatedButton with Icon : [ElevatedButton.icon](https://api.flutter.dev/flutter/material/ElevatedButton/ElevatedButton.icon.html)
* 描述 Description : 同時擁有icon以及label的按鈕 Widget
* 建構式 Constructor : 
```
ElevatedButton.icon({
    Key? key,
    required VoidCallback? onPressed,
    VoidCallback? onLongPress,
    ButtonStyle? style,
    FocusNode? focusNode,
    bool? autofocus,
    Clip? clipBehavior,
    required Widget icon,
    required Widget label
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 按下後執行的程式 onPressed
  2. 圖標 icon
  3. 標籤 label
* 其他要加的建構式參數 Other Constructor Parameters : 
  1. 樣式 style
  2. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: ElevatedButton.icon(
            onPressed: () {},
            icon: Icon(Icons.airplay),
            label: Text('Airplay'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/F3Lg1Uo.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/11VoNGJ.png =40%x)



#### b. Construct Parameter 'style' : [ElevatedButton.styleFrom](https://api.flutter.dev/flutter/material/ElevatedButton/styleFrom.html)
* 描述 Description : ElevatedButton 的按鈕樣式 class
* 方法 Method : 
```
ButtonStyle styleFrom({
    Color? primary,
    Color? onPrimary,
    Color? onSurface,
    Color? shadowColor,
    double? elevation,
    TextStyle? textStyle,
    EdgeInsetsGeometry? padding,
    Size? minimumSize,
    Size? fixedSize,
    BorderSide? side,
    OutlinedBorder? shape,
    MouseCursor? enabledMouseCursor,
    MouseCursor? disabledMouseCursor,
    VisualDensity? visualDensity,
    MaterialTapTargetSize? tapTargetSize,
    Duration? animationDuration,
    bool? enableFeedback,
    AlignmentGeometry? alignment,
    InteractiveInkFeatureFactory? splashFactory
})
```
* 要求的參數 Required Parameters : None
* 其他可加的參數 Other Parameters : 
  1. 主顏色 primary ( 內容顏色, 按下後的顏色... )
  2. 背景顏色 backgroundColor
  3. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: ElevatedButton(
            onPressed: () {},
            child: Text('TextButton'),
            style: ElevatedButton.styleFrom(primary: Colors.brown),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/vIBzJDt.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/PHpSY4M.png =40%x)
### III. [OutlinedButton](https://api.flutter.dev/flutter/material/OutlinedButton-class.html)
* 描述 Description : 無背景顏色, 有邊線的按鈕 Widget
* 建構式 Constructor : 

```
const OutlinedButton({
    Key? key,
    required VoidCallback? onPressed,
    VoidCallback? onLongPress,
    ButtonStyle? style,
    FocusNode? focusNode,
    bool autofocus = false,
    Clip clipBehavior = Clip.none,
    required Widget child
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 按下後執行的程式 onPressed
  2. 內容 child 
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 樣式 style
  2. ...
* 補充 Supplement : 
  YouTube上教學影片中，有些會教到舊的按鈕 ( 已經被棄用，無法使用 ) !
  **如若看到 OutlineButton ,  請改用 OutlinedButton**
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: OutlinedButton(
            onPressed: () {},
            child: Text('OutlinedButton'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/LlmRReo.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/b0VOt4Y.png =40%x)
#### a. 延伸 Extend - 加上圖標的按鈕 OutlinedButton with Icon : [OutlinedButton.icon](https://api.flutter.dev/flutter/material/OutlinedButton/OutlinedButton.icon.html)
* 描述 Description : 同時擁有icon以及label的按鈕 Widget
* 建構式 Constructor : 
```
OutlinedButton.icon({
    Key? key,
    required VoidCallback? onPressed,
    VoidCallback? onLongPress,
    ButtonStyle? style,
    FocusNode? focusNode,
    bool? autofocus,
    Clip? clipBehavior,
    required Widget icon,
    required Widget label
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 按下後執行的程式 onPressed
  2. 圖標 icon
  3. 標籤 label
* 其他要加的建構式參數 Other Constructor Parameters : 
  1. 樣式 style
  2. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: OutlinedButton.icon(
            onPressed: () {},
            icon: Icon(Icons.airplay),
            label: Text('Airplay'),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/6uh7h0i.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/ZeOoBUI.png =40%x)



#### b. Construct Parameter 'style' : [OutlinedButton.styleFrom](https://api.flutter.dev/flutter/material/OutlinedButton/styleFrom.html)
* 描述 Description : OutlinedButton 的按鈕樣式
* 方法 Method : 
```
ButtonStyle styleFrom({
    Color? primary,
    Color? onPrimary,
    Color? onSurface,
    Color? shadowColor,
    double? elevation,
    TextStyle? textStyle,
    EdgeInsetsGeometry? padding,
    Size? minimumSize,
    Size? fixedSize,
    BorderSide? side,
    OutlinedBorder? shape,
    MouseCursor? enabledMouseCursor,
    MouseCursor? disabledMouseCursor,
    VisualDensity? visualDensity,
    MaterialTapTargetSize? tapTargetSize,
    Duration? animationDuration,
    bool? enableFeedback,
    AlignmentGeometry? alignment,
    InteractiveInkFeatureFactory? splashFactory
})
```
* 要求的參數 Required Parameters : None
* 其他可加的參數 Other Parameters : 
  1. 主顏色 primary ( 內容顏色, 按下後的顏色... )
  2. 背景顏色 backgroundColor
  3. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
          child: OutlinedButton(
            onPressed: () {},
            child: Text('TextButton'),
            style: OutlinedButton.styleFrom(primary: Colors.brown),
          ),
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/wU05T3I.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/g55AXuQ.png =40%x)
### IV. [IconButton](https://api.flutter.dev/flutter/material/IconButton-class.html)
* 描述 Description : 圖標 / 圖片按鈕 Widget
* 建構式 Constructor : 
```
const IconButton({
    Key? key,
    double iconSize,
    VisualDensity? visualDensity,
    EdgeInsetsGeometry padding,
    AlignmentGeometry alignment,
    double? splashRadius,
    Color? color,
    Color? focusColor,
    Color? hoverColor,
    Color? highlightColor,
    Color? splashColor,
    Color? disabledColor,
    required VoidCallback? onPressed,
    MouseCursor mouseCursor,
    FocusNode? focusNode,
    bool autofocus,
    String? tooltip,
    bool enableFeedback,
    BoxConstraints? constraints,
    required Widget icon
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 圖標 icon   ( 只要是 Widget 皆可 )
  2. 按下後執行的程式 onPressed
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 顏色 color
  2. 圖標大小 iconSize
  3. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        ),
        body: Center(
            child: IconButton(
          icon: Icon(Icons.wifi),
          color: Colors.blue,
          iconSize: 100.0,
          onPressed: () {},
        )),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color.fromARGB(150, 200, 0, 100),
        )),
  ));
}
```
* 顯示結果 Result : 
  * Before Clicking
    ![](https://i.imgur.com/d5eTw1Q.png =40%x)
  * When Clicking
    ![](https://i.imgur.com/gQeAzkC.png =40%x)

  

## I. 容器 Container Widget
### I. [Container](https://api.flutter.dev/flutter/widgets/Container-class.html)
* 描述 Description : 含有 填充 padding ,  頁邊空白 margin 的 區塊 Widget
* 建構式 Constructor : 
```
Container({
    Key? key,
    AlignmentGeometry? alignment,
    EdgeInsetsGeometry? padding,
    Color? color,
    Decoration? decoration,
    Decoration? foregroundDecoration,
    double? width,
    double? height,
    BoxConstraints? constraints,
    EdgeInsetsGeometry? margin,
    Matrix4? transform,
    AlignmentGeometry? transformAlignment,
    Widget? child,
    Clip clipBehavior
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. (背景)顏色 color
  2. 寬度 width
  3. 高度 height
  4. 內容 child
  5. 填充 padding
  6. 頁邊空白 margin 
  7. ...
* 補充 Supplement : 
  margin 與 padding 的差別 - 
  
  margin 是與外邊的距離
  padding 則是內部與 內容 child 的距離
  
  ![](https://i.imgur.com/CDDEY1x.png)

* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Container(
            padding: EdgeInsets.symmetric(vertical: 10.0, horizontal: 20.0),
            margin: EdgeInsets.only(top: 200.0,left: 80.0),
            color: Colors.blueAccent[100],
            child: Text('Text Widget in the Container Widget')),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/icPUYXh.png =40%x)
### II. [Padding](https://api.flutter.dev/flutter/widgets/Padding-class.html)
* 描述 Description : 只有填充 padding 的容器
* 建構式 Constructor : 
```
const Padding({
    Key? key,
    required EdgeInsetsGeometry padding,
    Widget? child
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 填充 Padding
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 內容 child 
  2. ...
* 舉例示範 Example :　
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Padding(
            padding: EdgeInsets.all(30.0),
            child: Text('Text Widget in the Padding Widget')),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/zwRM3G7.png =40%x)
### III. [Card](https://api.flutter.dev/flutter/material/Card-class.html)
* 描述 Description : 卡片設計 ( 圓角 , 有陰影 ) Widget
* 建構式 Constructor : 
```
const Card({
    Key? key,
    Color? color,
    Color? shadowColor,
    double? elevation,
    ShapeBorder? shape,
    bool borderOnForeground,
    EdgeInsetsGeometry? margin,
    Clip? clipBehavior,
    Widget? child,
    bool semanticContainer
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 顏色 color
  2. 陰影顏色 shadowColor
  3. 陰影 elevation
  4. 頁邊空白 margin
  5. 內容 child
  6. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            Card(
                margin: EdgeInsets.only(top: 10.0),
                color: Colors.white,
                child: Text('Text 0', style: TextStyle(fontSize: 27.0))),
            Card(
                margin: EdgeInsets.only(top: 10.0),
                color: Colors.white,
                child: Text('Text 1', style: TextStyle(fontSize: 27.0))),
            Card(
                margin: EdgeInsets.only(top: 10.0),
                color: Colors.white,
                child: Text('Text 2', style: TextStyle(fontSize: 27.0))),
            Card(
                margin: EdgeInsets.only(top: 10.0),
                color: Colors.white,
                child: Text('Text 3', style: TextStyle(fontSize: 27.0)))
          ],
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 結果顯示 Result : 
  ![](https://i.imgur.com/rsMqa3Y.png =40%x)
#### a. 建構式參數 Constructor Parameters ' margin ' & ' padding ' : [EdgeInsets](https://api.flutter.dev/flutter/painting/EdgeInsets-class.html)
* 描述 Description : 與四邊相差的距離 class
* 建構式 Constructor : 
  1. [EdgeInsets.all](https://api.flutter.dev/flutter/painting/EdgeInsets/EdgeInsets.all.html)
     * 描述 Description : 與四邊相差相同的距離
     * 建構式 Constructor : 
     ```
        const EdgeInsets.all(double value)
     ```
     * 要求的建構式參數 Required Constructor Parameters : 
        I. 值 value
     * 其他可加的建構式參數 Other Constructor Parameters : None
     * 舉例示範 Example : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Container(  
               margin: EdgeInsets.all(50.0),
               padding: EdgeInsets.all(100.0),
               color: Colors.white,
               child: Text('Container Widget'),
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 顯示結果 Result :
       ![](https://i.imgur.com/X7NGsAN.png =40%x)
  2. [EdgeInsets.fromLTRB](https://api.flutter.dev/flutter/painting/EdgeInsets/EdgeInsets.fromLTRB.html)
     * 描述 Description : 與四邊分別相差的距離
     * 建構式 Constructor : 
     ```
        const EdgeInsets.fromLTRB(double left, double top, double right, double bottom)
     ```
     * 要求的建構式參數 Required Constructor Parameters : 
       I.   左 left
       II.  上 top
       III. 右 right
       IV.  下 Bottom
     * 其他可加的建構式參數 Other Constructor Parameters : None
     * 舉例示範 Example : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Container(  
               margin: EdgeInsets.fromLTRB(20.0, 30.0, 50.0, 70.0),
               padding: EdgeInsets.fromLTRB(20.0, 30.0, 50.0, 70.0),
               color: Colors.white,
               child: Text('Container Widget'),
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 顯示結果 Result : 
       ![](https://i.imgur.com/vA6I3fN.png =40%x)
  3. [EdgeInsets.only](https://api.flutter.dev/flutter/painting/EdgeInsets/EdgeInsets.only.html)
     * 描述 Description : 與四邊的其中幾邊的距離, 其餘為 0
     * 建構式 Constructor : 
     ```
        const EdgeInsets.only({double left, double top, double right, double bottom})
     ```
     * 要求的建構式參數 Required Constructor Parameters : None
     * 其他可加的建構式參數 Other Constructor Parameters : 
       I.   左 left
       II.  上 top
       III. 右 right
       IV.  下 Bottom
     * 舉例示範 Example : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Container(  
               margin: EdgeInsets.only(top: 200.0),
               padding: EdgeInsets.only(top: 50.0, left: 100.0),
               color: Colors.white,
               child: Text('Container Widget'),
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 顯示結果 Result : 
       ![](https://i.imgur.com/HEDKdja.png =40%x)
  4. [EdgeInsets.symmetric](https://api.flutter.dev/flutter/painting/EdgeInsets/EdgeInsets.symmetric.html)
     * 描述 Description : 與四邊對稱地相差相同的距離
     * 建構式 Constructor : 
     ```
        const EdgeInsets.symmetric({double vertical = 0.0, double horizontal = 0.0})
     ```
     * 要求的建構式參數 Required Constructor Parameters : None
     * 其他可加的建構式參數 Other Constructor Parameters : 
       I. 垂直 vertical
       II. 水平 Horizontal
     * 舉例示範 Example : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Container(  
               margin: EdgeInsets.symmetric(vertical: 100.0, horizontal: 50.0),
               padding: EdgeInsets.symmetric(vertical: 100.0, horizontal: 50.0),
               color: Colors.white,
               child: Text('Container Widget'),
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 顯示結果 Result : 
       ![](https://i.imgur.com/ys3fuij.pngb =40%x)



## J. 擴張 Expanded Widget
### I. [Expanded](https://api.flutter.dev/flutter/widgets/Expanded-class.html) 
* 描述 Description : 將內容區塊大小調整到主軸長度，通常用於 Column, Row
* 建構式 Constructor : 
```
Expanded({
    Key? key, 
    int flex = 1, 
    required Widget child
})
```
* 要求的建構式參數 Required Constructor Parameters : 
  1. 內容 child 
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 彈性 flex
     * 整數 int 型態, 用於跟其他 Expanded 的空間占比 ( 預設為 1 : 1 : ... )
  2. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            Expanded(
                child: Text(
                  '1',
                  style: TextStyle(
                      backgroundColor: Colors.white,
                      fontSize: 20.0,
                      fontFamily: 'Nunito'),
                ),
                flex: 1),
            Expanded(
                child: Text(
                  '2',
                  style: TextStyle(
                      backgroundColor: Colors.white,
                      fontSize: 20.0,
                      fontFamily: 'Nunito'),
                ),
                flex: 2),
            Expanded(
                child: Text(
                  '3',
                  style: TextStyle(
                      backgroundColor: Colors.white,
                      fontSize: 20.0,
                      fontFamily: 'Nunito'),
                ),
                flex: 3),
          ],
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 結果顯示 Result : 
  ![](https://i.imgur.com/lxxDPSv.png =40%x)
  
  
  
## K. 行列 Column & Row
### I. [Column](https://api.flutter.dev/flutter/widgets/Column-class.html)
* 描述 Description : 可以擁有多個內容的直行 Widget
* 建構式 Constructor : 
```
Column({
    Key? key,
    MainAxisAlignment mainAxisAlignment = MainAxisAlignment.start,
    MainAxisSize mainAxisSize = MainAxisSize.max,
    CrossAxisAlignment crossAxisAlignment = CrossAxisAlignment.center,
    TextDirection? textDirection,
    VerticalDirection verticalDirection = VerticalDirection.down,
    TextBaseline? textBaseline,
    List<Widget> children = const <Widget>[]
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 內容們 children
  2. 主軸對準 mainAxisAlignment
  3. 垂直(主軸)對準 crossAxisAlignment
  4. ...
* 舉例示範 Example :　
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Column(
          children: [
            Container(
                color: Colors.white,
                padding: EdgeInsets.symmetric(vertical: 80.0, horizontal: 10.0),
                margin: EdgeInsets.all(10.0)),
            Container(
                color: Colors.white,
                padding: EdgeInsets.symmetric(vertical: 80.0, horizontal: 10.0),
                margin: EdgeInsets.all(10.0)),
            Container(
                color: Colors.white,
                padding: EdgeInsets.symmetric(vertical: 80.0, horizontal: 10.0),
                margin: EdgeInsets.all(10.0)),
          ],
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/77jReWV.png =40%x)
### II. [Row](https://api.flutter.dev/flutter/widgets/Row-class.html)
* 描述 Description : 可以擁有多個內容的橫列 Widget
* 建構式 Constructor : 
```
Row({
    Key? key,
    MainAxisAlignment mainAxisAlignment = MainAxisAlignment.start,
    MainAxisSize mainAxisSize = MainAxisSize.max,
    CrossAxisAlignment crossAxisAlignment = CrossAxisAlignment.center,
    TextDirection? textDirection,
    VerticalDirection verticalDirection = VerticalDirection.down,
    TextBaseline? textBaseline,
    List<Widget> children = const <Widget>[]
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 內容們 children
  2. 主軸對準 mainAxisAlignment
  3. 垂直(主軸)對準 crossAxisAlignment
  4. ...
* 舉例示範 Example :
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Row(
          children: [
            Container(
                color: Colors.white,
                padding: EdgeInsets.symmetric(vertical: 50.0, horizontal: 40.0),
                margin: EdgeInsets.all(25.0)),
            Container(
                color: Colors.white,
                padding: EdgeInsets.symmetric(vertical: 50.0, horizontal: 40.0),
                margin: EdgeInsets.all(25.0)),
            Container(
                color: Colors.white,
                padding: EdgeInsets.symmetric(vertical: 50.0, horizontal: 40.0),
                margin: EdgeInsets.all(25.0)),
          ],
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/BNdyr7I.png =40%x)
#### a. 建構式參數 Constructor Parameters 'mainAxisAlignment' : [MainAxisAlignment](https://api.flutter.dev/flutter/rendering/MainAxisAlignment-class.html)
* 描述 Description : 分配主軸內容位置 class ( 主軸 : Column - 直行 , Row - 橫列 )
* 常數 Constants : 
  1. **MainAxisAlignment.start**
     * 描述 Description : 將內容放在主軸開頭
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               mainAxisAlignment: MainAxisAlignment.start,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/QLJuZhU.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               mainAxisAlignment: MainAxisAlignment.start,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/OzSfC3x.png =40%x)
  2. **MainAxisAlignment.center**
     * 描述 Description : 將內容放在主軸中間
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               mainAxisAlignment: MainAxisAlignment.center,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/fqGVbrH.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               mainAxisAlignment: MainAxisAlignment.center,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/psbNizR.png =40%x)
  3. **MainAxisAlignment.end**
     * 描述 Description : 將內容放在主軸末端
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               mainAxisAlignment: MainAxisAlignment.end,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/RzPeN84.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               mainAxisAlignment: MainAxisAlignment.end,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/XK89iRz.png =40%x)
  4. **MainAxisAlignment.spaceBetween**
     * 描述 Description : 將內容平均分配在主軸上，第一個內容前和最後一個內容後沒有空格
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               mainAxisAlignment: MainAxisAlignment.spaceBetween,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/Wkr1fkI.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               mainAxisAlignment: MainAxisAlignment.spaceBetween,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/81JMoTx.png =40%x)
  5. **MainAxisAlignment.spaceAround**
     * 描述 Description : 將內容平均分配在主軸上，第一個內容前和最後一個內容後的空格會是內容之間空格的一半
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               mainAxisAlignment: MainAxisAlignment.spaceAround,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/Lio0GnG.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               mainAxisAlignment: MainAxisAlignment.spaceAround,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/gE9DT9S.png =40%x)
  6. **MainAxisAlignment.spaceEvenly**
     * 描述 Description : 將內容平均分配在主軸上，第一個內容前和最後一個內容後的空格等同內容之間空格
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               mainAxisAlignment: MainAxisAlignment.spaceEvenly,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/NhVSX5X.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               mainAxisAlignment: MainAxisAlignment.spaceEvenly,
               children: [
                 Text('1',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('2',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
                 Text('3',style: TextStyle(fontFamily: 'Nunito',fontSize: 30.0)),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/rMnwGGK.png =40%x)
#### b. 建構式參數 Constructor Parameters 'crossAxisAlignment' : [CrossAxisAlignment](https://api.flutter.dev/flutter/rendering/CrossAxisAlignment-class.html)
* 描述 Description : 確認內容在垂直主軸的軸上位置 class
* 常數 Constants : 
  1. **CrossAxisAlignment.start**
     * 描述 Description : 將內容們對準垂直主軸的軸末端
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               crossAxisAlignment: CrossAxisAlignment.start,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/pubQhz0.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               crossAxisAlignment: CrossAxisAlignment.start,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/jIgCSrh.png =40%x)
  2. **CrossAxisAlignment.center**
     * 描述 Description : 將內容們對準垂直主軸的軸中心
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               crossAxisAlignment: CrossAxisAlignment.center,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/KUeZ9N5.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               crossAxisAlignment: CrossAxisAlignment.center,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/xvPbJCH.png =40%x)
  3. **CrossAxisAlignment.end**
     * 描述 Description : 將內容們對準垂直主軸的軸開頭
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               crossAxisAlignment: CrossAxisAlignment.end,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/GPCTHJp.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               crossAxisAlignment: CrossAxisAlignment.end,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/scbWx1e.png =40%x)
  4. **CrossAxisAlignment.stretch**
     * 描述 Description : 將內容們的大小調整到垂直主軸的軸長
     * 舉例示範 Example - Column : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Column(
               crossAxisAlignment: CrossAxisAlignment.stretch,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Column : 
       ![](https://i.imgur.com/P4lO3Ob.png =40%x)
     * 舉例示範 Example - Row : 
     ```java=
     void main() {
       runApp(MaterialApp(
         home: Scaffold(
             backgroundColor: Colors.grey[200],
             appBar: AppBar(
               title: Text('AppBar'),
               centerTitle: true,
               backgroundColor: Color(0xFFFF9000),
             ),
             body: Row(
               crossAxisAlignment: CrossAxisAlignment.stretch,
               children: [
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(10.0),
                     child: Text('1',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(20.0),
                     child: Text('2',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
                 Container(
                     color: Colors.white,
                     padding: EdgeInsets.all(30.0),
                     child: Text('3',
                         style: TextStyle(fontFamily: 'Nunito', fontSize: 30.0))),
               ],
             ),
             floatingActionButton: FloatingActionButton(
               child: Text('Button'),
               onPressed: () {},
               backgroundColor: Color(0xFFFF9000),
             )),
       ));
     }
     ```
     * 結果顯示 Result - Row : 
       ![](https://i.imgur.com/bac40PB.png =40%x)



## L. 分隔線 Divider Widget
### I. [Divider](https://api.flutter.dev/flutter/material/Divider-class.html)
* 描述 Description : 分隔線 Widget
* 建構式 Constructor : 
```
const Divider({
    Key? key,
    double? height,
    double? thickness,
    double? indent,
    double? endIndent,
    Color? color
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 高度 height  ( 分隔線會出現在這高度的中間 )
  2. 厚度 thickness
  3. 顏色 color
  4. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            Text(
              '1',
              style: TextStyle(fontSize: 20.0, fontFamily: 'Nunito'),
            ),
            Divider(
              color: Colors.black,
              height: 30.0,
              thickness: 2.5,
            ),
            Text(
              '2',
              style: TextStyle(fontSize: 20.0, fontFamily: 'Nunito'),
            ),
          ],
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 結果顯示 Result : 
  ![](https://i.imgur.com/PRQNcav.png =40%x)


## M. 大小方塊 SizedBox Widget
### I. [SizedBox](https://api.flutter.dev/flutter/widgets/SizedBox-class.html)
* 描述 Description : 可當作空白方塊，也可以限制內容大小的方塊 Widget
* 建構式 Constructor : 
```
SizedBox({
    Key? key, 
    double? width, 
    double? height, 
    Widget? child
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. 高度 height 
  2. 寬度 width
  3. 內容 child
  4. ...
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(
    home: Scaffold(
        backgroundColor: Colors.grey[200],
        appBar: AppBar(
          title: Text('AppBar'),
          centerTitle: true,
          backgroundColor: Color(0xFFFF9000),
        ),
        body: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            Text(
              '1',
              style: TextStyle(fontSize: 20.0, fontFamily: 'Nunito'),
            ),
            SizedBox(height: 30.0),
            Text(
              '2',
              style: TextStyle(fontSize: 20.0, fontFamily: 'Nunito'),
            ),
          ],
        ),
        floatingActionButton: FloatingActionButton(
          child: Text('Button'),
          onPressed: () {},
          backgroundColor: Color(0xFFFF9000),
        )),
  ));
}
```
* 結果顯示 Result : 
  ![](https://i.imgur.com/ccCnZwY.png =40%x)



## N.自創 Stateless / Stateful Widget (Hot Reload)
### I. [Stateless Widget](https://api.flutter.dev/flutter/widgets/StatelessWidget-class.html)
* 描述 Description : 可自創的 Widget Class, 通常用作介面 => 回傳 Widget 如: Scaffold ...
* 建構式 Constructor ( 可自行增加建構式參數運用 ): 
```
const StatelessWidget({
    Key? key
    ...
})
```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. key
  2. ... ( 可自行增加 )
* 提醒 Reminder : 無法更改 Widget 內容
* 快捷 Shortcut : stless 
* 舉例示範 Example :
```java=
void main() {
  runApp(MaterialApp(home: MyApp(text: 'My First App')));
}

class MyApp extends StatelessWidget {
  final String text;
  MyApp({Key? key, required this.text}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(text),
        centerTitle: true,                  
        backgroundColor: Colors.pink[100],
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {},                   
        child: Text('Button'),
        backgroundColor: Colors.pink[100],
      ),
    );
  }
}
```
* 顯示結果 Result : 
  ![](https://i.imgur.com/KUbzMla.png =40%x)




### II. [Stateful Widget](https://api.flutter.dev/flutter/widgets/StatefulWidget-class.html) 
  * 描述 Description : 可自創的 Widget Class, 通常用作介面 => 回傳 Widget 如: Scaffold ... 
  * 建構式 Constructor ( 可自行增加建構式參數運用 ): 
```
const StatefulWidget({
    Key? key
    ...
})

```
* 要求的建構式參數 Required Constructor Parameters : None
* 其他可加的建構式參數 Other Constructor Parameters : 
  1. key
  2. ... ( 可自行增加 )
* 提醒 Reminder : 經由 setState() => 更改 Widget Class 內容 ( 藉由重跑一次 build Function )
* 快捷 Shortcut : stful
* 補充 Supplement : 
  * Stateful Widget 執行的過程 : 
    initState() => build()
    遇到 setState() => build()
* 舉例示範 Example : 
```java=
void main() {
  runApp(MaterialApp(home: MyApp()));
}

class MyApp extends StatefulWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  int value = 0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('AppBar $value'),
        centerTitle: true,
        backgroundColor: Colors.pink[100],
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          setState(() => value++);
        },
        child: Text('Button'),
        backgroundColor: Colors.pink[100],
      ),
    );
  }
}
```
* 顯示結果 Result : 
  * Before Clicking 
  ![](https://i.imgur.com/cbbgs9t.png =40%x)
  * After Clicking 
  ![](https://i.imgur.com/lKnJn0g.png =40%x)
### 比較 Compare : Stateless Widget vs. Stateful Widget

  * 相同 Same :  需要回傳 Widget Class, 可以 Hot Reload, 可以使用變數
  * 不同 Different: Stateless 不得改變內容, Stateful 可以
  * 特性 Character : **熱重載 Hot Reload**
    * 在DeBug模式下才會執行
    * 不必重新編譯情況下，得以直接觀察到修改後的結果
    * 可以藉由存檔( ctrl + s / cmd + s ) 或 按 hot reload 按鈕執行



> Finished 
> [time=Tue, Sep 7, 2021 11:26 AM][name=楊世宇]