# Cloud-Enabled Privacy-Preserving Truth Discovery in Crowd Sensing Systems

<p class="icon star" markdown="1">隐私保护真值发现（Privacy-preserving Truth Discovery，PPTD)框架：使用同态密码系统（ homomorphic cryptosystem）的阈值Paillier加密对用户的加密数据进行加权聚合。可以准确地收集感官数据，同时保护用户观察和用户可靠性不被披露。<br/>MapReduce框架并行化扩展PPTD，以便在处理大规模人群感知数据 时并行进行真相发现过程。</p>

## 真值发现方法的共同原则

如果特定用户提供的数据更接近聚合结果，他将有更高的权重。

如果特定用户有更高的权重，特定用户的数据将在聚合过程中计算更多。



## PPTD框架的优点

它可以在保护用户数据的隐私的同时，准确地计算出所有汇总的结果，同时，不向任何一方披露权重信息。

## PPTD的相关定义

- 两种不同类型的人群感知方：
  - 用户（ *users*）：人群参与者，自愿或为了财政奖励而使用移动设备执行感知任务。
  - 云服务器（*cloud server* ）：收集用户数据和进行数据聚合的平台。
- 对象（*objects*）：表示云服务器分配的实体或问题。
- 观察值（*observation values*）：表示人群用户提供的感官读数或答案。
- 基本真值（*ground truth* ）：每个任务或问题的真实结果或答案。

## 真值发现

### 真值发现方法的共同过程：

1. 对基本真值进行随机猜测
2. 迭代地进行权重更新和真值更新，直到收敛

### 权重更新

- 基本思想：如果用户提供的数据接近于估计的基本真值，则用户权重被分配一个较高值。

- 平方距离函数d(·)：

  - 连续数据（ continuous data）：
    $$
    d(x_m^{k},x^*_m)=\frac{(x^k_m-x^*_m)^2}{std_m}
    $$

  - 分类数据（ categorical data）：
    $$
    d(x_m^{k},x^*_m)=(x^k_m-x^*_m)^T(x^k_m-x^*_m)
    $$
    其中真值向量为x_m^*，观察向量为
    $$
    x^k_m=(0,...,1,...0)^T
    $$

- 本论文采用CRH的权重计算函数作为测量用户观测值与基本真值之间差距的单调递减函数：

$$
w_k=log(\frac{\sum_{k^{'}=1}^{K}{\sum_{m=1}^{M}d(x_m^{k^{'}},x^*_m)}}{\sum_{m=1}^{M}d(x_m^{k},x^*_m)})
$$

### 真值更新

基本真值：
$$
x^*_m\leftarrow\frac{\sum_{k=1}^{K}{w_k.x^k_m}}{\sum_{k=1}^{K}w_k}
$$
对于连续数据：表示估计的基本真值。

对于分类数据：一个概率向量，其中每个元素表示特定的选择的概率。

## 加密工具

### 同态密码方案（ *Homomorphic Cryptographic Scheme*）

加法同态非对称密码系统（ additive homomorphic asymmetric cryptosystem）

### 阈值*Paillier*加密系统（ *Threshold Paillier Cryptosystem*）

既满足加法同态属性也满足阈值密码系统。

公钥pk=(g,n)加密明文：
$$
c=E_{pk}(m)=g^mr^nmod n^2
$$
同态性质：
$$
E_{pk}(m_1+m_2)=E_{pk}(m_1).E_{pk}(m_2)=g^{m_1+m_2}(r_1r_2)^nmod n^2
$$

$$
E_{pk}(a.m_1)=E_{pk}(m_1)^a=g^{am_1}r_1^{an}mod n^2
$$

私钥ski计算c的部分解密ci:
$$
c_i=c^{2\Delta sk_i}
$$

$$
\Delta=p!
$$

