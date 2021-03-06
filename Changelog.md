###MyCat Release Notes
####MyCat 1.3.0.3-alpha
+ order by 带函数的 的bug,如  order by date_format(traveldate, '%y-%m-%d')

+ 1.3.0.1修改order by ,group by 别名的bug

+ 增加pluginManage,修正eclipse导入lifeCycle错误

+ 修正多节点merge排序结果不正确bug

+ 修正skip过慢问题

+ 排序优化

+ 注解增加/*#mycat:格式;where condition1 or 1=1之类的永真条件路由错误问题

+ 修正最大堆排序结果不正确bug

+ between语句范围路由的支持

+ 修正druid group by 语句字段带表名提示字段找不到的问题

+ 解决druid主键in查询只匹配一个条件的问题

+ fixed:#87;mycat注释兼容mysql注释

+ 解决druid解析器order by字段名称与select语句字段名称不一制问题

+ 解决group by order by问题;解决select for update问题;修改错误提示信息

+ 解决druid解析器count语句问题

+ 修正Druid解析器添加分片字段错误



####MyCat 1.3.0.1

>git:

Fix bug:

1. 数据报文在某些特殊情况下没有实时写入Socket导致时延（重要）
2. Druid解析器的一些空指针、Limit处理、以及单引号的Bug

#####存在的缺陷

1. 目前还没有发现新的Bug

---
####MyCat 1.3


>git:e3111dfdee64163bd15aa6022171ad34c3aad455

特性:

1. 一致性hash分片支持
2. 默认Druid解析器提升性能
3. 人工智能Catlet 编程实现跨分片Join ，143行Demo代码可供参考
4. 性能大幅提升，相对1.2 插入性能提升100%，查询性能提升50%

Fix bug:

1. checkWriteBuffer可能分配不够的空间，存在潜在Bug()
2. Mysql 连接同步优化，以及修改Timeout 超时的问题
3. 主键缓存优化
4. 后端连接事件优化

#####存在的缺陷
- 比较重要的一个缺陷是数据报文在某些特殊情况下没有及时写入Socket导致时延，已经在1.3.0.1修复
	
 
| Author    |                   |                          |                             |
| :-------- | :---------------  | :----------------------- |:--------------------------- |
|姓名 |群名片|QQ|任务|
| Marshy  |        ||负责任务跟踪，提供了机器供Mycat官网使用，是Mycat美女大总管|
| |成都研发  ||分片排序优化模块       |
|王灯武 |武  | 15297449|引入新的Druid解析器    |
| 吴京润|一坨  |744142084| 一致性Hash分片和工具       |
| 海王星  | 负责github和版本发布，持续化构建       |||
| 石头狮子  | 写文档、实现了HA Datasource工具等       |||
| 冰风影  | 修复JDBC连接缺陷，开始NoSQL模块开发       |||
| .Jagger  | 自增长主键实现和性能测试、参与性能优化过程|||
| 非非想  |Mycat官网第一版       |||
| 一觉醒来  |协助数据库调优       |||
| 赵闪|Cheris |694050364 |提供了性能测试报告       |||
|詹益峰|哈哈|758297924|Mycat in action文档汉译英|
|刘晓栋|晓栋|67814134|翻译Mycat in action|
|陈秀升|xiuson|443697052|Mycat in action翻译和Mycat-server readme.md中英文两部分|
| 其他友情客串者  |酱油师、xiuson、哈哈、BEN、Mr.ZHU、超仔、深海、广州-UFO、等很多同学 ||||


---

####MyCat 1.2

>MyCat 1.2 (svn:r515)

特性:

1. 增加了SQL拦截器的功能，默认的实现将Mysql转义字符进行了处理

Fix bug:

1.  事务隔离问题

| Author    |                    |
| :-------- | :---------------  |
| 新加入 林志强、林晁、齐朗晔、杨创、何智峰等（一些遗漏了真名的同学，可以来信）  | 全面系统测试，协助发现和解决了一些重要缺陷|
|孙娟(酱油师）|全局序列号更新       |
| (opencloudber）  | 排序归并的一些缺陷发现并修复    |
| 王金成(永不言败）   | 发现和修复一些缺陷       |
| 蒋常春（CC）  | 性能测试       |
| 白磊（first level ）  | 性能测试    |
| 李翔远（光电=ω=鼠标 ）  |  	时间范围分片函数以及between支持      |
| 黄进兵（疯鱼）  | 贡献字符串分片函数|
| 高权（IT坨坨）  |测试以及缺陷反馈|
| 吴志辉（Leader）  |MyCat-server       |
| rainbow 团队  |协助数据库调优       |
|Qing|MyCat-cluster|
|提婆谭（暂定）|MyCat-Balance|
|Michael@micmiu.com|MyCat-server|
|无影|MyCat-server|
|shenzhw|性能测试|
|小鱼|测试|
|阿德|排序算法|
|面朝大海|修复BUG|
|木糖醇患者|修复BUG|

#####很多志愿者在努力研发中，后期版本陆续列出贡献者信息
---
