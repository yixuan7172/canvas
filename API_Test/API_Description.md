# API说明
  * 绘制路径
    * beginPath() 新建一条路径
    * closePath() 闭合一条路径
    * stroke() 通过线条来绘制图形轮廓
    * fill() 填充路径内容，生成实心图形
    * lineTo() 绘制直线
    * 路径填充fill()路径自动闭合，stroke()不会闭合路径，需要closePath()

 * 绘制圆弧及贝塞尔曲线  
    * arc()、arcTo() 绘制圆弧
    * quadraticCurveTo(cp1x, cp1y, x, y) 绘制二次贝塞尔曲线，cp1x,cp1y为一个控制点，x,y为结束点
    * bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y) 绘制三次贝塞尔曲线，cp1x,cp1y为控制点一，cp2x,cp2y为控制点二，x,y为结束点

 * 绘制矩形
   * rect(x, y, width, height) 绘制一个左上角坐标为（x,y），宽高为width以及height的矩形。

 * Path2D对象 声明路径
   * Path2D.addPath() 添加了一条路径到当前路径（可能添加了一个变换矩阵）。
   * Path2D.closePath() 
   * Path2D.moveTo()
   * Path2D.lineTo()
   * Path2D.quadraticCurveTo()
   * Path2D.bezierCurveTo()
   * Path2D.arc()
   * Path2D.ellipse() 添加一条椭圆路径
   * Path2D.rect()

 * 色彩 Colors
   * fillStyle
   * strokeStyle
   * globalAlpha 设置透明度

   * 设置线的样式
     * lineWidth 
     * lineCap 设置线条末端样式
     * lineJoin 设定线条与线条间接合处的样式
     * miterLimit 限制当两条线相交时交接处最大长度
     * getLineDash() 返回一个包含当前虚线样式，长度为非负偶数的数组
     * setLineDash(segments) 设置当前虚线样式。
        * eg:segments:[x,y]，x:虚线宽度  y:虚线间距离
     * lineDashOffset 设置虚线样式的起始偏移量
     
 * 渐变 Gradients
   * createLinearGradient(x1, y1, x2, y2) 表示渐变的起点 (x1,y1) 与终点 (x2,y2)。返回一个gradient。
   * createRadialGradient(x1, y1, r1, x2, y2, r2) 前三个定义一个以 (x1,y1) 为原点，半径为 r1 的圆，后三个参数则定义另一个以 (x2,y2) 为原点，半径为 r2 的圆
   * gradient.addColorStop(position, color) position 参数必须是一个 0.0 与 1.0 之间的数值，表示渐变中颜色所在的相对位置；color 参数必须是一个有效的 CSS 颜色值。
   