> [A generalisation, a simpli.cation and some applications of paillier’s probabilistic public-key system](https://link.springer.com/content/pdf/10.1007%2F3-540-44586-2_9.pdf)
> $$
> c^{'}=\prod_{i\epsilon s}{c_i^{2\lambda _{0,i}^S}\space mod\space n^{s+1}}\space where\space  \lambda _{0,i}^S=\Delta\prod_{i^{'}\epsilon{ s\backslash i}}\frac{-i}{i-i^{'}}\epsilon Z
> $$
>
> $$
> c^{'}=c^{4\Delta f(0)}=c^{{4\Delta}^2 d}=(1+n)^{{4\Delta}^2 M}
> $$
>
> M即为所求明文





## PPTD(privacy-preserving truth discovery)

云服务器分配对象后，PPTD参与方迭代执行：

1. 安全的权重更新（**Secure Weight Update**）
2. 安全的真值估计（**Secure Truth Estimation**）

### 安全和协议（*Secure Sum Protocol*）

目的：云服务器需要计算用户数据的总和，以更新用户的权重和估计基本真相，同时不泄露任何用户数据。

<img src="https://gitee.com/Jonesyl/pic-bed/raw/master/img/20210719222618.png" alt="Protocol1" style="zoom:80%;" />

### 安全权重更新（*Secure Weight Update*）

加密权重更新公式：
$$
E_{pk}(\widetilde w_k)=E_pk(\lfloor L.(log(\sum_{k^{'}=1}^KDist_{k^{'}})-log(Dist_k))\rfloor)
$$
更新步骤（过程如下图）：

![Figure2](https://gitee.com/Jonesyl/pic-bed/raw/master/img/20210719222621.png)

1. **云服务器发送估计的基本真值给用户k**

   - 首次迭代：随机初始化
   - 上次迭代得到的估计值

   **用户计算Dist_k和log(Dist_k)并加密。**

2. *用户k将对象m的观察值加密并发送给云服务器S

3. *云服务器基于安全和协议计算sum_x和x_m，将x_m发送给用户

4. *用户k计算d^k_m并加密后发送给服务器端

5. *服务器接收到所有d^k_m后计算sum_d，进而求得std_m

6. **用户提交加密的Dist_k和log(Dist_k)到云服务器，云服务器基于安全和协议计算sum_D和log(sum_D)，根据下面公式更新用户k的加密权重：**
   $$
   E_{pk}(\widetilde w_k)=E_pk(\widetilde {log\space sum_D}).E_pk(\widetilde {log\space Dist_k})^{-1}
   $$

其中2~5针对连续数据，用于计算标准差std_m，只在过程中执行一次

### 安全真值估计（*Secure Truth Estimation*）

更新步骤（如下图）：

![Figure3](https://gitee.com/Jonesyl/pic-bed/raw/master/img/20210719222638.png)

1. 云服务器将加密权重发送给用户，用户根据加密权重计算密文下的加权观察值：

   - 连续数据：
     $$
     E_{pk}(\widetilde w_k.\widetilde x_m^k)=E_{pk}(\widetilde w_k)^{\widetilde x_m^k}
     $$
     
   - 分类数据：
     $$
     E_{pk}(\widetilde w_k.\widetilde x_m^k(i))=\begin{cases}E_{pk}(0),if\space x_m^k(i)=0\\E_{pk}(\widetilde w_k).E_{pk}(0),if\space x_m^k(i)=1\end{cases}
     $$

   <p class="icon question" markdown="1">
   E_pk(w_k).E_pk(0)=E_pk(w_k+0) 乘E_pk(0)的目的：虽然数值没有区别，但更新密文形式，防止推测出一些信息。
   </p>

2. 用户将加密加权数据提交给云服务器。服务器计算基本真值。

   - 分子（安全和协议）
     - 连续数据：计算加权总和，再除以L^2得到近似值。
     - 分类数据：分别计算向量中的每个元素的近似值。
   - 分母（安全和协议）：云服务器在权重更新阶段存储了加密权重。

   <p class="icon notice" markdown="1">本步骤中对分类数据所估计的基本真相是概率值，用于在下一次迭代中更新用户权重。对象m的最终估值应该是在最后一次迭代中得到向量的最大概率的选择。</p>

### PPTD协议

<img src="https://gitee.com/Jonesyl/pic-bed/raw/master/img/20210719222751.png" alt="Protocol2" style="zoom:80%;" />

## 并行PPTD

- 分布式权值更新：加密权重更新结果存储于文件。

- 并行真值估计：

  ​	使用MapReduce框架对真值估计过程并行扩展，包含两个主要函数：

  1. Map函数，映射过程，处理输入值以生成一组中间键/值对。
  2. Reduce函数，合并与同意中间键相关的中间值。

<img src="https://gitee.com/Jonesyl/pic-bed/raw/master/img/20210719222800.png" alt="Algorithm2and3" style="zoom:80%;" />

## 隐私性分析

- 框架场景假设：所有参与方是半诚实的，没有共谋。
- PPTD的隐私性目标：
  1. 保护用户的观察值不被泄露（其他用户和云服务器）
  2. 用户权重不被任何一方获取

## 其他讨论

- 利用L舍入到整数带来的数值误差

- 值丢失，即不是所有对象都被所有人群用户观察到
- 感知任务发布后无法及时响应的问题
- 修改为用户权重只有用户自己知道的框架

## 连续数据实验评估

众包室内平面图施工系统实验：评价指标包括绝对误差平均值（MAE）和均方误差（RMSE）

- 准确性

  1. L参数（10^10）：随着L的增大，原始值的小数位数字丢失减少，真值和权重相对误差减小。
  2. 用户数量：估计误差随着用户数目增加而减少。

- 收敛性

- 计算成本

  - 用户端

    主要处理程序：

    1. 计算加密距离之和
    2. 计算加权观察值的密文

    随着对象数的增加，程序2的变化较大（运行时间增加）

  - 云服务器端

    主要处理程序：

    1. 更新权重
    2. 估计基本真值

    大部分时间用于过程2（并行化的原因）

    总运行时间于用户数和对象数大致呈线性

- 通信开销

  阈值设置为0.001时，通信开销约为O(K).

- 能源开销（由密码相关操作和数据传输引起的）

## 分类数据实验评估

人群智慧系统：使用错误率（*ErrorRate*）即估计结果与基本真值间的不匹配值百分比作为评价指标。

- 准确性

  1. 观察每个对象的平均用户数（对象存在不被所有用户观察到的情况）：平均用户数越大，错误率越低。
  2. L参数：随着L的增大，错误率降低。

- 收敛性：两次迭代内收敛

- 计算成本

  - 用户端

    过程2比过程1耗时更多，因为过程二大部分操作在密文基础上。

  - 云服务器端

    更新真理的计算时间远远大于所有场景中更新权值的时间

## 并行PPTD实验

使用一个Hadoop集群作为云服务器，对1000个用户和1000个对象进行了人群感知系统的模拟。

- 对象数目

  随着对象数量的增加，并行PPTD比基本PPTD更加高效。

- Reducer节点数

  随着Reducer数量的增加，运行时间在一开始迅速减少，并且很快就变平缓了。

  (因为包括更多的Reducer节点，虽然提高了并行性，但将会引入更多的开销（例如，通信）)

## 补充

隐私保护策略：

1. 匿名化
2. 数据扰动
3. 基于密码学或安全多方计算的方法



