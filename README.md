# flatcat
flatten an array swift style

```swift
import UIKit

func flattenArray(array:[Any]) -> [String] {
    var flatArray = [String]()
    for item in array {
        if let intItem = item as? String {
            flatArray.append(intItem)
        }
        
        if let arrayItem = item as? [Any] {
            for intItem in flattenArray(array: arrayItem) {
                flatArray.append(intItem)
            }
        }
    }
    return flatArray
}


let result = flattenArray(array:["Russle","Snapjacks","Grumpy-face",["Stinkster","Steve French",["Duke","Steve Austin"]],[[["Paw McCatny"]]],[],"Ner Ner"])
print("new array:", result)
```
