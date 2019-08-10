## MATLAB的一些常用内置函数

* rand(m,n)
  * 生成均匀分布的伪随机数，分布在(0~1)之间
  
  * m行n列矩阵，可指定精度，如: rand(m,n,'double')
  
  * rand('seed', key) 保证随机生成的矩阵与上次的相同
  
    ```matlab
    rand('seed', 1)
    rand(5,1)
    rand('seed', 1)
    rand(5,1)
    ```
  
    
  
* round()
  
  * 四舍五入传入的数值
  
* ceil()

  * 向+∞取整
  * 如ceil(5.3) = 6

* floor()

  * 向-∞取整

* fecal()

  * 计算函数的函数命令

    ```matlab
    x=[1.3,2.4,4.5]
    z = fecal('round', x)
    % z = 1 2 5
    ```

    

* size()
  * 返回对应矩阵的行列
  * size(A): 返回对应矩阵A的行列值(行 列)
  * size(A. 1): 返回对应矩阵的行
  * size(A, 2): 返回对应矩阵的列
  
* power()
  * 幂指数
  * power(a, b)  a 为底  b为次数
  
* linspace(start, end, num)

  * 生成等差数列
  * start 开始
  * end   结束
  * num  元素个数

* logspace(start, end, num)

  * 生成等比数列，10
  * start 开始元素 10^stat
  * end   结束元素 10^end
  * num  元素数目

* inv(A)

  * 求A的逆矩阵
  * A必须为方阵

* AX=B

  * X = A\B(A左除B)

* XA=B

  * X = A/B(A右除B)

## 线性代数

* det()

  * 求矩阵的值(A为方阵)

* rank()

  * 求矩阵的秩

* pinv()

  * 求矩阵的伪逆

* inv()

  * 求矩阵的逆

* trace()

  * 求矩阵的迹(对角线的元素和)

* orth()

  * 求矩阵的正交基

* subspace(A,B)

  * 求矩阵A、B划分列的夹角

* null()

  * 求矩阵的零空间的正交基

  

