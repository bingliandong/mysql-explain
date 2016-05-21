# mysql-explain
EXPLAIN Output Format(官方中文翻译)

这是一个关于select执行计划的解释语句.

针对每一个表执行select计划，explain会return一行信息。按mysql运行select语句的顺序，并且以表格形式列出信息。mysql使用嵌套循环join方法解决所有的joins。这意味着mysql从第一个表中获取一行数据，然后再从第二个表中获取一行数据，然后是第三个表，等等。当所有的表执行完，mysql输出选中的列，直到一个表中发现其中有更多的匹配行通过表列表回溯。下一行被从该表中读出并且此过程在下一个表中继续。

在mysql 5.7.3v之前，当关键字EXTENDED被使用时，explain产生一个show警告被看作额外的信息。explain EXTENDED还显示过滤列。看Section 9.8.3, “EXPLAIN EXTENDED Output Format” 。在mysql 5.7.3，扩展的输出是默认的，所以关键字EXTNEDED不是必须的。

警告：不能在同一个explain语句中使用EXTENDED和RARTITIONS，此为，任意两个关键字都不能再format选项中一起使用。

