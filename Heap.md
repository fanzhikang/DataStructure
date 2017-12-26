# Heap

## 最大堆创建

~~~c
typedef struct HeapStruct *MaxHeap;
struct HeadStruct{
  ElementType *Elements;
  int size;
  int Capacity;
}
~~~

~~~c
MaxHeap Create(int Maxsize)
  {
    MaxHeap H = malloc(sizeof(struct HeapStruct));
  H->Elements = malloc(sizeof(Elementtype)*(Maxsize+1));
  H->size=0;
  H->capacity = Maxsize;
  H->elements[0]=MaxData;//哨兵(最大)
  return H;
  }
~~~

## 插入

~~~c
void insert(MaxHeap H,Elementtype item){
  int i;
  if(isfull(H)){
    printf("");
  }
  i=++H->size;
  for(;H->Elements[i/2]<item;i/=2)
    H->Elements[i]=H->Elements[i/2];
  H->Elements[i]=item;
}
~~~

**时间复杂度:O(log N)**

## 删除

~~~ c
ElementType DeleteMax(MaxHeap H){
  int Parent,Child;
  ElementType Maxitem,temp;
  if(isEmpty()){
    return ;
  }
  MaxItem = H->Elements[1];
  temp = H->Elements[H->size--];
  for(Parent=1;Parent*2<=H->size;Parent=Child){
    Child = Parent*2;
    if(child!=H->size&& (H->Elements[child]<H->Elements[child+1]))
      child++;
    if(temp>=H->elements[child]) break;
    else 
      H->elements[parent]=H->elements[child];
  }
  H->elements[parent]=temp;
  return MaxItem;
}
~~~

