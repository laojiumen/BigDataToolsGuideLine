# Hbase(Official description)
### rowkey Design
* salting：加盐的方式，row key 的设计可以累加如token_id_num，一级一级的累加.
	   另外，此方式也可以理解为加密解密，如将有不同长度的字符串通过md5或者base64等方式存为固定长度的数据，第一是为了减少内存，第二是便于查址，第三是便于保护数据的真实性
* not to use timestamp or squence better: 最好不要用时间戳或者是累加的序列,如果一定要用的话可以使用OpenTSDB,或者timestamp不要放在首位 


#Hbase in action
###table schema design
* limit(used to limit the row):
	 rowkey -> limit row, family -> limit net IO, HFile, hard disk
	qualifier ->  net IO, timestamp -> limit HFile, hard disk, net IO
* 规范化和反规范化: 规范化 -> 关系型数据库
		    反规范化 -> 数据重复存在多个地方，减少join,提升查询速度
