#### 判断

 只记得一道题：一个语法制导为 `L-SDD` ，仅当它计算当前节点属性时不会用到子节点的属性值（可能表述不正确）

#### 填空

4. 
5. 如果需要把 `y` 加载到对应的寄存器 `R2` 中，指令是（），（后面还有两空忘了）

#### **1.词法分析：**

忘记有什么了， 光记得涉及到：`+、=、id、if、int、float、<=  ` ,而且题目要求浮点类型和整型常量要有对应的 `TOKEN` 名称

(1)给定一段代码，设计 `TOKEN`的种别码
(2)写出一个 `DFA` ，包含整数部分，可选的小数部分和可选的指数部分，整数部分和小数部分前面有可选的正/负号。例:$+10, -10.2 , 103.2E10, -1E05$



#### 2.语法分析：

给定文法
$$
S->aABb \\
A->Aa|a \\
B->bB|\varepsilon
$$


(1)要求画出`LR(1)`自动机，并且判断是否`LR(1)`文法。

(2)消除左递归然后判断是否`LL(1)`，说明理由。





#### 3.给定文法

$$
S->E=id \\
S->if \space E \space then \space S \\
S->while \space E \space do \space S \\
S->begin \space S; S \space end \\
S->break\\
$$





（可能不全，但是主要是这些）

(1)要求设计`SDT`，实现：在非循环语句里出现 `break `的时候，报错。

(2)写成全综合属性的`SDT`形式

(3)写出栈操作





#### 4.中间代码生成

```c
double a[4][8], sum; //维数里的数字具体是多少记不清了，但知道怎么写就问题不大
int n;
...
if condition then
	sum = 0.0
	while condition do
		sum = a[i][j] + sum
		n = n + 1 //可能顺序反了（
else 
	sum = 1.0
```

(1)写出三地址码，100开始

(2)写出a的类型表达式，并且说明符号表里应该存储它的哪些内容。

(3)已知if的后继代码从116开始。需要回填哪些信息？





#### 5.运行环境

```pascal
program main;
var a: integer;
	procedure p;
	var b: integer;
  		procedure q;
  		var c: integer;
  		begin ... end;
  		procedure r;
		var d: integer;
		begin ... end;
	begin ... end;
begin
	//这里忘了
end
```

(1)画出代码执行到 `main->p->q->r `时候的控制栈和 `display` 表

(2)`r` 运行结束后，`display`表进行哪些操作？





#### 6.代码优化（包含神秘指令 `halt`）

```assembly
	I:= 1
	J:= 0 
L1: 
	J = J + 1
	READ I
	if XXX goto L2 (忘了什么条件但应该无伤大雅,代码是靠流图想起来的，可能有错误)
	WRITE J
	halt
L2:
	I = I*I
	goto L1
```



(1)划分基本块并且画出流图

(2)求定值到达信息`IN`

(3)求全部定值的`du`链

(4)求活跃变量信息`OUT`

(5)求全部变量的`ud`链