##使用自编码器对两个k线的变化状态进行分类,再使用MTCL进行行情几率分析

k线1:开盘价，最高价，最低价，收盘价，成交量

k线2:开盘价，最高价，最低价，收盘价，成交量

只对两个K线的分变情况进行分类，再用蒙特卡洛树对k线变化状态进行行情几率预测

自编码器接收的数据为：
1）开盘价变化率:
          开盘2 - 开盘1
    ▵o = --------------
             开盘1

2）最高价变化率:
          最高2 - 最高1
    ▵h = --------------
              最高1

3）最低价变化率:
          最低2 - 最低1
    ▵l = --------------
              最低

4) 收盘价变化率:
          收盘2 - 收盘1
    ▵c = --------------
              收盘1

5）成交量变化率:
          成交2 - 成交1
    ▵v = --------------
              成交1

然后使用自编码器对这5个数据进行自编码分类，预计分为100～1000类别,再使用MTCL进行行情几率分析
