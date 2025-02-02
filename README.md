# 全目录

3000套系统，LW，复制到流浪器：www.yuque.com/wisebit/blog

# 7.CompilationPrincipleDesign


<p>抠群: 983063232(sql文件)</p>
<p>抠: 206157502(sql文件)</p>

<p><h1 align="center">7.编译解释器</h1></p>

<p align="center">
	<img src="https://img.shields.io/badge/jdk-1.8-orange.svg"/>
</p>

# 简介
>
> 
>
>
 <p>一、需求分析</p>
 <p>以编译原理书中最后一项作业，根据前端生成的中间代码来编写后端解释器，其中间代码标示了每行的行号，同时还包含了赋值语句、跳转语句、二位运算表达式的四则运算，条件语句跳转，列表类型的值获取等等，对于这个简单的中间代码执行程序，可以很简单的根据每行定义一个槽列表，方便跳转语句。主要的值类型可分为整型，布尔类型，我使用Object类型的列表存入，用instance判断其类型，从而转换，语法分析器中读入词法列表，根据每个槽生成槽内的字节码列表，槽对应行号和字节码列表。</p>
 <p>二、可行性分析</p>

 <p>上文中我使用槽代表每行应该执行的语句，后面我定义了一部分字节码，整个流程是以编译成字节码后执行的，对于字节码和语句树的方式，前者更加方便操作（对于列表的前进后退等等），更能完好的控制流程跳转。
 最后使用虚拟机的方式遍历执行字节码，虚拟机参考Python的执行方式，虚拟机内有两个值列表，一个存入当前作用域内执行的值，一个HashMap存入变量，对应执行列表中的某个位置。</p>
 

 <p>三、总体设计</p>
 <p>1.   首先主程序读入文件，转换成字符串。</p>
 <p>2.   传入词法分析器，生成特定的词法列表。</p>
 <p>3.   传入语法分析器，生成槽列表（字节码列表）。</p>
 <p>4.   槽列表传入虚拟机，遍历执行。</p>
 <p>5.   得到执行完成的两个列表，运行内列表和变量哈希列表，输出。</p>




# 环境

- <b>IntelliJ IDEA 2009.3</b>

- <b>Mysql 5.7.26</b>

- <b>Tomcat 7.0.73</b>

- <b>JDK 1.8</b>


## 缩略图

![](https://bitwise.oss-cn-heyuan.aliyuncs.com/2024/9/10/abe93df6-d5c0-4390-a99b-7a8d82db6a8b.png)

![](https://bitwise.oss-cn-heyuan.aliyuncs.com/2024/9/10/00acfd3c-1506-4477-92c2-b85652562619.png)

![](https://bitwise.oss-cn-heyuan.aliyuncs.com/2024/9/10/4fffd63a-7180-47b4-b829-5bb830b3abc3.png)

![](https://bitwise.oss-cn-heyuan.aliyuncs.com/2024/9/10/d5628a16-db8d-4c40-b873-a7589368601f.png)

![](https://bitwise.oss-cn-heyuan.aliyuncs.com/2024/9/10/7529a8ab-f832-4aab-b7a1-92090f0fc3b0.png)

