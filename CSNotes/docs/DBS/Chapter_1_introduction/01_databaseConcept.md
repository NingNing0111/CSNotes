# 数据库系统概论

- 数据: **Data**
- 数据库: Database, **DB**
- 数据库管理系统: DataBase Management System, **DBMS**
- 数据库系统: DataBase System, **DBS**
- 数据库系统的特点(优点)


## 数据 Data

&emsp;数据是**数据库中存储的基本对象**。其定义是：描述事物的符号记录。

&emsp;数据的种类：数字、文字、图形、图像等。

&emsp;数据的含义称为**数据的语义**，数据与其语义是不可分的。

## 数据库 DB

&emsp;&emsp;数据库是**长期存储**在计算机内、**有组织**的、**可共享**的**大量数据的集合**。

&emsp;&emsp;数据库的基本特征：

- 数据按一定的数据模型组织、描述和存储；
- 可为各种用户共享、冗余度较小、易扩展；
- 数据独立性较高。

## 数据库管理系统 DBMS

&emsp;&emsp;DBMS是位于用户应用与操作系统之间的一层数据管理软件，它是基础软件，是一个大型复杂的软件系统。

&emsp;&emsp;DBMS能够**科学地组织和存储数据、高效地获取和维护数据**。

&emsp;&emsp;数据库在计算机系统中的位置：

![](imags/1-1.png)

&emsp;&emsp;数据库处于操作系统与用户应用软件之间，处于基础软件平台。

### 主要功能

**1. 数据定义功能**

   - 提供数据定义语言(DDL)
   - 定义数据库中的数据对象
  
**2. 数据组织、存储和管理**

   - 分类组织、存储和管理各种数据；
   - 确定数据在存储级别上的结构和存取方式
   - 实现数据之间的联系
   - 提供多种存取方法提高存取效率

**3. 数据操纵功能**

   - 提供数据操纵语言(DML)
   - 实现对数据库的基本操作(增删改查)
  
**4. 数据库的事物管理和运行管理**

   - 数据的安全性、完整性、多用户对数据的并发使用
   - 发生故障后的系统恢复数据库
   - 由数据库管理系统统一管理和控制，保证事务正常运行
  
**5. 数据库的建立和维护功能**

   - 提供实用程序/工具，完成数据库数据批量装载，数据库转储，介质故障恢复，数据库的重组织和性能监视等
  
**6. 其它**

   - DBMS与网络中其它软件系统的通信
   - DBMS系统之间的数据转换
   - 异构数据库之间的互访和互操作
  
## 数据库系统 DBS

&emsp;&emsp;DBS是指在**计算机系统中引入数据库后的系统构成**。在不引起混淆的情况下常常把数据库系统简称为数据库。

### DBS构成

- 数据库
- 数据库管理系统及其应用开发工具
- 应用程序
- 数据库管理员 (DataBase Administrator, DBA)

![](imags/1-2.png)

## 数据库系统的特点

**1. 数据结构化**

   - **数据的整体结构化**是数据库的主要特征之一
     - 不再仅仅针对某一应用，而是面向整个企业或组织；
     - 不仅数据内部结构化，整体是结构化的，数据之间具有联系；
     - 数据记录可以变长；
     - 数据的最小存取单位是数据项
   - **数据用数据模型描述**，无需应用程序定义
   
**2. 数据的共享性高，冗余度低且易扩充**

   - 数据面向整个系统，可以被多个用户、多个应用共享使用；
   - 共享后具有如下好处：
     - 减少数据冗余，节约存储空间
     - 避免数据之间的不相容性与不一致性
     - 使系统易于扩充
  
**3. 数据独立性高**

   - 物理独立性
     - 指用户的应用程序与数据库中数据的物理存储是相互独立的。当数据的物理存储改变了，应用程序不用改变。
   - 逻辑独立性
     - 指用户的应用程序与数据库的逻辑结构是相互独立的。数据的逻辑结构改变了，应用程序不用改变。
   - 数据独立性由数据库管理系统的二级映像功能来保证。
  
**4. 数据由数据库管理系统统一管理和控制**

- **数据的安全性(Security)保护**: 保护数据以防止不合法的使用造成的数据的泄密和破坏。
- **数据的完整性(Integrity)检查**: 保证数据的正确性、有效性和相容性。
- **并发控制(Concurrency Control)**: 对多用户的并发操作加以控制和协调，防止相互干扰而得到错误的结果。
- **数据库恢复(Recovery)**: 将数据库从错误状态恢复到某一已知的正确状态。
  
## 总结

&emsp;&emsp;数据库是**长期存储**在计算机内**有组织**的**共享的**大量的数据集合，它可以供各种用户共享，**具有最小冗余度和较高的数据独立性**，数据库管理系统在数据库建立、运用和维护时对**数据库进行统一控制**，以保证数据的完整性、安全性，并在多用户同时使用数据库时进行并发控制，在发生故障后对数据库进行恢复。