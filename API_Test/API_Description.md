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
   * 