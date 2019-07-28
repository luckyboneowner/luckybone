
# 常用命令
```
# 配置GOPATH环境变量,路径下的src,bin目录分别放源码和可执行文件

# 直接执行,直接在.go文件所在目录下执行
go run hello

# 编译 需要配置GOPATH
go build hello
# 按照src的模块(hello),在bin下生成可执行文件 需要配置GOPATH
go install hello

```
# 快速入门示例
```
//声明一个工作空间
package main

import "fmt"
import "math/rand"
import "math"
import "math/cmplx"

//常量 const 不使用:= 可以是字符 字符串 布尔 或数值
const Pi = 3.14
const (
    Big = 1 << 100
    Small = Big >> 99
)
//变量声明var 类型写最后;如果已经有了初始值, 那么类型可以省略
/*
类型:
bool
string
int, int8, int16, int32, int64
uint, uint8, uint16, uint32, unint64, uintptr
byte //uint8的别名
rune //int32的别名 表示一个Unicode码点
float32
float64
complex64, complex128 //复数
int, uint 和 uintptr 在 32 位系统上通常为 32 位宽，在 64 位系统上则为 64 位宽。
*/
var c, python, java bool
var i_int, i_str = 1, "Hi"

//函数func
/*注释同C语言*/
//函数左括号{,要和函数名称同一行
//变量类型写后面...
func add(x int, y int) int {
    return x + y
}

func swap(x, y string)(string, string) {
    return y, x
}

/* Go的返回值可被命名, 被视为定义在函数顶部的变量
没有参数的return语句返回已命名的返回值.
*/
func split(sum int) (x int) {
    x = sum * 4 / 9
    //y = sum - x
    return
}

func needInt(x int) int {
    return x * 10 + 1
}

func needFloat(x float64) float64 {
    return x * 0.1
}
func main(){
    fmt.Println("My number is", rand.Intn(10))
    fmt.Printf("Now you have %g problem.\n", math.Sqrt(7))
    fmt.Println(math.Pi)
    fmt.Println(add(1,3))
    a, b := swap("My", "Go")
    fmt.Println(a, b)
    fmt.Println(split(9))
    
    var i int
    //这种赋值 只能在函数内使用, 有初值就不用var变量
    k := 1.1
    kk := k
    fmt.Println(i, c, python, java)
    fmt.Println(i_int, i_str, kk, k)
    var (
        ToBe bool = false
        MaxInt uint64 = 1<<64 -1
        z complex128 = cmplx.Sqrt(-5 + 12i)
    )
    //%T表示类型,v表示值--好直观
    fmt.Printf("Type: %T Value: %v\n", ToBe, ToBe)
    fmt.Printf("Type: %T Value: %v\n", MaxInt, MaxInt)
    fmt.Printf("Type: %T Value: %v\n", z, z)
    //不同类型的项之间赋值时需要显示转换 T(v),如果不指定类型, 则右值推导
    
    fmt.Println("--------")
    fmt.Println(needInt(Small))
    fmt.Println(needFloat(Small))
    //fmt.Println(needInt(Big))
    fmt.Println(needFloat(Big))
}
```

# 参考链接
[参考教程](http://c.biancheng.net/golang/)  
[快速入门](https://zhuanlan.zhihu.com/p/63537336)  
[在线运行](https://www.runoob.com/try/runcode.php?filename=helloworld&type=go)  
[官网地址](https://golang.google.cn/)