# PID2

---

## 数据环境约定

**请将所有数据的路径设为`./data/*`**

数据集下载地址：

1. [基本数据集](https://cloud.tsinghua.edu.cn/d/082fb75f372b4fa7a14c/)
2. [取sigma=1时的200ns弥散时间序列](https://cloud.tsinghua.edu.cn/f/3cc01e7dfe8c40cd992a/)[^1]
3. [取sigma=2时的200ns弥散时间序列](https://cloud.tsinghua.edu.cn/f/bb67c597f98a432b9c7f/)[^1]

可能有用的资料地址：

1. [往届ghost hunter宣讲会（区分粒子的思路介绍）](https://www.applysquare.com/pages/ghosthunter/webinar)
2. [大作业课堂动员会](http://hep.tsinghua.edu.cn/~berrysoft/bdeph2021/BDEPh2021_15_lite.mp4)

***

## 部分文件使用说明

### `PMT.csv`  探测器的位置信息

30个PMT探测器的位置信息，单位默认毫米 (如下所示)

| PMT_id | x | y | z |
| ------ | - | - | - |
| 0 | 428 | 139 | 700 |
| 1 | 265 | -364 | 700 |
| 2 | -245 | 756 | 245 |
| ... | ... | ... | ... |
| 29 | 245 | -756 | -245 |



数据来源于`PMT_Position.txt`，采用如下正则表达式修改：

    ```
    FROM: ^(\d+)\s+(-?\d+)\s+(-?\d+)\s+(-?\d+)$
    TO:   \1, \2, \3, \4
    ```

[^1]: 数据说明: 对应标签'1'或'2', 大小为(109166, 201)的数组。最后一列为1对应Alpha粒子,为0则Beta粒子.
