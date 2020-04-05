SQL Notes
# Definition
学生（学号，姓名，性别，身份证号，教师编号）
教师（教师编号，姓名，工资）

超键：
由超键的定义可知，学生表中含有学号或者身份证号的任意组合都为此表的超键。如：（学号）、（学号，姓名）、（身份证号，性别）等。

候选键：
候选键属于超键，它是最小的超键，就是说如果再去掉候选键中的任何一个属性它就不再是超键了。学生表中的候选键为：（学号）、（身份证号）。

主键：
主键就是候选键里面的一个，是人为规定的，例如学生表中，我们通常会让“学号”做主键，教师表中让“教师编号”做主键。

外键：
外键比较简单，学生表中的外键就是“教师编号”。外键主要是用来描述两个表的关系。
## reminder 
-　if two team TA TB both have teamid. dot "." is to specify which table　TA.Teamid
-　SQL 中增加 HAVING 子句原因是，WHERE 关键字无法与合计函数一起使用
- meaning of " = " found?
- 

# Syntax
- CREATE SCHEMA schema-name AUTHORIZATION user-name
- SELECT **column_name(s)** FROM **table_name** WHERE **condition**
- SELECT DISTINCT T.TeamID, T.TeamNameFROM Player P, Record R, Game G, Team TWHERE G.GameNo=R.GameNo AND G.HomeTeamID=P.TeamID AND T.TeamID=P.TeamID AND R.PlayerID=P.PlayerIDGROUP BY G.GameNo, T.TeamID, T.TeamNameHAVING SUM(R.Points) > ALL (SELECT SUM(R2.Points) FROM Record R2, Game G2, Player P2 WHERE G2.GameNo=R2.GameNo AND P2.PlayerID=R2.PlayerID AND P2.TeamID=G2.AwayTeamID AND G2.AwayTeamID=T.TeamID GROUP BY G2.GameNo);