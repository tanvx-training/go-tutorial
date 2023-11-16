            Golang Variables

### Variables
- Biến là một phần của bộ nhớ được sử dụng để tạm thời lưu trữ dữ liệu, giúp chương trình có thể làm việc với nó.
- Trong Golang, có một dạng chung để khai báo biến. Cụ thể, ngôn ngữ sử dụng từ khóa var, một kiểu dữ liệu rõ ràng và một phép gán. <br/>
Ví dụ: var myVariable int = 10; sẽ khai báo một biến có tên là myVariable kiểu dữ liệu là int và có giá trị ban đầu là 10.
<br><hr>
### Variable Declaration with Initialization
- Nếu bạn đã biết trước giá trị của một biến, bạn có thể khai báo biến và gán giá trị cho nó trong cùng một dòng mã.

```
package main

import "fmt"

func main() {
	var i int = 10
	var s string = "Canada"

	fmt.Println(i)
	fmt.Println(s)
}
```

- var i int = 10: Đây là cách khai báo một biến có tên là i kiểu dữ liệu là int và khởi tạo giá trị là 10.
- var s string = "Canada": Tương tự, đây là cách khai báo một biến có tên là s kiểu dữ liệu là string và khởi tạo giá trị là chuỗi "Canada".

> Trong Go, ngôn ngữ này có đặc tính "strong static typing", có nghĩa là bạn cần phải chỉ định kiểu dữ liệu của biến khi bạn khai báo nó.
> Việc này giúp tăng tính chắc chắn của chương trình và giảm số lượng lỗi liên quan đến kiểu dữ liệu trong quá trình thực thi.

### Variable Declaration without Initialization
- Khai báo một biến trong Go, sử dụng từ khóa var, theo sau là tên biến và kiểu dữ liệu của biến.
```
package main

import "fmt"

func main() {
	var i int
	var s string

	i = 10
	s = "Canada"

	fmt.Println(i)
	fmt.Println(s)
}
```

- Trong đoạn này, hai biến được khai báo.
    - Biến i được khai báo với kiểu dữ liệu là int.
    - Biến s được khai báo với kiểu dữ liệu là string.
- Lưu ý rằng tại thời điểm này, chúng chỉ được khai báo (declaration) mà không có giá trị khởi tạo
>Biến i và s chưa được gán giá trị có ý nghĩa nào cả. Điều này có nghĩa là chúng chỉ là các ô nhớ có thể chứa dữ liệu, nhưng chưa có giá trị cụ thể được gán cho chúng

- Tiếp theo trong mã chương trình, giá trị được gán cho các biến i và s.
    - i được gán giá trị là 10, là một số nguyên.
    - s được gán giá trị là "Canada", là một chuỗi ký tự.

### Variable Declaration with type inference
- Trong Go, nếu bạn gán giá trị cho biến ngay từ lúc khai báo, bạn có thể lược bỏ phần chỉ định kiểu dữ liệu của biến
- Trong trường hợp này, kiểu dữ liệu của biến sẽ được hệ thống suy luận (type inference) dựa trên giá trị được gán cho biến.
- Điều này giúp làm cho mã nguồn ngắn gọn hơn và giảm cần phải lặp lại thông tin kiểu dữ liệu.


```
package main

import (
	"fmt"
	"reflect"
)

func main() {
	var i = 10
	var s = "Canada"

	fmt.Println(reflect.TypeOf(i))
	fmt.Println(reflect.TypeOf(s))
}
```
- Trong đoạn mã này, hai biến i và s được khai báo và ngay lập tức được khởi tạo giá trị.
- Biến i được khởi tạo với giá trị nguyên 10.
- Biến s được khởi tạo với giá trị chuỗi "Canada".

>Ngôn ngữ Go hỗ trợ suy luận kiểu dữ liệu, nghĩa là bạn không cần phải đặc biệt chỉ định kiểu dữ liệu khi khởi tạo biến nếu giá trị đã được xác định.

- Đoạn mã sử dụng gói reflect trong thư viện chuẩn của Go để xác định kiểu dữ liệu của biến tại thời điểm chạy.
    - Hàm reflect.TypeOf(i) trả về kiểu dữ liệu của biến i, trong trường hợp này là int.
    - Hàm reflect.TypeOf(s) trả về kiểu dữ liệu của biến s, trong trường hợp này là string.
  
### Multiple Variable Declaration

- Trong Golang, bạn có thể khai báo và khởi tạo giá trị cho nhiều biến trong một dòng mã.

```
package main

import (
	"fmt"
)

func main() {
	var fname, lname string = "John", "Doe"
	m, n, o := 1, 2, 3
	item, price := "Mobile", 2000

	fmt.Println(fname + lname)
	fmt.Println(m + n + o)
	fmt.Println(item, "-", price)
}
```

