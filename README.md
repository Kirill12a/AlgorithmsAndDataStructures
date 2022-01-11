# AlgorithmsAndDataStructures
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
