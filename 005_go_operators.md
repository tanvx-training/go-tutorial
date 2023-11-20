            Golang Operators

# Operators
- Arithmetic Operators (Toán tử số học)
- Assignment Operators (Toán tử gán)
- Comparison Operators (Toán tử so sánh)
- Logical Operators (Toán tử logic)
- Bitwise Operators (Toán tử bitwise)

## Arithmetic Operators in Go Programming Language
- Các toán tử số học thực hiện các phép toán số học như cộng, trừ, nhân, chia và các phép toán khác.
- Ví dụ: +, -, *, /, % (phép chia lấy dư).
- 
```
| Operator | Description     | Example | Result                             |
|----------|-----------------|---------|------------------------------------|
| +        | Addition        | x + y   | Sum of x and y                     |
| -        | Subtraction     | x - y   | Subtracts one value from another   |
| *        | Multiplication  | x * y   | Multiplies two values              |
| /        | Division        | x / y   | Quotient of x divided by y         |
| %        | Modulus         | x % y   | Remainder of x divided by y        |
| ++       | Increment       | x++     | Increases the value of a variable by 1 |
| --       | Decrement       | x--     | Decreases the value of a variable by 1 |
```

### Example
```
package main

import "fmt"

func main() {
	var x, y = 35, 7

	fmt.Printf("x + y = %d\n", x+y)
	fmt.Printf("x - y = %d\n", x-y)
	fmt.Printf("x * y = %d\n", x*y)
	fmt.Printf("x / y = %d\n", x/y)
	fmt.Printf("x mod y = %d\n", x%y)

	x++
	fmt.Printf("x++ = %d\n", x)

	y--
	fmt.Printf("y-- = %d\n", y)
}
```

## Assignment Operators in Go Programming Language
- Các toán tử gán được sử dụng để gán giá trị cho biến. Ví dụ: =, +=, -=, *=, /= (gán, cộng và gán, trừ và gán, nhân và gán, chia và gán).

```
| Assignment | Description                  | Example        |
|------------|------------------------------|----------------|
| x = y      | Assign                       | x = y          |
| x += y     | Add and assign               | x = x + y      |
| x -= y     | Subtract and assign          | x = x - y      |
| x *= y     | Multiply and assign          | x = x * y      |
| x /= y     | Divide and assign quotient   | x = x / y      |
| x %= y     | Divide and assign modulus    | x = x % y      |
```

### Example

```
package main

import "fmt"

func main() {
	var x, y = 15, 25
	x = y
	fmt.Println("= ", x)

	x = 15
	x += y
	fmt.Println("+=", x)

	x = 50
	x -= y
	fmt.Println("-=", x)

	x = 2
	x *= y
	fmt.Println("*=", x)

	x = 100
	x /= y
	fmt.Println("/=", x)

	x = 40
	x %= y
	fmt.Println("%=", x)
}
```

## Comparison Operators in Go Programming Language
- Các toán tử so sánh so sánh hai giá trị và trả về một giá trị boolean (true hoặc false). Ví dụ: ==, !=, <, >, <=, >= (bằng, khác, nhỏ hơn, lớn hơn, nhỏ hơn hoặc bằng, lớn hơn hoặc bằng).

```
| Operator | Name                          | Example     | Result                                     |
|----------|-------------------------------|-------------|--------------------------------------------|
| ==       | Equal                         | x == y      | True if x is equal to y                    |
| !=       | Not equal                     | x != y      | True if x is not equal to y                |
| <        | Less than                     | x < y       | True if x is less than y                   |
| <=       | Less than or equal to         | x <= y      | True if x is less than or equal to y       |
| >        | Greater than                  | x > y       | True if x is greater than y                |
| >=       | Greater than or equal to      | x >= y      | True if x is greater than or equal to y   |
```

### Example
```
package main

import "fmt"

func main() {
	var x, y = 15, 25

	fmt.Println(x == y)
	fmt.Println(x != y)
	fmt.Println(x < y)
	fmt.Println(x <= y)
	fmt.Println(x > y)
	fmt.Println(x >= y)
}
```

## Logical Operators in Go Programming Language
- Các toán tử logic thực hiện các phép toán logic như AND, OR và NOT. Ví dụ: &&, ||, ! (AND, OR, NOT).

```
| Operator | Name          | Description                                             | Example                  |
|----------|---------------|---------------------------------------------------------|--------------------------|
| &&       | Logical And   | Returns true if both statements are true                | x < y && x > z          |
| \|\|      | Logical Or    | Returns true if one of the statements is true           | x < y \|\| x > z         |
| !        | Logical Not   | Reverse the result, returns false if the result is true | !(x == y && x > z)       |
```

### Example
```
package main

import "fmt"

func main() {
	var x, y, z = 10, 20, 30

	fmt.Println(x < y && x > z)
	fmt.Println(x < y || x > z)
	fmt.Println(!(x == y && x > z))
}
```

## Bitwise Operators in Go Programming Language
- Các toán tử bitwise thực hiện các phép toán bitwise trên các bit của các số nguyên. Ví dụ: &, |, ^, <<, >> (AND bitwise, OR bitwise, XOR bitwise, dịch trái, dịch phải).
```
| Operator | Name                   | Description                                                   |
|----------|------------------------|---------------------------------------------------------------|
| &        | AND                    | Sets each bit to 1 if both bits are 1                          |
| \|       | OR                     | Sets each bit to 1 if one of two bits is 1                     |
| ^        | XOR                    | Sets each bit to 1 if only one of two bits is 1                |
| <<       | Zero fill left shift   | Shift left by pushing zeros in from the right and let the leftmost bits fall off |
| >>       | Signed right shift     | Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off |
```
### Example
```
package main

import "fmt"

func main() {
	var x uint = 9  //0000 1001
	var y uint = 65 //0100 0001
	var z uint

	z = x & y
	fmt.Println("x & y  =", z) // x & y  = 1

	z = x | y
	fmt.Println("x | y  =", z) // x | y  = 73

	z = x ^ y
	fmt.Println("x ^ y  =", z) // x ^ y  = 72

	z = x << 1
	fmt.Println("x << 1 =", z) // x << 1 = 18

	z = x >> 1
	fmt.Println("x >> 1 =", z) // x >> 1 = 4
}
```
