#canvas常用API
>画布特点:绘制上的元素不会改变
>画布的编程模式
1：清除
2：描绘
##形状
>矩形
* ctx.fillRect(x,y,width,height)      填充矩形
* ctx.strokeRect(x,y,width,height)    框线矩形
>圆
* ctx.arc(x,y,r,start,end)           圆(开始结束角度)
>线
* ctx.beginPath       开始一个路径
* ctx.moveTo          移动画笔到某点
* ctx.lineTo          让路径中`拥有`(并不会直接绘制)一条道某点的线
* ctx.rect(x,y,width,height)          让路径中`拥有`(并不会直接绘制)一个矩形
* ctx.fill            填充当前路劲
* ctx.stroke()        描边当前路径
* ctx.closePath       结束一个路劲
>曲线
* ctx.quadraticCurveTo(cp1x,cp1y,x,y)                   二次贝塞尔
* ctx.bezierCurveTo(cp1x,cp1y,cp2x,cp2y,x,y)            三次贝塞尔
>清除画布
* ctx.clearRect(0，0，0，0)    清楚一个矩形区域
* 重新设置宽高
##样式
>
* ctx.fillStyle = '';
* ctx.storkeStyle = '';
* globalAlpha = 0.2;  全局透明度
* lineWidth = value
  设置线条宽度。
* lineCap = type
  设置线条末端样式。一：butt，round 和 square(端点处加上了等宽且高度为一半线宽的方块)。默认是 butt
* lineJoin = type
  设定线条与线条间接合处的样式。
* miterLimit = value
  限制当两条线相交时交接处最大长度；所谓交接处长度（斜接长度）是指线条交接处内角顶点到外角顶点的长度。
* getLineDash()
  返回一个包含当前虚线样式，长度为非负偶数的数组。
* setLineDash(segments)
  设置当前虚线样式。
  lineDashOffset = value
  设置虚线样式的起始偏移量
* createLinearGradient(x1, y1, x2, y2)
createLinearGradient 方法接受 4 个参数，表示渐变的起点 (x1,y1) 与终点 (x2,y2)。
* createRadialGradient(x1, y1, r1, x2, y2, r2)
createRadialGradient 方法接受 6 个参数，前三个定义一个以 (x1,y1) 为原点，半径为 r1 的圆，后三个参数则定义另一个以 (x2,y2) 为原点，半径为 r2 的圆。
* gradient.addColorStop(position, color)
addColorStop 方法接受 2 个参数，position 参数必须是一个 0.0 与 1.0 之间的数值，表示渐变中颜色所在的相对位置。例如，0.5 表示颜色会出现在正中间。color 参数必须是一个有效的 CSS 颜色值（如 #FFF， rgba(0,0,0,1)，等等）。
* shadowOffsetX = float
shadowOffsetX 和 shadowOffsetY 用来设定阴影在 X 和 Y 轴的延伸距离，它们是不受变换矩阵所影响的。负值表示阴影会往上或左延伸，正值则表示会往下或右延伸，它们默认都为 0。
* shadowOffsetY = float
shadowOffsetX 和 shadowOffsetY 用来设定阴影在 X 和 Y 轴的延伸距离，它们是不受变换矩阵所影响的。负值表示阴影会往上或左延伸，正值则表示会往下或右延伸，它们默认都为 0。
* shadowBlur = float
shadowBlur 用于设定阴影的模糊程度，其数值并不跟像素数量挂钩，也不受变换矩阵的影响，默认为 0。
*　shadowColor = color
shadowColor 是标准的 CSS 颜色值，用于设定阴影颜色效果，默认是全透明的黑色。
*　fillText(text, x, y [, maxWidth])
在指定的(x,y)位置填充指定的文本，绘制的最大宽度是可选的.
* strokeText(text, x, y [, maxWidth])
在指定的(x,y)位置绘制文本边框，绘制的最大宽度是可选的.
* font = value
当前我们用来绘制文本的样式. 这个字符串使用和 CSS font 属性相同的语法. 默认的字体是 10px sans-serif。
* textAlign = value
文本对齐选项. 可选的值包括：start, end, left, right or center. 默认值是 start。
* textBaseline = value
基线对齐选项. 可选的值包括：top, hanging, middle, alphabetic, ideographic, bottom。默认值是 alphabetic。
* direction = value
文本方向。可能的值包括：ltr, rtl, inherit。默认值是 inherit。
##旋转 变形
>画布(挪动)
* ctx.save()           保存画布初始位置(只保存画布状态包含画笔（状态） 不保存任何图像)
* ctx.translate(x,y)   移动画布    
* ctx.restore()        恢复到原来位置
* ctx.rotate(弧度)         画布旋转
* ctx.scale()
* drawImage(image, x, y, width, height)
这个方法多了2个参数：width 和 height，这两个参数用来控制 当像canvas画入时应该缩放的大小
* drawImage(image, sx, sy, sWidth, sHeight, dx, dy, dWidth, dHeight)
第一个参数和其它的是相同的，都是一个图像或者另一个 canvas 的引用。其它8个参数最好是参照右边的图解，前4个是定义图像源的切片位置和大小，后4个则是定义切片的目标显示位置和大小。

##画笔方法  
arcTo
arcTobeginPath
beginPathbezierCurveTo
bezierCurveTocanvas
get canvas
clearRect
clearRectclip
clipclosePath
closePathconstructor
CanvasRenderingContext2DcreateImageData
createImageDatacreateLinearGradient
createLinearGradientcreatePattern
createPatterncreateRadialGradient
createRadialGradientdrawFocusIfNeeded
drawFocusIfNeededdrawImage
drawImageellipse
ellipsefill
fillfillRect
fillRectfillStyle
get fillStyle
set fillStyle
fillText
fillTextfont
get font
set font
getContextAttributes
getContextAttributesgetImageData
getImageDatagetLineDash
getLineDashglobalAlpha
get globalAlpha
set globalAlpha
globalCompositeOperation
get globalCompositeOperation
set globalCompositeOperation
imageSmoothingEnabled
get imageSmoothingEnabled
set imageSmoothingEnabled
isPointInPath
isPointInPathisPointInStroke
isPointInStrokelineCap
get lineCap
set lineCap
lineDashOffset
get lineDashOffset
set lineDashOffset
lineJoin
get lineJoin
set lineJoin
lineTo
lineTolineWidth
get lineWidth
set lineWidth
measureText
measureTextmiterLimit
get miterLimit
set miterLimit
moveTo
moveToputImageData
putImageDataquadraticCurveTo
quadraticCurveTorect
rectresetTransform
resetTransformrestore
restorerotate
rotatesave
savescale
scalesetLineDash
setLineDashsetTransform
setTransformshadowBlur
get shadowBlur
set shadowBlur
shadowColor
get shadowColor
set shadowColor
shadowOffsetX
get shadowOffsetX
set shadowOffsetX
shadowOffsetY
get shadowOffsetY
set shadowOffsetY
stroke
strokestrokeRect
strokeRectstrokeStyle
get strokeStyle
set strokeStyle
strokeText
strokeTexttextAlign
get textAlign
set textAlign
textBaseline
get textBaseline
set textBaseline
transform
transformtranslate
translatewebkitImageSmoothingEnabled
get webkitImageSmoothingEnabled
set webkitImageSmoothingEnabled
