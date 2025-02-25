## 万能阴影布局，定制化你要的阴影。 ShadowLayout 2.0震撼上线（需要阴影地方，被它嵌套即可享受阴影，阴影可定制化，效果赶超CardView）
* 支持定制化阴影
* 支持随意更改阴影颜色值
* 支持x,y轴阴影偏移 
* 可随意更改阴影扩散区域 
* 支持阴影圆角属性
* 支持单边或多边不显示阴影
#### 2.0更新功能（最近发现有人直接拿去当自己项目，发布博客和github。我想说尊重下辛苦蜜蜂的劳动成果。转载请说明出处）
* 支持ShadowLayout背景填充颜色，圆角属性随阴影圆角改变
* 支持动态修改ShadowLayout各种属性，及内部代码优化  

### [最近有人反应内存情况，请看分析](https://juejin.im/post/5d4c1392f265da03bc126584#heading-12)

## 效果展示（截图分辨率模糊，真机运行效果赶超CardView）
|基础功能展示|各属性展示|随意更改颜色|
|:---:|:---:|:---:|
|![](https://github.com/lihangleo2/ShadowLayout/blob/master/main.jpg)|![](https://github.com/lihangleo2/ShadowLayout/blob/master/first_show.gif)|![](https://github.com/lihangleo2/ShadowLayout/blob/master/other_show.gif)

## 添加依赖

 - 项目build.gradle添加如下
   ```java
   allprojects {
		repositories {
			maven { url 'https://jitpack.io' }
		}
	}
   ```
 - app build.gradle添加如下
    ```java
   dependencies {
	        implementation 'com.github.lihangleo2:ShadowLayout:2.0.1'
	}
   ```
   
## 使用
```xml
      <com.lihang.ShadowLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:hl_cornerRadius="18dp"
        app:hl_dx="0dp"
        app:hl_dy="0dp"
        app:hl_leftShow="false"
        app:hl_shadowColor="#2aff0000"
	app:hl_shadowBackColor="#fff"
        app:hl_shadowLimit="5dp">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="36dp"
            android:paddingLeft="10dp"
            android:paddingRight="10dp"
            android:text="定制化你的阴影"
            android:textColor="#000" />

    </com.lihang.ShadowLayout>
```

 # 自定义属性
 ####  圆角属性
 - app:hl_cornerRadius="18dp"  阴影圆角属性（同时如果设置了背景填充色也是背景圆角）
  
 #### 阴影扩散程度
 - app:hl_shadowLimit="5dp"  阴影的扩散区域
  
 #### 阴影布局背景颜色值
 - app:hl_shadowBackColor="#fff" 阴影布局背景填充色，圆角属性即是阴影圆角
 
 ####  阴影的颜色（注意必须有透明度）
 - app:hl_shadowColor="#2a000000"  阴影的颜色可以随便改变,透明度的改变可以改变阴影的清晰程度
```java
	//这里是setShadowLayer源码的描述，去掉了部分代码便于理解
	/*
     * The alpha of the shadow will be the paint's alpha if the shadow color is
     * opaque, or the alpha from the shadow color if not.
     */
    public void setShadowLayer(float radius, float dx, float dy, int shadowColor) {
      mShadowLayerRadius = radius;
      mShadowLayerDx = dx;
      mShadowLayerDy = dy;
      mShadowLayerColor = shadowColor;
      nSetShadowLayer(mNativePaint, radius, dx, dy, shadowColor);
    }
```

 #### x轴的偏移量
 - app:hl_dx="0dp"    也可以理解为左右偏移量
 
 #### y轴的偏移量
 - app:hl_dy="0dp"    也可以理解为上下的偏移量

 #### 阴影的4边可见不可见（与偏移量无关）
 - app:hl_leftShow="false"    左边的阴影不可见，其他3边保持不变
 


