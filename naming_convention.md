## Naming Convention

### 1. Gunakan PascalCase untuk nama dan Protokol, dan lowerCaseCase untuk yang lainnya.

```swift
protocol SpaceThing{
// ...
}

class SpaceFleet: SpaceThing {
    enum Formation {
        //...
    }
    class Spaceship {
        //...
    }
    var ships: [Spaceship] = []
    static let worldName: String = "Earth"

    func addShip(_ ship: Spaceship) {
        //...
    }
}

let myFleet = SpaceFleet()
```
### 2. Nama booleans seperti isSpaceship, hasSpacesuit, etc.

this makes it clear that they are booleans and not other types.

### 3. Akronim dalam nama (mis. URL) menggunakan huruf besar semua kecuali jika itu adalah awal dari nama yang seharusnya lebih rendahCamelCase, dalam hal ini harus sama huruf kecil.

```swift
class URLValidator {
    func isValidUrl(_ URL: URL) -> bool {
        //...
    }
    func isProfileUrl(_) URL: URL. for userId: String) -> Bool {
        //...
    }
}
let URLValidator = UrlValidator()
let isProfile = URLValidator.IsProfilerUrl(URLToTest, userId: IDofUser)
```