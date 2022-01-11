# AlgorithmsAndDataStructures

## Стек
> Стек (англ. stack – стопка) – это структура данных, в которой новый элемент всегда записывается в ее начало (вершину) и очередной читаемый элемент также всегда
> выбирается из ее начала. В стеках используется метод доступа к элементам LIFO (Last Input – First Output, "последним пришел – первым вышел").
```swift
class Stack<T>{
    private var array: [T]=[]
    
    init (elements: [T]){
        array = elements
    }
    
    func push(element: T){
        array.append(element)
    }
    
    func pop()->T?{
        return array.removeLast()
    }
}


var array = Stack(elements: [1,24,5,64,32,52])
array.pop()
```

![изображение](https://user-images.githubusercontent.com/45273279/148935620-9f3ed50f-b569-4cdb-a5ce-85d40eba4937.png)

## Очередь
>Очередь – это динамическая структура данных которая состоит из набора элементов которые размещены последовательно друг за другом. При этом добавление элементов >осуществляется с одной стороны, а удаление (вытягивание) – с другой стороны. Очередь работает по принципу FIFO (First In — First Out), то есть «первым пришел – первым вышел».

```swift
class Queu<T>{
    private var array: [T]=[]

    init (elements: [T]){
        array = elements
    }
    
    func push(element: T){
        array.append(element)
    }
    
    func pop()->T?{
        return array.removeFirst()
    }
}
var queu = Queu(elements: [1,2,4,6,3,6,7,8,9])
queu.pop()
queu.push(element: 3)
```
![изображение](https://user-images.githubusercontent.com/45273279/148936661-e6d574dc-683b-42b9-8d5f-6d65e922cc9d.png)


## Бинарное дерево (англ. binary tree) — это упорядоченное корневое дерево, у каждой вершины которого имеется не более двух сыновей. В бинарном дереве каждый сын произвольной вершины определяется как левый или правый.
```swift
class TreeNode<T>{
    var value: T
    
    var left: TreeNode<T>?
    var right: TreeNode<T>?
    
    init(value: T){
        self.value = value
    }
}
let top = TreeNode(value: 8)
let left = TreeNode(value: 3)
let right = TreeNode(value: 10)
top.left = left
top.right = right

  //    0
 //    / \
//    3  10

```
![изображение](https://user-images.githubusercontent.com/45273279/148937255-ab0e0226-5f97-4ca1-a6af-9288ea745e4a.png)

