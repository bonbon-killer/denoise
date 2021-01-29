# denoise
去噪的方法很多，其中小波去噪、自适应去噪、卡尔曼滤波器都有不同的特点。白噪声因为其频谱范围宽，传统的滤波器无法达到较好的滤波目的。
## 小波去噪
  小波去噪的经典方法有：阈值法，小波分解法，小波包分解法
  
  连续小波变换得到的系数是时间和频率，根据小波系数可以画出时频图
  （图片已给出）
  
### 阈值法去噪

原理：经过正交小波变换小波变换后的小波系数中，能量集中在少数小波系数中，也即幅值比较大的小波系数绝大多数是有用信号，而幅值较小的一般是噪声；寻找到一个合适的阈值，将小于阈值的小波系数进行相应处理，然后根据处理后的小波系数还原出有用信号

步骤：

    正交小波变换，选取一个正交小波和分解层数N
    对测量信号的每一层高频系数通过阈值函数处理，低频系数不处理
    对处理后的小波系数进行重构
    
软阈值函数：会丢掉信号的一些特征
硬阈值函数：会产生突变

效果见图

### 小波分解

原理：多尺度小波分解相当于一个高通滤波器和若干个带通滤波器，将每一级的低频系数继续分解；如果将噪声对应的系数清除，或者将信号对应的系数挑出来进行重构，就可以得到去噪后的信号

效果见图

ps:综合考虑小波分解的分辨率以及信号频率等因素，选取合适的分解层数和采样率可以更好地还原信号

### 小波分解重构与傅里叶变换去噪结合


