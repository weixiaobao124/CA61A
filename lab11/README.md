### lab11

reader.py

>read函数：先将输入字符串经过tokenize转化为一些tokens，然后调用read_expr将token转化为expr类
>
>
>
>lexer：词法分析
>
>paser: 语法分析



expr.py

paser将token转化为expr的四种类型，分别为`Literal`, `Name`, `CallExpr`, and `LambdaExpr`

Literal：字面值



Name：名字，可能绑定为变量，或者绑定为`CallExpr`



CallExpr：支持内置的add，min等操作，在`expr.py`的env中定义，即`Value`的子类`PrimitiveFunction`。支持自己定义的lambda操作。



LambdaExpr:参数，函数体均是expr组成





 对于`PrimitiveFunction`，直接用传给它的参数就能计算

 对于`LambdaExpr`，需要先用实参替代形参

 因此如果能在`env`中新定义函数的话，需要用到类似`LambdaExpr`类的构造



env

需要新的env的地方:`LambdaExpr`，需要先用实参替代形参


