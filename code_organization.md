## Organisasi Kode

Gunakan ekstensi untuk mengatur kode Anda ke dalam blok fungsionalitas logis. Setiap ekstensi harus diberi tanda `// MARK: -` komentar agar semuanya teratur.

### Kesesuaian Protokol

Secara khusus, saat menambahkan kesesuaian protokol ke model, lebih suka menambahkan ekstensi terpisah untuk metode protokol. Ini membuat metode terkait dikelompokkan bersama dengan protokol dan dapat menyederhanakan instruksi untuk menambahkan protokol ke kelas dengan metode yang terkait. 

**Preferred**:
```swift
class MyViewController: UIViewController {
  // class stuff here
}

// MARK: - UITableViewDataSource
extension MyViewController: UITableViewDataSource {
  // table view data source methods
}

// MARK: - UIScrollViewDelegate
extension MyViewController: UIScrollViewDelegate {
  // scroll view delegate methods
}
```
**Not Preferred**:
```swift
class MyViewController: UIViewController, UITableViewDataSource, UIScrollViewDelegate {
  // all methods
}
```

Karena kompilator tidak mengizinkan Anda untuk mendeklarasikan ulang kesesuaian protokol dalam kelas turunan, maka tidak selalu diperlukan untuk mereplikasi grup ekstensi dari kelas dasar. Ini terutama benar jika kelas turunan adalah kelas terminal dan sejumlah kecil metode sedang diganti. Kapan mempertahankan grup penyuluhan diserahkan kepada kebijaksanaan penulis.

Untuk pengontrol tampilan UIKit, pertimbangkan untuk mengelompokkan siklus proses, pengakses kustom, dan IBAction dalam ekstensi kelas terpisah. 

### Unused Code / Dead Code

Kode yang tidak digunakan (mati), termasuk kode template Xcode dan komentar placeholder harus dihapus. Pengecualian adalah ketika tutorial atau buku Anda menginstruksikan pengguna untuk menggunakan kode yang diberi komentar.

Metode aspirasional yang tidak terkait langsung dengan tutorial yang implementasinya hanya memanggil superclass juga harus dihapus. Ini termasuk metode UIApplicationDelegate kosong / tidak terpakai. 

**Preferred**:
```swift
override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
  return Database.contacts.count
}
```

**Not Preferred**:
```swift
override func didReceiveMemoryWarning() {
  super.didReceiveMemoryWarning()
  // Dispose of any resources that can be recreated.
}

override func numberOfSections(in tableView: UITableView) -> Int {
  // #warning Incomplete implementation, return the number of sections
  return 1
}

override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
  // #warning Incomplete implementation, return the number of rows
  return Database.contacts.count
}
```

### Minimal Imports

Impor hanya modul yang dibutuhkan file sumber. Misalnya, jangan impor `UIKit` karena mengimpor` Foundation` sudah cukup. Demikian juga, jangan impor `Fondasi` jika Anda harus mengimpor` UIKit`. 

**Preferred**:
```
import UIKit
var view: UIView
var deviceModels: [String]
```

**Preferred**:
```
import Foundation
var deviceModels: [String]
```

**Not Preferred**:
```
import UIKit
import Foundation
var view: UIView
var deviceModels: [String]
```

**Not Preferred**:
```
import UIKit
var deviceModels: [String]
```