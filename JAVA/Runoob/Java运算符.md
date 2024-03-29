子类是父类的类型，但父类不是子类的类型。

子类的实例可以声明为父类型，但父类的实例不能声明为子类型。

```
class Vehicle {}

public class Car extends Vehicle {
    public static void main(String args[]){
        Vehicle v1 = new Vehicle(); //父类型
        Vehicle v2 = new Car(); //子类的实例可以声明为父类型
        Car c1 = new Car();    // 子类型
        Car c2 = new Vehicle(); //这句会报错，父类型的实例不能声明为子类型

        //Car（子类）是Vehicle（父类）类型, Vehicle（父类）不是Car（子类）类型
        boolean result1 =  c1 instanceof Vehicle;    // true
        boolean result2 =  c1 instanceof Car;        // true
        boolean result3 =  v1 instanceof Vehicle;    // true
        boolean result4 =  v1 instanceof Car;          // false
        boolean result5 =  v2 instanceof Vehicle;    // true
        boolean result6 =  v2 instanceof Car;          // true

        System.out.println(result1);
        System.out.println(result2);
        System.out.println(result3);
        System.out.println(result4);
        System.out.println(result5);
        System.out.println(result6);
   }
}
```

从执行结果来看，虽然 v2 被声明为了 Vehicle（父类），但它既是 instanceof Vehicle，又是 instanceof Car，所以 v2 其实是 Car（子类），否则 v2 instanceof Car 应该为 false。





**C + = A** 与 **C = C + A** 是有区别的一句话总结： **+= 运算符既可以实现运算，又不会更改 s 的数据类型；而后者，C 和 A 必须是同一类型，否则无法直接运算**。

```
public class Student{
    public static void main(String[] args){
        short s = 10;

        //s = s + 3; 编译不通过
        s = (short)(s + 1); //不建议如此实现
        s += 1;    //既可以实现运算，又不会更改s的数据类型
        System.out.println("输出变量");
    }
}
```

另外， **-=** ， ***=** ， **/=** 也应同理。