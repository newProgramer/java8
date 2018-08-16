# 语法

```
(parameters) -> expression
或
(parameters) ->{ statements; }
```

以下是lambda表达式的重要特征:

* **可选类型声明：**不需要声明参数类型，编译器可以统一识别参数值。
* **可选的参数圆括号：**一个参数无需定义圆括号，但多个参数需要定义圆括号。
* **可选的大括号：**如果主体包含了一个语句，就不需要使用大括号。
* **可选的返回关键字：**如果主体只有一个表达式返回值则编译器会自动返回值，大括号需要指定明表达式返回了一个数值。

```
public class TestLambda {

    //类型声明
    MathOperation add = (int a, int b) -> a + b;
    //不用类型声明
    MathOperation sub = (a,b) -> a - b;
    //用括号
    MathOperation multi = (int a, int b) -> { a+=b; return a * b; };

    MathOperation div = (int a, int b) -> a / b;

    @Test
    public void test() {
        TestLambda testLambda = new TestLambda();

        //两种写法
        System.out.println(operate(1,2, add));
        System.out.println(add.operation(1,2));
        System.out.println(operate(1,2, sub));
        System.out.println(sub.operation(1,2));
        System.out.println(operate(1,2, multi));
        System.out.println(multi.operation(1,2));
        System.out.println(operate(1,2, div));
        System.out.println(div.operation(1,2));
    }

    private String operate(int a, int b, MathOperation mathOperation) {
        return String.valueOf(mathOperation.operation(a,b));
    }

    interface MathOperation {
        int operation(int a, int b);
    }
}
```

> Lambda表达式主要用来定义行内执行的方法类型接口
>
> Lambda表达式免去了使用匿名方法的麻烦
>
> Lambda表达式只能引用标记了final的外层局部变量



