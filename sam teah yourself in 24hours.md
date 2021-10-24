### 
    Any Java class can hold data. One of the most useful is  Vector , a data
structure that holds objects of the same class.

Vectors are like arrays, which also hold elements of related data, but they
can grow or shrink in size at any time.
```java
import java.util.Vector;
// 开辟内存
Vector<String> victoria = new Vector<String>();

// 写入
victoria.add("Vance")
victoria.add("lskdfj")
victoria.add("aabbcc")

// 读取
String name = victoria.get(1)

// 类似indexOf方法
if (victoria.contains("Velma")) {
  System.out.println("Velma found")
}

// 删除
victoria.remove(0)// 方式一
victoria.remove("Velma")// 方式二

// 遍历 容器
for (String name : victoria) {// 前面存放单元的变量  后面是容器的 变量名
  System.out.println(name);
}

//排序
// 通过 Collections.sort(list) 的静态方法 sort来处理
 
```

### 继承
```java
  public class Point3D extends Point {
    // x,y 属性父类已经有了
    // 所以自己只要实现z 属性就可以了

    pubic int z;
    
    public Point3D(int x, int y, int z) {
      super(x, y);// 注意是这样初始化父类的
      this.z = z
    }

    public void move(int x, int y, int z) {
      this.z = z;
      super.move(x, y);
    }
  }
```

### Components And Container
    When you are putting a GUI together, you work with two kinds of objects:
components and containers. A component is an individual element in a user
interface, such as a button or slider. A container is a component that you
can use to hold other components.

    To add components to a frame, you must create the component and add it to
the container.

```java
// 这个类 控制组建放在哪
FlowLayout flo = new FlowLayout();
// 指定flo为 样式控制类
pane.setLayout(flo);
```

### 设计一个自己的panel
    The first step in creating your own user interface component is to decide
the existing component from which to inherit. The  ClockPanel component
is a subclass of  JPanel --page  183

### 有多套 布局类
```java
// The GridLayout Manager

```

### 如何监听
```java
import java.awt.event.*;

public class Graph implements ActionListener {

}

public class Graph3D implements ActionListener, MouseListener {

}

// 谁去监听  组件去监听
JButton fireTorpedos = new JButton("Fire torpedos");
fireTorpedos.addActionListener(this);
```

## Exceptions
  > These errors turn up when you write a Java program that compiles suc-
  >cessfully but encounters a problem as it runs.

  >the user of the class is the Java interpreter.
  > 有些异常 再所难免 比如运行时 接收输入    Java programs can take care of their own excep-
>tions by using a  try - catch block statement

## 忽略异常
```java
public loadURL(String address) throws MalformedURLException {
URL page = new URL(address);
loadWebPage(page);
}
```

## 多线程
 >If you put time-consuming tasks in their own threads, the rest
  of the program runs more quickly. This often is used to prevent a task from
  slowing down the responsiveness of a program’s graphical user interface
  (GUI).

## streams 读写数据（data）
  > java objects 本身就是数据结构
  >  taking its name from water streams that take fish, boats,
>and industrial pollutants from one place to another.
> streams 可以从  其他端口  网络 内存 硬盘  DVD-roms等读取写入数据
```java
//   There are two kinds of streams:
// . Input streams, which read data from a source
// . Output streams, which write data to a source

// All input and output streams are made up of bytes, 
// individual integers
// with values ranging from 0 to 255. 

// 三步走
// . Create a stream object associated with the data.
// . Call methods of the stream to either put information in the stream or
// take information out of it.
// . Close the stream by calling the object’s  close() method.

// 这里最常用的异常类
// IOException
// byte [] 到字符串的转换时非常常见的
```

## Buffer
  >  Buffering is the process of saving data in
>memory for use later when a program needs it. 
> 现从缓冲区读取 
>  When a Java program
>   needs data from a buffered input stream, it looks in the buffer first, which
>  is faster than reading from a source such as a file.