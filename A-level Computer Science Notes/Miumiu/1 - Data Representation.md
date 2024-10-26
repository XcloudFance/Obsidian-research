KiB

KB - 1000 - 10 ^ 3 -  **base 10** number
B**i**nary - 1024 - 2 ^ 10 - **base 2** number

1 Bit  相当于就是binary number的一位

> [!NOTE] Presentation
> 11011 - 5 bits

**1 Byte = 8 bits**
1 KiB = 1024 Bytes
1 MiB = 1024 KiB
1 GiB  = 1024 MiB

1 KB = 1000 Bytes
1 MB = 1000 KB
1 GB = 1000 MB



## Image Representation
---

###  Bitmap 位图
- Consists of **pixels**, of each represents a specific color by binary number.
	- pixel is the smallest unit in bitmap to represent a single color
	- more pixels mean **larger file size**, but **better quality**
- When zooming in, the bitmap image get **pixelated**

- Resolution 分辨率 - pixels的个数
	- 3840 * 2180 images - 长3840pixels, 宽是2180pixels
	- **Color Depth** - 色深 - How many number of bits taken by each color in pixels
		- 普通图片是由RGB组成的，每个颜色通常8个bit
		- Color Depth: 24 bits
		- Each pixels needs to take up 24 bits to store.
		- 
	- File Size Calculation
		- Number of pixels * Color Depth
		- 3840 * 2180 * 3 Bytes = 
	
- Bitmap stores its **metadata** in **file header** (the beginning of the data of the file)
	- metadata: basic information about this image
		- Author
		- Color Depth
		- Pixels
		- Dates of taken
		- location
	- 

	- RGB - Red Green Blue - 255

### Vectoric 矢量图
- Storing **drawing lists** and **drawing objects**
	- Drawing Lists 
- When zooming in, no quality is lost - 和bitmap相反
- When resize the image, need to re-calculate each objects
