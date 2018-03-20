# API说明
# 绘制路径
  * beginPath() 新建一条路径
  * closePath() 闭合一条路径
  * stroke() 绘制出通过 moveTo() 和 lineTo() 方法定义的路径
  * fill() 填充路径内容，生成实心图形
  * lineTo() 绘制直线
  * 路径填充fill()路径自动闭合，stroke()不会闭合路径，需要closePath()

# 绘制圆弧及贝塞尔曲线
  * arc()、arcTo() 绘制圆弧
  * quadraticCurveTo(cp1x, cp1y, x, y) 绘制二次贝塞尔曲线，cp1x,cp1y为一个控制点，x,y为结束点
  * bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y) 绘制三次贝塞尔曲线，cp1x,cp1y为控制点一，cp2x,cp2y为控制点二，x,y为结束点

# 绘制矩形
  * rect(x, y, width, height) 绘制一个左上角坐标为（x,y），宽高为width以及height的矩形。
  * clearRect(x, y, width, height)   坐标，宽高

# Path2D对象 声明路径
  * Path2D.addPath() 添加了一条路径到当前路径（可能添加了一个变换矩阵）。
  * Path2D.closePath()
  * Path2D.moveTo()
  * Path2D.lineTo()
  * Path2D.quadraticCurveTo()
  * Path2D.bezierCurveTo()
  * Path2D.arc()
  * Path2D.ellipse() 添加一条椭圆路径
  * Path2D.rect()

# 色彩 Colors
  * fillStyle 填充颜色
  * strokeStyle 线框颜色
  * globalAlpha 设置透明度,0-1.0，默认1.0

  * 设置线的样式
    * lineWidth 线宽

    * lineCap 设置线条末端样式
      * butt：默认。向线条的每个末端添加平直的边缘。
      * round	向线条的每个末端添加圆形线帽。
      * square	向线条的每个末端添加正方形线帽。

    * lineJoin 线条拐角
      * miter	默认。创建尖角。
      * bevel	创建斜角。
      * round	创建圆角。
     
    * miterLimit 限制当两条线相交时交接处最大长度
    * getLineDash() 返回一个包含当前虚线样式，长度为非负偶数的数组
    * setLineDash(segments) 设置当前虚线样式。
        * eg:segments:[x,y]，x:虚线宽度  y:虚线间距离
    * lineDashOffset 设置虚线样式的起始偏移量
     
# 渐变 Gradients
  * createLinearGradient(x1, y1, x2, y2) 表示渐变的起点 (x1,y1) 与终点 (x2,y2)。返回一个gradient。
  * createRadialGradient(x1, y1, r1, x2, y2, r2) 前三个定义一个以 (x1,y1) 为原点，半径为 r1 的圆，后三个参数则定义另一个以 (x2,y2) 为原点，半径为 r2 的圆
  * gradient.addColorStop(position, color) position 参数必须是一个 0.0 与 1.0 之间的数值，表示渐变中颜色所在的相对位置；color 参数必须是一个有效的 CSS 颜色值。

# 图案样式 Patterns
  * createPattern(image, type) Image 可以是一个 Image 对象的引用，或者另一个 canvas 对象。
                                Type 必须是下面的字符串值之一：repeat，repeat-x，repeat-y 和 no-repeat。

# 阴影 Shadows
  * shadowOffsetX = float，shadowOffsetY = float   设定阴影在 X 和 Y 轴的延伸距离，它们是不受变换矩阵所影响的。正值则表示会往下或右延伸，它们默认都为 0。
  * shadowBlur = float  设定阴影的模糊程度，其数值并不跟像素数量挂钩，也不受变换矩阵的影响，默认为 0。
  * shadowColor = color   设定阴影颜色效果，默认是全透明的黑色。
   
# Canvas 填充规则（当我们用到 fill时）
  * 'nonzero'  非零绕组规则，默认。
  * 'evenodd'  单双数圈规则。

