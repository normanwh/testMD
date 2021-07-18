# 数据结构  
- 线性表：  
- 逻辑结构:  
	除了头结点都有唯一前驱，除了尾结点都有唯一后继  
- 存储结构:  
	顺序表：
~~~c++
	typedef struct Lnode
	{
		int length;
		struct Lnode arr[MAXSIZE];
	}Lnode;

	单链表：
	
	typedef struct Lnode
	{
		int data;
		struct Lnode *next;
	}Londe;
	
	双链表:
	
	typedef struct Lnode
	{
		int data;
		struct Lnode *next;
		struct Londe *prior;
	}Lnode;

	静态链表:
	
	typedef struct Lnode
	{
		Element data;
		int  *next;
	}List[MAXSIZE];
~~~

> 特点：  
>> 顺序表按顺序存储在连续的空间，按序号查找时间复杂度为O(1),按值查找时间复杂度为O(n),但插入删除操作要移动大量元素，时间复杂度为O(n)
>> 链表不是连续存储空间，所以按序按值查找要从前往后遍历，时间复杂度为O(n),插入删除操作主要消耗在查找元素上。对给定结点，单链表后继直接插入删除为O(1),双链表则前驱后继都为O(1);
### 链表的基本操作：  
(此处为带头结点的操作)  
- 插入：  
~~~c++
	Lnode *p = (Lnode)malloc(sizeof(Lnode));
	if(Lnode->next == NULL)
		Lnode->next = p;
	if(Lnode->next != NULL)
		p->next = Lnode->next;
		Lnode->next = p;
		