- Ví dụ đầu tiên sử dụng hai biến chuỗi fname và lname được khai báo và khởi tạo cùng một lúc. fname được gán giá trị "John" và lname được gán giá trị "Doe".
- Ví dụ thứ hai sử dụng cú pháp khai báo ngắn gọn := để khai báo và khởi tạo ba biến số nguyên m, n, và o. Các biến này được gán giá trị 1, 2, và 3 tương ứng.
- Ví dụ thứ ba khai báo và khởi tạo hai biến item (kiểu chuỗi) và price (kiểu số nguyên). Biến item được gán giá trị "Mobile" và biến price được gán giá trị 2000.

### Short Variable Declaration

- Trong Golang, toán tử := được gọi là "short variable declaration operator" và nó được sử dụng để khai báo và gán giá trị cho một biến ngắn gọn.
- Sử dụng toán tử := giảm bớt cần phải sử dụng từ khóa var và chỉ định kiểu dữ liệu của biến một cách rõ ràng.

```
package main

import (
	"fmt"
	"reflect"
)

func main() {
	name := "John Doe"
	fmt.Println(reflect.TypeOf(name))
}
```

>Toán tử := giúp viết mã nguồn ngắn gọn hơn và giảm sự lặp lại bằng cách tự động suy luận kiểu dữ liệu của biến từ giá trị được gán cho nó.

### Scope of Golang Variables Defined by Brace Brackets

- Trong ngôn ngữ lập trình Go, "phạm vi" của một biến xác định khu vực trong mã nguồn mà biến đó có thể truy cập được.
- Phạm vi của biến được xác định bởi nơi mà biến được khai báo.
  - Nếu một biến được khai báo bên trong một khối mã (block), như là một hàm, hoặc một cấu trúc điều khiển như if, for, hoặc switch, thì biến đó chỉ có thể truy cập được bên trong khối đó và bất kỳ khối lồng bên trong nếu có.
  - Một khi quá trình thực thi thoát khỏi khối đó, biến sẽ ra khỏi phạm vi và không thể truy cập được nữa.
```
package main

import (
	"fmt"
)

var s = "Japan"

func main() {
	fmt.Println(s) // Accessing the global variable 's' and printing its value
	x := true      // Declaring and initializing a local variable 'x'
    
	if x { // If 'x' is true, execute the block of code inside the if statement
		y := 1 // Declaring and initializing a local variable 'y' inside the if block
        
		if x != false { // If 'x' is not false, execute the block of code inside the if statement
			fmt.Println(s) // Accessing the global variable 's' and printing its value
			fmt.Println(x) // Printing the value of local variable 'x'
			fmt.Println(y) // Printing the value of local variable 'y'
		}
	}
    
	fmt.Println(x) // Printing the value of local variable 'x'
}
```

>Trong ví dụ này, s là biến toàn cục, x là biến cục bộ của hàm main, và y là biến cục bộ của khối if đầu tiên. Biến s có thể truy cập từ mọi nơi trong chương trình, trong khi x chỉ có thể truy cập trong hàm main và y chỉ có thể truy cập trong khối if đầu tiên và các khối if lồng bên trong nó.

### Zero value in Golang

- Trong trường hợp bạn khai báo một biến mà không gán giá trị, Go sẽ tự động gán giá trị mặc định cho biến đó. Giá trị mặc định này thường được gọi là "zero-value."
- Giá trị mặc định của một biến phụ thuộc vào kiểu dữ liệu của biến. Ví dụ, giá trị mặc định của một biến kiểu số nguyên (int) là 0, của kiểu dấu chấm động (float64) là 0.0, và của kiểu chuỗi (string) là "" (chuỗi rỗng).

```
package main

import "fmt"

func main() {
	var quantity float32
	fmt.Println(quantity)

	var price int16
	fmt.Println(price)

	var product string
	fmt.Println(product)

	var inStock bool
	fmt.Println(inStock)
}
```
>0 <br/>
>0
>
>false

### Golang Variable Declaration Block

- Trong Go, bạn có thể nhóm nhiều biến cùng một loại hoặc liên quan vào trong một khối (block).
- Việc nhóm biến giúp tăng khả năng đọc mã nguồn bằng cách tạo ra các nhóm logic, liên quan đến nhau, thay vì khai báo biến một cách riêng lẻ.

```
package main

import "fmt"

var (
	product  = "Mobile"
	quantity = 50
	price    = 50.50
	inStock  = true
)

func main() {
	fmt.Println(quantity)
	fmt.Println(price)
	fmt.Println(product)
	fmt.Println(inStock)
}
```

Trong ví dụ, có một nhóm biến toàn cục được khai báo:
- product (kiểu string): Biến này chứa tên sản phẩm, được gán giá trị là "Mobile".
- quantity (kiểu int): Biến này chứa số lượng sản phẩm, được gán giá trị là 50.
- price (kiểu float64): Biến này chứa giá của sản phẩm, được gán giá trị là 50.50.
- inStock (kiểu bool): Biến này chứa một giá trị boolean, biểu thị tình trạng hàng tồn kho, được gán giá trị là true (sản phẩm có sẵn trong kho).
