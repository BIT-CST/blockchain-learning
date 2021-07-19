# Cloud-enabled privacy-preserving truth discovery in crowd sensing systems



<span class="cser-tag" markdown="1"> SenSys  </span> <span class="cser-tag" markdown="1"> CCF B </span>

> Miao, C., Jiang, W., Su, L., Li, Y., Guo, S., Qin, Z., … Ren, K. (2015). Cloud-enabled privacy-preserving truth discovery in crowd sensing systems. *SenSys 2015 - Proceedings of the 13th ACM Conference on Embedded Networked Sensor Systems*, 183–196. https://doi.org/10.1145/2809695.2809719



TA 为 clients 和 server 生成密钥。

> we assume a semantically secure (p, t)-threshold Paillier cryptosystem has been given (e.g., established by a **trusted key manage- ment center**)



# 为什么有错误值

poor sensor quality, lack of sensor calibration, background noise, incomplete views of observations, and even the intent to deceive



# 保护 2 种隐私

* 用户上传的数据

    private personal information. 

    aggregating health data, such as treatment outcomes

    geotagging campaigns can provide accurate and timely localization of specific objects

* 用户的权重

    user reliability

    * 和数据结合推断隐私

        > from user reliability information, together with his observation values, the attacker may be able to **infer the personal information** of the user, such as major, education level, age, gender, lan- guage, and even personality.

    * 操纵数据价格

        > the participating users usually trade their data with the system administrator for rewards, and the leakage of user reliability may lead to **malicious manipulation of data price**.

# 真值发现基本思想

The **common principle** shared in truth discovery approaches is that a particular user will have higher weight if the data provided by him is **closer** to the aggregated results, and a particular user’s data will be counted more in the aggregation procedure if this user has a higher weight

Each participating user will first send the encrypted summation of distances between his own observation values and the estimated aggregated values to the cloud server. Then, the cloud server updates users’ weights in encrypted form without decrypting the received distances information, and sends the updated weight to each user. Next, each user cal- culates the ciphertexts of weighted data using the received encrypted weight. Finally, the final results are estimated by the cloud server based on the ciphertexts received from users

# 真值发现过程

## 权重更新

![image-20210625083420171](https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/06/25/image-20210625083420171-083429.png)

## 真值更新

![image-20210625083451091](https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/06/25/image-20210625083451091-083453.png)

2 种数据

* continuous (e.g., temperature and hu- midity)
* categorical (e.g., multiple-choice answer)



## Threshold Paillier Cryptosystem

![image-20210625083551817](https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/06/25/image-20210625083551817-083553.png)

特点是私钥分给 n 个人，t 个人对密文进行部分解密，结合起来可以解密密文。

注意不是恢复密钥而是解密密文。

# 基本过程

<img src="https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/06/25/image-20210625083738811-083741.png"  style="max-width: 600px; width:100%;" />
