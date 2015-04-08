# Shell-Sort
Shell sort implementation in swift.


```Swift

import Foundation

let arr = [22,7,2,-5,8,400,32,321,1,1,1,2,1,2,23,2141]

func shellSort(var arr:[Int]) -> [Int] {
    
    var inc = arr.count / 2
    
    while inc > 0 {
        for var i = inc; i < arr.count; ++i {
            var j = i
            let temp = arr[i]
            while (j >= inc && arr[j - inc] > temp) {
                arr[j] = arr[j - inc]
                j = j - inc
            }
            arr[j] = temp
        }
        
        if (inc == 2) {
            inc = 1
        } else {
            inc = Int(Double(inc) * (5.0 / 11))
        }
    }
    
    return arr
}

println(shellSort(arr))
```
