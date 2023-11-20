            Golang Variables

### Constants
- Hằng số được sử dụng để biểu diễn các giá trị cố định và không thay đổi, trong khi biến được sử dụng để biểu diễn các giá trị có thể biến đổi
<br><hr>
### Declaring (Creating) Constants
- Trong ngôn ngữ lập trình Go (Golang), từ khóa const được sử dụng để khai báo hằng số.

```
package main

import "fmt"

const PRODUCT string = "Canada"
const PRICE = 500

func main() {
	fmt.Println(PRODUCT)
	fmt.Println(PRICE)
}
```

- Một điểm quan trọng là bạn phải gán giá trị cho hằng số ngay từ lúc khai báo. Không giống như biến, bạn không thể gán giá trị cho hằng số sau khi nó đã được khai báo.
- Điều này đảm bảo rằng giá trị của hằng số sẽ không bao giờ thay đổi trong suốt quá trình chạy của chương trình.
### Multilple Constants Declaration Block
- Khai báo hằng số có thể được nhóm lại với nhau thành các khối hoặc nhóm trong mã nguồn.

```
package main

import "fmt"

const (
	PRODUCT  = "Mobile"
	QUANTITY = 50
	PRICE    = 50.50
	STOCK  = true
)

func main() {
	fmt.Println(QUANTITY)
	fmt.Println(PRICE)
	fmt.Println(PRODUCT)
	fmt.Println(STOCK)
}
```

- Mục đích của việc nhóm các khai báo hằng số lại là để cải thiện "readability" (khả năng đọc hiểu) và "code quality" (chất lượng mã nguồn).
- Khi các khai báo hằng số được sắp xếp theo cách tổ chức, người đọc mã nguồn có thể dễ dàng định vị và hiểu các hằng số liên quan đến nhau. Điều này giúp giảm sự rối bời trong mã nguồn và làm cho nó dễ đọc hơn, đồng thời cải thiện chất lượng của mã nguồn.

### Naming Conventions for Golang Constants
- "Theo quy ước, tên của hằng số thường được viết bằng chữ cái in hoa." - Điều này là để dễ dàng phân biệt hằng số từ biến khi đọc mã nguồn.
- Việc sử dụng chữ cái in hoa là một quy ước ngôn ngữ lập trình giúp nâng cao khả năng nhận biết và phân biệt giữa hằng số và biến trong mã nguồn.