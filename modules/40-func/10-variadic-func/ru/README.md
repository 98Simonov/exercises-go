
Последний аргумент функции может быть вариативным. Функция может иметь максимум один вариативный аргумент и этот аргумент всегда слайс. Чтобы обозначить аргумент вариативным, нужно поставить три точки `...` перед его типом:

```go
package main

import (
	"fmt"
)

func main() {
	// кол-во аргументов может быть любым
	PrintNums(1, 2, 3)
}


func PrintNums(nums ...int) {
	for _, n := range nums {
		fmt.Println(n)
	}
}
```

Также тремя точками можно разбить слайс на элементы при передаче в вариативную функцию. Например, встроенный метод `append(slice []Type, elems ...Type) []Type`, который добавляет последний элемент в слайс, принимает вариативный аргумент `elems ...Type`. Чтобы добавить один слайс в конец другого, нужно разбить второй слайс на элементы путем добавления трех точек `...` после переменной:

```go
nums1 := []int{1,2,3,4,5}

nums2 := []int{6,7,8,9,10}

res := append(nums1, nums2...) // [1 2 3 4 5 6 7 8 9 10]
```