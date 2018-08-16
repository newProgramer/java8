```
public interface TestInterface {

    default void print() {
        System.out.printf("我是一个默认方法");
    }
    
    static void print2() {
        System.out.println("我是一个静态方法");
    }
}

public class TestInterfaceImpl implements TestInterface {
}

public void test() {
    TestInterface testInterface = new TestInterfaceImpl();
    testInterface.print();
    TestInterface.print2();
}
```



