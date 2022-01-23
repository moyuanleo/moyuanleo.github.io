# 算法(第四版) IntelliJ IDEA 配置环境搭建

* @墨缘
* 花了一天时间，遇到了各种奇怪的问题，找了网上的各种教程感觉不够全面，于是打算自己写一篇。
* 时间：2021.8.15

## 目标

* 实现书中1.1.10的示例代码：二分查找

## 笔者使用的工具

* Windows 10 20H2
* IntelliJ IDEA版本：2021.1.1
* JDK版本：9.0.4
* 作者提供的jar包：[下载地址](https://algs4.cs.princeton.edu/code/algs4.jar)   （来源）https://algs4.cs.princeton.edu/code/ 

![image-20210815160053936](https://i.loli.net/2021/08/15/krC3bMxJXTnf7Hz.png)

* 测试数据：[下载地址](https://algs4.cs.princeton.edu/code/algs4-data.zip) 本例中只需用到其中的 tinyW.txt 和 tinyT.txt

## 正式开始

* 建议开始前确认javac命令能够正确编译出class文件

### 一、配置CLASSPATH环境变量

* 将下载下来的algs4.jar文件放入C:\Users\leo\algs4\   文件夹内(将leo替换为你自己的用户名)
* ![image-20210815161649007](https://i.loli.net/2021/08/15/zHuDecS1rFsPhKZ.png)

* 依次点击 设置->系统->关于，找到右边的高级系统设置

<img src="https://i.loli.net/2021/08/15/le9yWJk6zVi84xu.png" alt="image-20210815160931543" style="zoom:33%;" />

* 依次点击”高级“选项卡，点击“环境变量”

  <img src="https://i.loli.net/2021/08/15/VleCvpbJ8EoaNHn.png" alt="image-20210815161140845" style="zoom:33%;" />
  
* 在用户变量中新建一个名为 CLASSPATH 的变量，值为

  ```
  C:\Users\leo\algs4\algs4.jar
  ```

* 依次点击确定退出”系统属性“窗口

### 二、创建IntelliJ IDEA项目

* 在IntelliJ IDEA中新建一个Project，笔者此处命名为 Binary_Search

### 三、导入jar包

* 依次点击 File->Project Structure->Modules 并按箭头和序号将C:\Users\leo\algs4中的algs4.jar文件导入

<img src="https://i.loli.net/2021/08/15/gjGzFSAdNPQs4H3.png" alt="image-20210815163356478" style="zoom:33%;" />

<img src="https://i.loli.net/2021/08/15/l3W8zQvuweaIhJL.png" alt="image-20210815163631905" style="zoom:33%;" />

* 如果能在External Libraries看到如图所示即为成功

<img src="https://i.loli.net/2021/08/15/Rn7ugt1sAEIVfrk.png" alt="image-20210815163906977" style="zoom: 33%;" />

### 四、输入代码

* 在项目的src目录中新建一个类，名为BinarySearch，输入书上的示例代码并保存

```java
import edu.princeton.cs.algs4.In;
import edu.princeton.cs.algs4.StdIn;
import edu.princeton.cs.algs4.StdOut;

import java.util.Arrays;

public class BinarySearch {
    public static int rank(int key, int[] a) {
        int lo = 0;
        int hi = a.length - 1;
        while (lo <= hi) {
            int mid = lo + (hi - lo) / 2;
            if (key < a[mid]) hi = mid - 1;
            else if (key > a[mid]) lo = mid + 1;
            else return mid;
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] whitelist = In.readInts(args[0]);
        Arrays.sort(whitelist);
        while (!StdIn.isEmpty()) {
            int key = StdIn.readInt();
            if (rank(key, whitelist) < 0)
                StdOut.println(key);
        }
    }
}
```

* 更好的代码可以在 https://algs4.cs.princeton.edu/11model/BinarySearch.java.html  中看到

### 五、使用Terminal编译并运行

* 将在上文中下载的 tinyW.txt 和 tinyT.txt放入src目录
* 在Terminal中进入src目录，输入以下代码，即编译完成，src目录下会出现BinarySearch.class文件

```
javac BinarySearch.java
```

![image-20210815164844574](https://i.loli.net/2021/08/15/DZdlTA2XS7f5yEV.png)

* 在Termianl中输入以下代码，理想情况下如图所示，即成功 ，此时的BinarySearch不要加.class （血的教训:unamused:）​

```
java BinarySearch tinyW.txt < tinyT.txt
```

![image-20210815165136237](https://i.loli.net/2021/08/15/6IyzufwUkgYm8dZ.png)



## 常见问题及可能的原因

### 一、提示“错误：找不到或无法加载主类“

![image-20210815170326247](https://i.loli.net/2021/08/15/JlOLkI8WofQvAsE.png)

* 此时编译应该正常进行，能够生成.class文件，可能由于运行时输成BinarySearch.class，
* 注意是否将java文件放入某package中，此时若要运行class文件，需要带上包名
* 若仍不能解决，可参考第一篇文档

### 二、Exception in thread "main" java.lang.NoClassDefFoundError: StdIn

### 三、BinarySearch.java:1: 错误: 程序包edu.princeton.cs.algs4不存在

* 问题二与三应该与在IDEA中导入jar包的位置以及环境变量CLASSPATH的配置有关

## 注意事项

* 使用终端进行编译和运行时，确保自己项目创建所用的JDK与编译运行的JDK是同一个版本
* 不要老是想着升级到最新版本的IDEA，可能会有意想不到的bug（我升级后双击居然运行不了，果断回滚
* 如果你的英语足够好，可以点击[这里](https://algs4.cs.princeton.edu/code/)查看官方的教程，在中间偏下从本文第一张图所示的位置开始

## 参考文档

https://www.cnblogs.com/wangxiaoha/p/6293340.html