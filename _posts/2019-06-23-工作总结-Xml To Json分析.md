Xml To Json分析

一.已知条件
1.xml文件标签和json标签的对应关系----表格对应关系
2.所需json文件的格式----一个json版式的文件模板
3.Xml文件大体格式----通过示例xml文件和对应关系总结所得
4.一个测试的Xml文件----完整的xml文件

方案一：（已实现）
具体步骤：
首先使用java内部内嵌的技术（javax.xml.bind）设置一个和目标对应（标签名称和对应的从属关系）的xml文件；
然后使用dom4j技术从已知的xml文件中获取表格中的相应标签对应的值存入map集合；
随后使用自定义的pojo（也就是实体类中的set方法）设置和目标对应的zml文件中的内容；
最后先将得到的目标的xml文件使用java内部内嵌的技术（javax.xml.bind）将xml文件转换为Object对象，然后使用阿里jar包（com.alibaba.fastjson.JSON）中的JSON.toJSONString方法将Object转换为json输出
方案分析:
1.map数据存储过于复杂，嵌套多层map，容易出现遍历错误
2.由于每次的标签的数据获取都需要调用方法，效率低，执行慢；
3.由于给定的xml文件固定，如果xml文件改变，需要在代码中修改大量的标签对应关系，操作不便。

方案二：


