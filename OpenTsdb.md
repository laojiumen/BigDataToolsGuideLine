#OpenTsdb
### 概述
基于HBase构建的分布式可扩展的时间序列数据库
优势：避免了hbase中存在的hot-spot现象

### 具体实现
三个部分：hbase(存储), tsd(查询), tcollector(采集数据)
数据库中建表: tsdb, tsdb-uid（tsdb的辅助表.
 
tsdb中存储使用标签(tag)标示一个检测结果，包括指标(metric) 元数据名字 和 元数据值。tsdb-uid用来管理这些创建的标签并创建唯一的id(UID)来唯一指定（一般为三个字节宽）
hbase(存储): tsdb 表的rowkey设计 -> UID+部分时间戳+标签名+标签值
