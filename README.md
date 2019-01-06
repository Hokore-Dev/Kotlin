# Kotlin
코틀린 공부하면서 대충 적어둔 내용

## 변수와 상수

변수
- 값을 담을 수 있는 그릇
- 값을 다른 값으로 바꿀 수 있음
- 초기값 필요하지 않음
- var 선언

숫자, 글자,논리값,배열,문자열

숫자
Byte(8bit) -128 ~ 127
Short(16bit) -32768 ~ 32767
int(32bit) 21억
long (64bit) 
float(32bit) 소수점 7자리
double(64bit) 소수점 14자리

```kotlin
fun main(args: Array<String>) {
    var number1 : Byte = 127
    var number2 : Short = 32767
    var number3 : Int = 21_0000_0000
    var number4 : Long = 22_0000_0000
    var number5 : Float = 3.1234567f
    var number6 : Double = 3.12345678901234
    
    println(number1)
    println(number2)
    println(number3)
    println(number4)
    println(number5)
    println(number6)
    
    var number7 = 127
    var number8 = 32767
    var number9 = 21_0000_0000
    var number10 = 22_0000_0000
    var number11 = 3.1234567f
    var number12 = 3.12345678901234
    
    println(number7.javaClass.name)
    println(number8.javaClass.name)
    println(number9.javaClass.name)
    println(number10.javaClass.name)
    println(number11.javaClass.name)
    println(number12.javaClass.name)
}
```

글자
-글자 한개만 담음
- Char 입력해서 선언
- ''작은 따옴표를 이용해서 입력

논리값
- true/false 값만 가질 수 있음
- Boolean 입력해서 선언

문자열
- 여러개의 문자를 담을 수 있음
- String 입력해서 선언
- "큰 따옴표를 이용해서 입력
- 
```kotlin
fun main(args: Array<String>) {
    var character : Char = 'A'
    var boolean : Boolean = true
    var string : String = "Hello World!"
    
    println(character)
    println(boolean)
    println(string)
    
    println(character.javaClass.name)
    println(boolean.javaClass.name)
    println(string.javaClass.name)
}
```

배열
- 2차원 데이터
- Array<데이터 형식> 입력해서 선언

```kotlin
fun main(args: Array<String>) {
    var intArray : Array<Int> = arrayOf(1,2,3)
    var charArray : Array<Char> = arrayOf('A', 'B')
    var stringArray : Array<String> = arrayOf("My", "Name")
    var boolArray : Array<Boolean> = arrayOf(false, true)
    
    println(intArray.toList())
    println(charArray.toList())
    println(stringArray.toList())
    println(boolArray.toList())
}
```


상수
- 값을 담을 수 있는 그릇
- 값을 바꿀 수 없음
- 초기값 필요
- val 선언

```kotlin
val test = 1
```

## 연산자
대입 연산자
> =
(데이터를 받을 변수) = (데이터를 입력한 값)

산술 연산자
+,-,*,/,%

```kotlin
fun main(args: Array<String>) {
    var x = 7
    var y = 3
    
    println(x + y)
    println(x - y)
    println(x * y)
    println(x / y)
    println(x % y)
}
```

비교 연산자
x > y
x < y
x >= y
x <= y
x == y
x != y

```kotlin
fun main(args: Array<String>) {
    var x = 7
    var y = 3
    var z = 7
    
    println(x > y)
    println(x < y)
    println(x >= z)
    println(x <= z)
    println(x == z)
    println(x != z)
}
```

범위 연산자
(자바에 없는 기능)

(비교 변수) in 시작값..마지막값
=> x in 1..10
1 <= x <= 10

```kotlin
fun main(args: Array<String>) {
    var x = 1
    var y = 11
    
    println(x in 1..10)
    println(y !in 1..10)
}
```

## 접근 권한
private
protected
internal
public

class human{
	접근자 var h1: String = ""
}

디폴트가 public
접근 권한
private
protected
internal
public

class human{
접근자 var h1: String = “”
}

디폴트가 public

## 제어문
if
when
while
for

## if
if, else if, else

```kotlin
fun main(args: Array<String>) {
    var x = 7
    var y = 3
    
    if (x > y)
    {
        println("x 값이 큽니다")
    }
    else if (x < y)
    {
        println("y 값이 큽니다")
    }
    else
    {
        println("x값과 y값이 서로 어느것도 크지 않습니다")
    }
}
```

## When문
다른 언어의 switch 문과 값음

