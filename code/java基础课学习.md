  ### 栈内存 堆内存 方法区  static 成员区  方法内部区
  **模糊的东西学不会，理解不了的东西记不住**
        -- 学习传智 基础课 有感  
        -- 编译器  第一步 认的就是类型 类型对不上 直接报错  引用 内存地址是有类型的
        -- 从栈内存 堆内存 方法区     基本类型和引用类型  来理解
        -- 就是内存的读写 了解到这层，就不会再被其他的乱七八糟的概念 模糊了
        -- 如果直接用内存读写的方式来 教育编程 岂不是 很直观， 直接到本质， 所以很多教育 
          其实是咕哝玄虚  教的人自己也不是很清楚   尤其是大学的IT教育 简直就是坑人 
          真的，太坑了   不知道这些人怎么在大学里上课的 

  重写 override  因为方法是内存地址 所以子类可以覆盖掉父类
  但是静态方法 不能 override 这个是类的属性  放在 静态方法去


  如果像任东  那样 一开始就学学扎实  再出来混呢
  老是 埋怨 没有很好地有人带  真的  其实有很多资源可以学习

  多态 基类  支持无限扩展   打破 类型限制
  强类型语言 很多概念 就是打破  强类型 带来的类型限制

  多态弊端  不是使用子类的特有功能

  如何解决：
    Son s = (Son) f;// 强行转换  把父类想引用 强行转换为子类的引用  这个时候 子类所有的方法都
      // 可以调用


  分析： 从具体到抽象 （分析出共性）
  实现： 从抽象到具体 （写实现基类（抽象类）  再实现具体子类）


  接口是没有构造方法的
```java
  interface Person {

  }
  // public static final int a  接口中的属性都是 静态属性
  // 抽象类 is a  共性功能
  // 接口  like a 扩展功能 usb接口
```

### 匿名内部类 在安卓开发中使用比较多
```java
  pd.method(new Person() {
    public void study() {
      System.out.println('实现完这个 类后 直接在内存中 开辟')
    }
  })
  // 用完后 就会被gc 回收
```

### 返回值类型
```java
  Outer.method().show()
  method是静态方法，由于可以调用方法，所以返回值method是个对象   链式编程
```

### java语法设计上的缺陷
```java
  只有方法可以多态 ，但是没有virtual关键字
  interface Inter {
    void show();//这里省略了public abstract  重写的的时候 忘记 public 就报错了 
  }
```

### eclipse常用快捷键
    - ctrl+shift+f 格式化
    - ctrl+shift+o 导入包
    - alt+上/下 箭头 滑动代码

## jar 是什么文件
    - jar 是多个class文件的压缩包
    - 项目右键 export Java下选择JAR文件
    - 定义和调用 拷贝到项目目录  右键选择 add to build path
    - 一般配合  javadoc使用
    - debug 设置断点
```java
    if (!(obj instanceof Student)) {
        return false;
    }
```

## 可以克隆的  需要实现Cloneable 接口

## 字符串常量词 概念

## 反编译工具  XJad
  不太理解的知识点通过反编译工具  查看
```java
  Strinig s5 = null 
  System.out.println("isEmpty" + s5.isEmpty())//直接报 空指针异常
```

## 特例
```java
  // -方法内  改变 String类型参数 不会改变 虽然是引用类型 但是不会改变
  // java 内存有个字符串 常量次

  // byte 缓冲区  0-127
  Interger i7 = 127;
  Interger i8 = 128;
  System.out.println(i7== i8); //false

  // Inter.valueOf() 方法源码
  // -128-127 到IntegerCache.cache[i + IntergerCache.low]

  // System.arraycopy() 这个命名写错了
```


## 字符串分割
```java
    String s3 = "d:\\work\\vue";
    String[] arr = s3.split("\\\\");// 需要4个分隔符
```

## 集合
```java
  // 集合只能存储引用类型
  // 集合可以存储不同类型的元素
  // java提供了很多集合类
  // Collection = 》List => ArrayList Vector LinkedList
  //              》 Set =>HashSet TreeSet 

  // 迭代器是依赖于集合而存在的
  // 集合长度 size() 不是length（）方法
  // 这里 Iterator用的比较多
  Iterator it = new ArrayList()
  while(it.hasNext()) {
    String s = (String)it.next();
  }

  // contains()方法 依赖于equals() 方法

```