# canvas 点击区域（某些浏览器尚未实现）
  * CanvasRenderingContext2D.addHitRegion() 在canvas上添加一个点击区域。
  * CanvasRenderingContext2D.removeHitRegion() 从canvas上移除指定id的点击区域。
  * CanvasRenderingContext2D.clearHitRegions()  移除canvas上的所有点击区域。
  * 焦点圈
    * CanvasRenderingContext2D.drawFocusIfNeeded() 如果给定的元素获得了焦点，这个方法会沿着在当前的路径画个焦点圈。
    * CanvasRenderingContext2D.scrollPathIntoView() 把当前的路径或者一个给定的路径滚动到显示区域内。

# 绘制文本
  * fillText(text, x, y [, maxWidth])  在指定的(x,y)位置填充指定的文本，绘制的最大宽度是可选的。
  * strokeText(text, x, y [, maxWidth])  在指定的(x,y)位置绘制文**本边框**，绘制的最大宽度是可选的。
  * font和CSS font 属性相同的语法. 默认的字体是 10px sans-serif。
  * textAlign  可选的值包括：start, end, left, right or center. 默认值是 start。
  * textBaseline    基线对齐选项. 可选的值包括：top, hanging, middle, alphabetic, ideographic, bottom。默认值是 alphabetic。
  * direction   文本方向。可能的值包括：ltr, rtl, inherit。默认值是 inherit。
  * measureText()  文本测量，返回一个 TextMetrics对象的宽度、所在像素，这些体现文本特性的属性。

# 使用图片
  * 图片的源：
    * HTMLImageElement  这些图片是由Image()函数构造出来的，或者任何的<img>元素。
    * HTMLVideoElement  用一个HTML的 <video>元素作为你的图片源，可以从视频中抓取当前帧作为一个图像。
    * HTMLCanvasElement  可以使用另一个 <canvas> 元素作为你的图片源。
    * ImageBitmap  一个高性能的位图，可以低延迟地绘制，它可以从上述的所有源以及其它几种源中生成。
    * 这些源统一由 CanvasImageSource类型来引用。
    * drawImage(image, x, y)  绘制图片，image 是 image 或者 canvas 对象，x 和 y 是其在目标 canvas 里的起始坐标。
    * drawImage(image, x, y, width, height)  width 和 height，这两个参数用来控制 当向canvas画入时应该缩放的大小。
    * drawImage(image, sx, sy, sWidth, sHeight, dx, dy, dWidth, dHeight)
       其它8个参数，前4个是定义图像源的切片位置和大小，后4个则是定义切片的目标显示位置和大小。
    *  mozImageSmoothingEnabled   值为 false 时，图像不会平滑地缩放。默认是 true 。
    * globalCompositeOperation   改变层级关系

    * ImageData 
      * createImageData(width, height)
      * getImageData(left, top, width, height)
      * putImageData(myImageData, dx, dy) 对场景进行像素数据的写入。
      
      * 保存图片
        * canvas.toDataURL('image/png') 默认设定。创建一个PNG图片。
        * canvas.toDataURL('image/jpeg', quality)  创建一个JPG图片。你可以有选择地提供从0到1的品质量，1表示最好品质，0基本不被辨析但有比较小的文件大小。
        * canvas.toBlob(callback, type, encoderOptions)  这个创建了一个在画布中的代表图片的Blob对像。
       
# 变形
  * save() restore()  save 和 restore 方法是用来保存和恢复 canvas 状态的，都没有参数。当save()方法被调用后，当前的状态就被推送到栈中保存。调用 restore 方法，上一个保存的状态就从栈中弹出，所有设定都恢复。
  * transform(m11, m12, m21, m22, dx, dy)  将当前的变形矩阵乘上一个基于自身参数的矩阵。
  * resetTransform()  重置当前变形为单位矩阵。
        等于 ctx.setTransform(1, 0, 0, 1, 0, 0)

  * 移动
    * translate(x, y)

  * 旋转
    * rotate(angle)

  * 缩放
    * scale(x, y)  值比 1.0 小表示缩小，比 1.0 大则表示放大。

  * 裁切路径
    * clip()

  * 动画
      

