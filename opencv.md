
# 基础

## 1. 图片的读取
```python
import cv2
im=cv2.imread('路径') #读取图片
cv2.imwrite('文件名',im)# 写入图片
im2=cv2.cvtColor(im,cv2.COLOR_BGR2GRAY)#颜色空间转换 此为转换成黑白
cv2.imshow('img',im)# 窗口名为‘img’，展示的图片为im
```
## 2.图片的展示
- 由于opencv是BGR,matplotlib是RGB,直接展示会出错，所以有以下三种方式转换
1. 方式一
```python
import cv2
from matplotlib import pyplot as plt
im=cv2.imread('路径')
b,g,r=cv2.split(im)
im2=cv2.merge([r,g,b])
plt.imshow(im2)
plt.show()
```
2. 方式二
```python
import cv2
from matplotlib import pyplot as plt
im=cv2.imread('路径')
im2=im[...,::-1]
plt.imshow(im2)
plt.show()
```
3. 方式三
```python
import cv2
from matplotlib import pyplot as plt
im=cv2.imread('路径')
im2=cv2.cvtColor(im,cv2.COLOR_BGR2RGB)
plt.imshow(im2)
plt.show()
```

