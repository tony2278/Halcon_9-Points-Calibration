binary_threshold (ImageScaled, Region, 'max_separability', 'dark', UsedThreshold)  *二值化提取黑或提取白
创建模板的相关算子
第二步：保持9个圆点不动，使用机械手的作业工具对准9个圆的圆心位置，并保存好机械手坐标。
然后把9个点的坐标按照圆的序号在生成一个一维数组变量。
（一定要对好序号，就是第一步中排序后的序号和数组元素一一对应）

第三步：使用图像行列的圆心和机械手的一维数组变量，生成一个矩阵关系。
vector_to_hom_mat2d (Column, Row, X, Y, HomMat2D)   *HomMat2D就是我们要的这个矩阵。
write_tuple (HomMat2D, 'D:/1012.tup')   *保存矩阵使用
read_tuple ('D:/1012.tup', HomMat2D1)    *读取矩阵使用

第四步：有矩阵了，就直接使用矩阵即可。（识别）使用相机去识别一个或多个新的物体，并得到行列中心，如何使用了镜像mirror_image，这里也必须使用镜像关系，就是图像要保持一致性。

affine_trans_point_2d (HomMat2D, Column1, Row1, Rx, Ry)    *矩阵转换，把CR坐标转换为RxRy





1 halcon中9点标定
   https://blog.csdn.net/weixin_45320837/article/details/99615539
2 halcon中9点标定
   https://blog.csdn.net/elie_yang/article/details/106315448


使用halcon结合机械XY轴对相机进行9点标定
   https://www.it610.com/article/1282838488902811648.htm



