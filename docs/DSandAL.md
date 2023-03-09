# 数据结构与算法

计算机中的核心课程（我认为），主要是算法相关，这样划分只是为了单个界面不至于太多内容

## 数据结构

### Introduction

#### 结构体

结构体封装一个用户自定义的数据类型（包括操作），因此结构体的知识一定要扎实。



首先注意`struct Xiaoma { ... };`和`typedef struct { ... } Xiaoma;`的区别



`struct Xiaoma { ... };`实例

```c++
struct Xiaoma {
    char name[20];
    int age;
};		//自定义了一个数据类型“Xiaoma”，包含两个成员

int main() {
	Xiaoma MYC; //声明了一个“Xiaoma”类型的变量MYC
    strcpy( MYC.name, "MaYueChen");
    MYC.age = 20;
```

结构体作为函数参数：

```c++
#include <headers>

void printINFO( struct Ma Xiaoma );

struct Ma {
    char name[20];
    int age;
};

int main() {
    Ma xiaoma;
    strcpy( MYC.name, "MaYueChen");
    MYC.age = 20;
    
    printINFO( struct Ma xiaoma );
    
    return 0;
}

void printINFO( struct Ma Xiaoma ) {
    cout << Xiaoma.name << endl;
    cout << Xiaoma.age << endl;
}
```



**指向结构的指针**

定义一个指向`Ma`数据类型的指针`xiaoma_pointer`：`struct Ma *xiaoma_pointer`

初始化指针（存放结构变量的地址）：`xiaoma_pointer = &Xiaoma`

**指针访问结构成员表示为：**
`xiaoma_pointer -> name`;

**typedef关键字**
可以使用typedef为类型起一个“别名”，然后用别名来定义此类型的变量

```c++
typedef struct DataStack {
    int arr[MAXSIZE];
    int top;
} Stack, *S;
```

现在，可以用`Stack`来定义`DataStack`类型的变量，用`S`定义指向`DataStack`类型的指针变量。

### 概论
一些正式讲课前的宏观层面的观点，就当随想集记录一下：
> 参考余腊生的PPT

**fundamental Terminology**

+ Data: Data carry message.
  + Numeric data
  + Non-numeric data
+ Data element/member
+ Data item
+ Data object: Set of Data members with the SAME type
+ Data type(int e.g.): Express the range(0~2,147,483,647) and their methods set(+-*/ e.g.).

**ADT(Abstract Data Type)**

+ Encapsulation
+ Inheritance
+ Polymorphism

Form description of ADT:(**important**)
``` c
ADT adt_name {
    DataObject = ;
    Structure/Relation = ;
    Operations:
        /*prototype*/
        precondition
        input
        process
        output
        postcondition
}
```

given example:(I add some commits)
``` c
ADT Complex {
    Data object: D = {e1, e2|e1, e2 belong_to RealSet };
    Data Relationship: R1={<e1, e2>|E1 is real and E2 is imaginary part of the plural number};
    Essential operations:
    InitComplex(&Z, e1, e2); //Initialize an Instance, This operation is necessary
    DestroyComplex(&Z); //Destroy an Instance, This operation is necessary
    GetReal(Z, &realPart); //Didn't change the elemetns, called 'referrence operation'

    //On the contrary, operation that changes elements called 'process operation'
    Add(Z1, Z2, &sum); 
}ADT Complex;
```

+ predecessor and successor

    Only one predecessor and one successor: Linear list

    Only one predecessor and multiple successor: Tree

    multiple predecessor and multiple successor: Graph

*Can three structures mentioned above represent all the relationships in nature?*

Not. We need **Set**.

Linearlist, Tree, Graph and Set can represents every relationships.

+ Logic structure
Data forms of organization ，the logical relation between the data element 
  + associative means
  + adjacency relation
      + Linear
      + Non-linear

+ Physical structure(Storage mapping): The mapping of logical structure in the storage
  + Node

> We will see the 'Logical' and 'Physical' appears in pairs everywhere.

[虽然想锻炼英语能力，但为了避免复习时看得太难受，还是用中文吧]

 **抽象** 是编程中最重要的事情。

**Abstract** is the most important thing in programming.

步骤抽象（Procedure Abstraction）

+ 把函数当做黑盒子 treating funcion as black box
+ 予以明确的描述 giving concise specification


对于一个函数，我们只需要输入一个数，然后得到输出结果（也可以为void），而不关心具体细节

这样的抽象使得函数自身对程序没有影响，同时解放了程序员，极大地减小了工作量

#### 复杂度(Complexity)

**时间复杂度**

**空间复杂度**



**后续课程的基本脉络**

1. 给出抽象数据类型（ADT）的定义
2. 给出逻辑结构（Logical）
3. 使用不同的存储方式（Physical）
4. 实际应用

### Linear List

n个元素形成的序列，其中基本组成有表的头元素、尾元素、直接前驱与直接后继

几个重要概念：

+ Linear List
+ Length
+ Is Empty?
+ Order

注：这里的Order指元素的位序，其从1开始（而非0）

#### ADT of Linear List

    ADT   List {
    Data object：D＝{ ai | a_i ∈ElemType, i=1,2,...,n, n≥0 }
    Relation ：R1＝{ <ai-1 ,ai >|ai-1 ,ai∈D, i=2,...,n }
    Operations ：
        InitList( &L ) 
        DestroyList( &L )
        ListEmpty( L )  // to check the status   may  include a ListFull()
        ListLength( L )  //to get the attribute
        //to get the element in the list
        PriorElem( L, cur_e, &pre_e )
        NextElem( L, cur_e, &next_e )
        GetElem( L, i, &e )
        LocateElem( L, e, compare( ) ) //to search
        ListTraverse(L, visit( )) //to  traverse it(visit all the elements in the list and only once)
        ClearList( &L ) 
        PutElem(& L, i, e ) 
        ListInsert( &L, i, e ) 
        ListDelete( &L, i, &e)
    } ADT List


## 算法



