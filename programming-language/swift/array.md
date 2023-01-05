# Array

### Different ways to construct array

```swift
var scores = Array<Int>()
scores.append(100)
scores.append(80)
scores.append(85)
print(scores[1])
// 80
```

```swift
var albums = [String]()
albums.append("Folklore")
albums.append("Fearless")
albums.append("Red")
```

#### with initial values

```swift
var albums = ["Folklore"]
albums.append("Fearless")
albums.append("Red")
```

### Remove

```swift
var characters = ["Lana", "Pam", "Ray", "Sterling"]
print(characters.count)

characters.remove(at: 2)
print(characters.count)

characters.removeAll()
print(characters.count)

// 4
// 3
// 0
```