```kotlin
fun main(args: Array<String>) {
    var x = 1
    
    when(x)
    {
        1 -> println("x 값은 1입니다")
        2 -> println("x 값은 2입니다")
        else -> {
            println("x값은 1또는 2가 아닙니다")
        }
    }
}
```

## For문
Range For문
for (변수 in 1..10 step 2)

Collection For문
for (item in collection)

```kotlin
fun main(args: Array<String>) {
    for (x in 1..10 step 2)
    {
        println(x)
    }
    
    var intArray : Array<Int> = arrayOf(1,10,100)
    for (item in intArray)
    {
        println(item)
	}
}
```

## While문
```kotlin
fun main(args: Array<String>) {
	var x = 0
    
    while (x < 5)
    {
        x++;
        println("while 반복")
	}
    println("끝")
}
```

## Function
함수, 메서드라고 부름

```kotlin
fun 이름 (입력값) : 리턴값 {
	return 리턴
}
```

```kotlin
fun main(args: Array<String>) {
	
	var x = 36
    println(addFour(x))
}

fun addFour(input : Int) : Int
{
    var total = input + 4
    return total
}
```

## Class
class (클래스명) {
	var name : String  // (Property)
	fun test{ // (Function)
	}
}

```kotlin
class Human
{
    val country : String = "한국"
    val gender : String = "남"
    val name : String = "민준"
    
    fun printHumanInfo() {
        println("나라는 $country 성별은 $gender 이름은 $name 입니다.")
    }
}

fun main(args: Array<String>) {
	var h1 = Human()
    h1.printHumanInfo()   
}
```

## Inheritance
open class (클래스명) {
	open var name : String
	open fun test{
	}
}

open 을 적은 함수 변수 클래스는 상속 전용 (virtual 같은 거 )

Override란
상속받은 변수, 기능 재구축

open class Person: Human(){
	override val name = "민준"
}

```kotlin
open class Human
{
    open val country : String = "한국"
    open val gender : String = "남"
    open val name : String = "민준"
    
    fun printHumanInfo() {
        println("나라는 $country 성별은 $gender 이름은 $name 입니다.")
    }
}
class American :Human()
{
    override val country : String = "미국"
    override val name : String = "minjun"
}
```


## Interface
정보 상호 작용의 매개체.

interface CarInterface{
	fun test1()
	fun test2()
}

```kotlin
interface CarInterface{
    fun vibraction(wave : String)
}

class Car{
    var touch : CarInterface? = null
    fun runStart(){
        touch?.vibraction("덜덜덜")
    }
}

open class Human : CarInterface
{
    override fun vibraction(wave: String){
        if (wave == "덜덜덜")
        {
            println("사람 : 자동차 진동이 너무 심하군");
		}
    }
    
    open val country : String = "한국"
    open val gender : String = "남"
    open val name : String = "민준"
    
    fun printHumanInfo() {
        println("나라는 $country 성별은 $gender 이름은 $name 입니다.")
    }
}
```

## Nested Class
중첩 클래스, 클래스 내부 클래스

## Data Class
data class Student(
	var grade: Int,
	var gender: String
)

데이터 전용 클래스 구현체들이 정의되어 있음 tostring 같은
	
```kotlin
data class Student(
	var grade: Int,
    var name : String,
    var gender : String,
    var birthday : String
)

fun main(args: Array<String>) {
	var howl = Student(1, "하울", "man", "199999")
    var howl2 = Student(1, "하울", "man", "199999")
    var howl3 = howl.copy()
    
    println(howl3.toString())
    
    howl3.grade = 3 // Setter
    println(howl3.grade) // Getter
    println(howl3.hashCode())
    println(howl.equals(howl2))
}
```

## NullSafety
null point exception

선언
변수에 nullsafety 선언,
직접 접근 차단

var name : String? = "테스트"

Null Safety 강제 해제 ( !! 로 해제 할 수 있음)
(변수!!)
널을 풀어버리는 오류 발생

안전 해제 그냥 (자동 해제 권장)
println(name)

? 안전 해제 (하위 맴버 접근을 위해 사용)
println(name?.length)

대입
var howl : String = ""
var name : String? = "하울"
howl = name X
howl = name!! 

```kotlin
fun main(args: Array<String>) {
	var howl : String? = null
    var name : String? = "하울"
    
    //println(howl!!)
    println(name!!)
    
    println(howl)
    println(name)
    
    println(howl?.length)
    println(name?.length)
    
    var test1 : String
    var test2 : String? = "TEST"
    
    test1 = test2!!
    println(test1)
}
```
