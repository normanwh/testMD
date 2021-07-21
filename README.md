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
- 头插法建立单链表 
~~~c++
Lnode* List_HeadInsert(Lnode* &L)
{
	L = (Lnode*)malloc(sizeof(Lnode));//创建头结点
	L->next = NULL;//初始为空链表
	Lnode p = (Lnode*)malloc(sizeof(Lnode));//创建新结点
	int x;
	p->data = x;
	p->next = L->next;
	L->next = p;
	return L;
}
~~~
- 尾插法建立单链表
~~~c++
Lnode* List_TailInsert(Lnode* &L)
{
	int x;
	L = (Lnode*)malloc(sizeof(Lnode));//头结点
	*r = L;//r指向表尾
	Lnode* p = (Lnode*)malloc(sizeof(Lnode));
	s->data = x;
	r->next = s;
	r = s;//指向表尾
	r->next = NULL;
	return L;
}
~~~
- 按序号查找结点值
~~~c++
Lnode* GetElem(Lnode* L,int i)
{
	int j = 1;
	Lnode *p = L->next;
	if (i == 0)
		return L;
	if (i < 1)
		return NULL;
	while(p && j < i)
	{
		p = p->next;
		j++;
	}
	return p;
}
~~~
- 按值查找表结点
~~~c++
Lnode* LocateElem(Lnode* L,ElemType e)
{
	Lnode* p = L->next;
	while(p != NULL && p->data != e)
		p = p->next;
	return p;
}
~~~
- 插入结点操作

~~~c++
p = GetElem(L,i-1);
s->next = p->next;
p->next = s;
~~~
---
# 栈和队列  
> 顺序栈  
~~~c++
typdef struct 
{
	ElemType data[MAXSIZE]
	int top;
}Sqstack;
~~~
- 初始化栈
~~~c++
void InitStack(SqStack &S)
{
	S.top == -1;
}
~~~
- 判栈空
~~~c++
void StackEmpty(SqStack &S)
{
	if (S.top == -1)
		return true;
	if (S.top != -1)
		return false;
}
~~~

