# AlgorithmsAndDataStructures

Стек
> Стек (англ. stack – стопка) – это структура данных, в которой новый элемент всегда записывается в ее начало (вершину) и очередной читаемый элемент также всегда
> выбирается из ее начала (рис. 30.1). В стеках используется метод доступа к элементам LIFO (Last Input – First Output, "последним пришел – первым вышел").
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
