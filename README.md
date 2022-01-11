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

## Бинарное дерево
> Бинарное дерево (англ. binary tree) — это упорядоченное корневое дерево, у каждой вершины которого имеется не более двух сыновей. В бинарном дереве каждый сын  
> произвольной вершины определяется как левый или правый.
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
![изображение](https://user-images.githubusercontent.com/45273279/148937397-92a6583d-3df2-4c8a-b7c8-f4ed9ea548c9.png)

## Граф
> Граф - это топологичекая модель, которая состоит из множества вершин и множества соединяющих их рёбер. При этом значение имеет только сам факт, какая вершина с 
> какой соединена.

```swift
class Edge<T, U>{//ребра
    var label: U
    var vertex: Vertex<T>

    init(label: U, vertex: Vertex<T>){
        self.label = label
        self.vertex = vertex
    }
}

class Vertex<T, U>{ 
    var value: T
    var edges: [Edge<T,U>]

    init(value: T, edges: [Edge<T, U>]){
        self.value = value
        self.edges = edges
    }
}

```
![Снимок экрана 2022-01-11 в 14 53 53](https://user-images.githubusercontent.com/45273279/148938121-59e4cfdf-0aae-4e46-8a6b-91c81317ed60.png)



```swift
## Сортировка

extension Array where Element: Comparable{
    // Сортировка пузырьком
    func bubbleSort()->[Element]{
        var array = self
        for i in (0..<array.count-1).reversed(){
            for j in (1..<(i+1)){
                if array[j-1]>array[j]{
                    let temp = array[j-1]
                    array[j-1] = array[j]
                    array[j] = temp
                }
            }
        }
        return array
    }
    
//    Сортировка выбором
    func selectionSort() -> [Element]{
        var array = self
        for i in 0..<array.count - 1{
            var minIndex = i
            for j in (i+1..<array.count){
                if array[j] < array[minIndex]{
                    minIndex = j
                }
            }
            let temp = array[minIndex]
            array[minIndex] = array[i]
            array[i] = temp
        }
        return array

    }
    
}
[0,12,41,1,2,3,5,6].bubbleSort() 
[0,12,41,1,2,3,5,6].selectionSort()

```
