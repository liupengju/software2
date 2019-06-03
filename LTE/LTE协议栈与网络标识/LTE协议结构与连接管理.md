#### Uu&S1接口协议栈结构

- 协议（协议号：36.401）定义：Uu&S1上的协议栈分为：

  - 用户面：用于执行PS承载服务的协议。如通过AS传递的用户数据

- 控制面

  - 用于控制EPS承载，以及基于不同方面（包括请求服务，控制不同的传输资源，切换等等）的UE和网络之间的连接的协议，同时也包括NAS消息的透明传输的机制

  ![1559487077334](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559487077334.png)

##### 用户面协议

- 没有了RNC控制接口的用户平面（MAC/RLC）功能由eNodeB进行管理和控制
- 用户面和控制面协议栈均包含PHY，MAC，RLC和PDCP层，控制面向上还包括RRC层和NAS层。

![1559487716889](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559487716889.png)

![1559487751870](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559487751870.png)

##### 控制面协议栈

- ​	没有RNC，空中接口的控制平面（RRC）功能由eNodeB进行管理和控制

![1559487821405](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559487821405.png)

![1559487832028](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559487832028.png)

##### 连接管理概述

- 在LTE系统中，连接管理是UE和eNodeB以及MME之间连通性的管理，包括控制面板连接与用户面连接：

  - 控制面连接建立，也叫信令连接建立（包括RRC连接建立和S1信令连接建立）；
  - 用户面连接建立，也叫E-RAB连接建立

  ![1559488800797](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559488800797.png)

  > 手机要和SGW传输数据，数据要传输的话就意味着手机和SGW需要先建立E-RAB连接。
  >
  > 要建立用户面的数据首先要建立控制面。（控制面需要先建立信令连接。建立好再确认一些安全模式之后，就可以进行数据传输）。
  >
  > 控制面板的连接包括RRC连接（空口的连接，也就是UE和eNodeB的）和信令连接（eNodeB和MME的），这两段建立好了，就是一个信令连接建立成功。

- 信令连接

  - 信令连是为了业务承载连接的建立而建立
  - 但某些场景下，信令连接仅仅是为了某个信令过程而不是为了业务承载的连接，例如用户的位置更新过程。

  ![1559491410011](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559491410011.png)

  > 通常，建立用用户面连接需要先建立信令连接。但是建立控制面有时候并不完全是为了建立用户面

   

- RRC连接

  - RRC连接是UE和eNodeB之间的层三连接，RRC连接建立有UE出发

    ![1559493542062](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559493542062.png)

    > CCCH：公共控制信道
    >
    > DCCH：专有控制信道
    >
    > SRB0是在CCCH上边传输的，也就是SRB0传输的是多个用户一起发，而SRB1开始则是专用的。

- S1/S11接口控制面识别标识

  - 如何在S1/S11接口的控制面来识别术语某一用户的消息呢？
    - 在eNodeB测用eNB S1AP UE IE;
    - 在MME侧用 MME S1AP UE ID；

   ![1559497017824](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559497017824.png)

  > S1/S11接口中，对于一个UE，eNB侧有一个标识，MME侧有一个标识，这两侧的ID一起可以标识唯一的一个用户。一个ID用来区分一个UE是不够的，因为一个基站，对应这多个MME。

- 用户面连接建立（E-RAB连接建立）

  ![1559498120172](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559498120172.png)

  - S1/S11接口用户面识别标识

  ![1559498366386](C:\Users\liupe\AppData\Roaming\Typora\typora-user-images\1559498366386.png)

  

  - fa
  - fad
  - fad