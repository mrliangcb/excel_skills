# excel_skills

### 1.IF函数
  IF(ISNA(VLOOKUP(Table!D2,Sheet1!$A$6:$A$7,1,0)),"F",Table!D2)



### 2.将35万批量改成350000  
选中涂黑 目标列，ctrl+F , 替换 , 查找内容写"万" , 替换为 0000    
亿也是同样道理  

但是如果有1.6亿和1.6万，这样做是不行的  
(1)筛选这一列，包含万 字的，然后选中这一列，ctrl+f ，把万字替换为 空,然后旁边增加一行,=10000*E2,于是1.6万，就换成16000了，放在附加行  
(2)  


### 3.SUMIFS 按条件求和  
 SUMIFS(L2:L8,D2:D8,D2)  
 L2:L8是要求和的数字  D2:D8是判断域  D2是判决标准  （也能写成{ , , }，但是不能选择一列，所以可以先选出F,Y辅助列，然后再求和也行）  

### 4.COUNTIFS数一下有多少个   
  COUNTIFS(D2:D8,"Y")   Y也可以写一个特定的单元格内容Sheet1!C2  
  数一下D2到D8中，Y有多少个  


### 5.LEFT()  
  LEFT(F219,FIND("号",F219&"号"))  
  
  
### 6.INDEX()  
  INDEX(A:A,SMALL(IF(ISNUMBER(FIND("女",$A$2:$A$100)),1000,ROW($2:$100)),ROW(A1)))&""  

### 7.查找这一格是否有这个字    
IF(ISNUMBER(FIND("A",A1)),"有","无")  
找A1中是否有A这个字母，有的话返回第一个值  

### 8.公式LEFT(B2,LEN(B2)-1)  
去掉最后一个字符  

### 9.=right(A1,6)  
留下右边的6个字符  

### 10.统计公式  
  IF(ISNUMBER(FIND("万",$J2)),LEFT($J2,LEN($J2)-1)*10000,IF(ISNUMBER(FIND("亿",$J2)),LEFT($J2,LEN($J2)-1)*100000000, $J2))  