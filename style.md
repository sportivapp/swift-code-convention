## Code Styling

### 1. Jangan Menggabungkan Type Data dimana itu definisikan

```swift
// WRONG
let host: Host =  Host()

// RIGHT
let host: Host()
```

```swift
enum Direction {
    case left
    case right
}
```
```swift
// WRONG
return Direction.left

// RIGHT
return.left
```

### 2. Jangan Gunakan Self selain adanya ambiguitas / diperlukan oleh bahasanya.
```swift
final class Listing {
    
    init(capacity: Int, allowsPets: Bool) {
        // WRONG
        self.capacity = capacity
        self.isFamilyFriendly = !allowPets // 'self'. bit required here

        // RIGHT
        self.capacity = capacity
        isFamilyFriendly = !allowPets 
    }

    private let isFamilyFriendly:Bool
    private var capacity: Int

    private func increaseCapacity(by amount: Int) {
       // WRONG
        self.capacity += amount
        
        //RIGHT
        capacity += amount

        // WRONG
        self.save()

        //RIGHT
        save()
    }
}
```
### 3. Tambahkan comma di elemen terakhir dari multi-line array.

```swift
//WRONG
let rowContent = [
    listingUrgentDatesRowContent(),
    listingUrgentBookedRowContent(),
    listingUrgentBookedShortRowContent()
]

//RIGHT
let rowContent = [
    listingUrgentDatesRowContent(),
    listingUrgentBookedRowContent(),
    listingUrgentBookedShortRowContent(),
]
```

### 4. Beri nama bagi tuples agar tidak membinggungkan.

```swift
//WRONG
func whatever() ->(Int, Int) {
    return(4, 4)
}
let thing = whatever()
print(thing.0)

//RIGHT
func whatever() -> (x: Int, y: Int) {
    return (x: 4, y: 4)
}

// THIS IS ALSO OKAY
func whatever2() -> (x: Int, y: Int) {
    let x = 4
    let y = 4
    return (x, y)
}

let coord = whatever()
coord.x
coord.y
```
### 5. Beri colon setelah identifier, dilanjutkan oleh spasi.

```swift
//WRONG
var dict = [KeyType:ValueType]()
var dict = [KeyType : ValueType]()

//RIGHT
var dict = [KeyType: ValueType]()
```

```swift
//WRONG
var a : Double = 0

//RIGHT
var a: Double = 0
```

```swift
//WRONG
class MyClass : SuperClass {
    // ...
}

//RIGHT
class MyClass: SuperClass {
    // ...
}
```

### 6. Pakai Constructors dari pada Make() functions untuk NSRange dan yang lain.

```swift
//WRONG
let range = NSMakeRange(10, 5)

//RIGHT
let range = NSRange(location: 10, length: 5)
```

### 7. Berikan spasi di antara panah kembali untuk mempermudah bacaan.

```swift
//WRONG
func doSomething(completion: ()->Void) {
    //...
}

//RIGHT
func doSomething(completion: () -> Void) {
    //...
}
```
```swift
//WRONG
func doSomething()->String {
    //...
}

//RIGHT
func doSomething() -> String {
    //...
}
```