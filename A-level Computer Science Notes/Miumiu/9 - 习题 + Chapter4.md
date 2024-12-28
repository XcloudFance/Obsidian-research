
Each pixel is arranged / stored in the file sequentially.
每个像素在文件里面都是按顺序一个接着一个存储的

## RLE - Run-length Encoding

RLE是一种无损压缩，压缩的算法已经写在名字里面了
run + length

aaaaaaabbbbbbc   <- 压缩前
a7b6c1                     <- 压缩后
要怎么解压？
aaaaaaabbbbbbc 把abc的次数放回来就是解压了

abcdefg <- 压缩前
a1b1c1d1e1f1g1   <- 压缩后




- lossless compression
	- 压缩后的文件是可以恢复成压缩前的样子
	- The file can be restored in the way before it gets compressed
- A -> A-  -> A
- 什么时候用无损压缩？
	- 文档类的
	- 重要信息类的

- lossy compression
	- 音频，图像，视频这种multimedia 的用有损压缩
	- 有损压缩对图像的修改是永久的，不可恢复不可逆转
	- 因为这种多媒体类的文件哪怕损耗一点质量(quality)也可以运行或者完整的被理解




## Vector Graphic
- A vector graphic consists of drawing objects
- Drawing Objects: mathematically defined constructs, such as triangle, line, 