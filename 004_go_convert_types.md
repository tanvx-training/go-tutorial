            Golang Convert Types

# Type Conversion
- Quá trình chuyển đổi giá trị từ một kiểu dữ liệu sang một kiểu dữ liệu khác.
- Điều này thường xảy ra khi chúng ta muốn sử dụng giá trị của một biến với một kiểu dữ liệu khác hoặc khi thực hiện các phép toán giữa các kiểu dữ liệu khác nhau.
<br><hr>
## How to Convert string to integer and integer to string type in Go?
>1) Atoi() Function
- Bạn có thể sử dụng hàm Atoi() từ gói strconv để chuyển đổi một chuỗi thành một giá trị số nguyên.
- Hàm Atoi() là một phần của gói strconv trong Go và cung cấp một cách tiện lợi để thực hiện chuyển đổi này.
### Syntax
>func Atoi(s string) (int, error)
### Example
```
package main

import (
	"fmt"
	"strconv"
	"reflect"
)

func main() {
	strVar := "100"
	intVar, err := strconv.Atoi(strVar)
	fmt.Println(intVar, err, reflect.TypeOf(intVar))
}
```

>2) ParseInt() Function
### Syntax
>func ParseInt(s string, base int, bitSize int) (i int64, err error)

- s: Một chuỗi cần được giải thích (parse).
- base: Một số nguyên đặc trưng cho cơ số (hệ) của chuỗi cần giải thích. Nó có giá trị từ 0 đến 36, trong đó 0 đại diện cho cơ số được xác định tự động dựa trên định dạng của chuỗi đầu vào.
- bitSize: Kích thước bit của giá trị trả về, có giá trị từ 0 đến 64.
### Example
```
package main

import (
	"fmt"
	"reflect"
	"strconv"
)

func main() {
	strVar := "100"

	intVar, err := strconv.ParseInt(strVar, 0, 8)
	fmt.Println(intVar, err, reflect.TypeOf(intVar))

	intVar, err = strconv.ParseInt(strVar, 0, 16)
	fmt.Println(intVar, err, reflect.TypeOf(intVar))

	intVar, err = strconv.ParseInt(strVar, 0, 32)
	fmt.Println(intVar, err, reflect.TypeOf(intVar))

	intVar, err = strconv.ParseInt(strVar, 0, 64)
	fmt.Println(intVar, err, reflect.TypeOf(intVar))
}
```
>3) FormatInt() Method
- Hàm FormatInt chuyển đổi số nguyên i thành chuỗi với cơ số (base) đã chỉ định. Chuỗi kết quả sẽ sử dụng các ký tự chữ cái thường 'a' đến 'z' để biểu diễn các giá trị số từ 10 trở lên (nếu có), giống như cách được sử dụng trong các hệ số lớn hơn 10.
### Syntax
>func FormatInt(i int64, base int) string
### Example
```
package main

import (
	"fmt"
	"reflect"
	"strconv"
)

func main() {
	var i int64 = 125
	fmt.Println(reflect.TypeOf(i))
	fmt.Println(i)

	var s string = strconv.FormatInt(i, 10)
	fmt.Println(reflect.TypeOf(s))
	
	fmt.Println("Base 10 value of s:", s)
	
	s = strconv.FormatInt(i, 8)
	fmt.Println("Base 8 value of s:", s)
	
	s = strconv.FormatInt(i, 16)	
	fmt.Println("Base 16 value of s:", s)
	
	s = strconv.FormatInt(i, 32)	
	fmt.Println("Base 32 value of s:", s)
}
```
## How to Convert string to float and float to string type in Go?
>1) ParseFloat() Function
### Syntax
>func ParseFloat(s string, bitSize int) (float64, error)

- s: Một chuỗi cần được giải thích (parse) thành số dấu chấm động.
- bitSize: Kích thước bit của giá trị dấu chấm động trả về, có thể là 32 hoặc 64.
### Example
```
package main

import (
	"fmt"
	"reflect"
	"strconv"
)

func main() {
	s := "3.1415926535"
	f, err := strconv.ParseFloat(s, 8)
	fmt.Println(f, err, reflect.TypeOf(f))

	s1 := "-3.141"
	f1, err := strconv.ParseFloat(s1, 8)
	fmt.Println(f1, err, reflect.TypeOf(f1))

	s2 := "A-3141X"
	f2, err := strconv.ParseFloat(s2, 32)
	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println(f2, err, reflect.TypeOf(f2))
	}
}
```
>2) FormatFloat() Method
- Hàm FormatFloat chuyển đổi số dấu chấm động f thành chuỗi dựa trên các tham số định dạng và độ chính xác đã cho. Nó làm tròn kết quả dựa trên giả định rằng giá trị ban đầu được lấy từ một giá trị dấu chấm động có kích thước bit là bitSize.
### Syntax
>func FormatFloat(f float64, fmt byte, prec, bitSize int) string
- f: Số dấu chấm động cần được chuyển đổi thành chuỗi.
- fmt: Định dạng chuỗi của giá trị kết quả (ví dụ: g, f, e).
- prec: Số chữ số thập phân được giữ lại trong kết quả.
- bitSize: Kích thước bit của giá trị dấu chấm động f (32 cho float32, 64 cho float64).
### Example
```
package main

import (
	"fmt"
	"reflect"
	"strconv"
)

func main() {
	var f float64 = 3.1415926535
	fmt.Println(reflect.TypeOf(f))
	fmt.Println(f)

	var s string = strconv.FormatFloat(f, 'E', -1, 32)
	fmt.Println(reflect.TypeOf(s))
	fmt.Println(s)
}
```

## How to Convert string to boolean and boolean to string type in Go?
>1) ParseBool() Function
### Syntax
>func ParseBool(s string) (bool, error)

- "1" hoặc "t" hoặc "T" hoặc "TRUE" hoặc "true" hoặc "True": Trả về giá trị boolean true.
- "0" hoặc "f" hoặc "F" hoặc "FALSE" hoặc "false" hoặc "False": Trả về giá trị boolean false.
### Example
```
package main

import (
	"fmt"
	"strconv"
)

func main() {
	s1 := "true"
	b1, _ := strconv.ParseBool(s1)
	fmt.Printf("%T, %v\n", b1, b1)

	s2 := "t"
	b2, _ := strconv.ParseBool(s2)
	fmt.Printf("%T, %v\n", b2, b2)

	s3 := "0"
	b3, _ := strconv.ParseBool(s3)
	fmt.Printf("%T, %v\n", b3, b3)

	s4 := "F"
	b4, _ := strconv.ParseBool(s4)
	fmt.Printf("%T, %v\n", b4, b4)
}
```

>2) FormatBool() Method
- Hàm FormatBool chuyển đổi giá trị boolean b thành chuỗi. Nếu giá trị boolean là true, hàm trả về chuỗi "true". Nếu giá trị boolean là false, hàm trả về chuỗi "false".
### Syntax
>func FormatBool(b bool) string
- b: Giá trị boolean cần được chuyển đổi thành chuỗi.
### Example
```
package main

import (
	"fmt"
	"reflect"
	"strconv"
)

func main() {
	var b bool = true
	fmt.Println(reflect.TypeOf(b))

	var s string = strconv.FormatBool(true)
	fmt.Println(reflect.TypeOf(s))
}
```