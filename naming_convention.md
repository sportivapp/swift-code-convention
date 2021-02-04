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
### 4. Hindari Controller dalam nama kelas yang bukan pengontrol tampilan.

**Salah:**
```swift
AnimationController
CameraController
PermissionController
```
**Baik:**
```swift
AnimationManager
CameraManager
PermissionManager
```

### 5. Tambahkan tanda koma pada elemen terakhir dari larik multi-baris.

**Salah:**
```swift
func whatever() -> (Int, Int) {
    return (4, 4)
}
let thing = whatever()
print(thing.0)
```
**Baik:**
```swift
func whatever() -> (x: Int, y: Int) {
    return (x: 4. y: 4)
}
```
**Ini Oke**
```swift
func whatever2() -> (x: Int, y: Int) {
    return (x: 4. y: 4)
}
```
```swift
let coord = whatever()
coord.x
coord.y
```

### 6. Outlet harus diawali dengan singkatan tipe tampilan
**Sample:**
```swift
lblTitle → UILabel
txtPassword →>UITextField
txtEmail
btnOK → UIButton
viewContainer → UIView
tblSchedule → UITableView
colCalendar → UICollectionView
```
### 7. Pemberian Nama sebaiknya ditulis dengan bagian General terlebih dahulu kemudian bagian Spesifik terakhir.
**Salah:**
```swift
let rightTitleMargin: CGFloat
let leftTitleMargin: CGFloat
let bodyRightMargin: CGFloat
let bodyLeftMargin: CGFloat
```
**Benar:**
```swift
let titleRightMargin: CGFloat
let titleLeftMargin: CGFloat
let bodyMarginRight: CGFloat
let bodyMarginLeft: CGFloat
```
### 8. Fungsi Event-Handling harus diberi nama seperti kalimat bentuk Lampau.
**Salah:**
```swift
class ExperienceViewController {
    private func handleBookButtonTap(){
        //...
    }
    private func modelChanged(){
        //...
    }
}
```
**Benar:**
```swift
class ExperienceViewController {
    private func didTapBookButton(){
        //...
    }
    private func modelDidChanged(){
        //...
    }
}
```