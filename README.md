[![official JetBrains project](https://jb.gg/badges/official-plastic.svg)](https://confluence.jetbrains.com/display/ALL/JetBrains+on+GitHub)

# kotlin-koans-edu

Kotlin Koans are a series of exercises to get you familiar with the Kotlin Syntax.
Each exercise is created as a failing unit test, and your job is to make it pass.
You can work with Kotlin Koans in one of the following ways:

- You can play with Koans online: https://play.kotlinlang.org/koans/overview.
- You can solve the tasks right inside IntelliJ IDEA or Android Studio by
  [installing the EduTools plugin](https://www.jetbrains.com/help/education/install-edutools-plugin.html?section=IntelliJ%20IDEA)
  and [choosing Kotlin Koans course](https://www.jetbrains.com/help/education/learner-start-guide.html?section=Kotlin%20Koans).

You don't need this project if you want to solve the tasks. Install the educational plugin or do it online.
This project contains the task content, so please submit a new pull request if you want to contribute any changes
to the existing or new tasks.

## Introduction

- Named arguments, Default arguments
- Triple-quoted strings
- Nullable types
  - [Null safety | Kotlin](https://kotlinlang.org/docs/null-safety.html)
- Nothing type
  - [The Nothing type](https://kotlinlang.org/docs/exceptions.html#the-nothing-type)
  - 例外を投げる（値を返さない）関数の戻り値として使える `Nothing` 型
- Lambdas
  - [Lambda expressions and anonymous functions](https://kotlinlang.org/docs/lambdas.html#lambda-expressions-and-anonymous-functions)
    - function literal と呼ぶらしい。JS の無名関数
    - `{ 引数1: 型1, 引数2: 型2, ... -> <expression> }`
  - [`any`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/any.html)

## Classes

- Data classes
  - [Classes | Kotlin](https://kotlinlang.org/docs/classes.html) 
  - [Properties | Kotlin](https://kotlinlang.org/docs/properties.html)
  - [Data classes | Kotlin](https://kotlinlang.org/docs/data-classes.html)

- class のコンストラクタには処理を書けない。かわりに `init` を使用する
- `init` は複数定義できる。プロパティの初期化も含め上から順に実行される

```kotlin
class InitOrderDemo(name: String) {
    val firstProperty = "First property: $name".also(::println)
    
    init {
        println("First initializer block that prints $name")
    }
    
    val secondProperty = "Second property: ${name.length}".also(::println)
    
    init {
        println("Second initializer block that prints ${name.length}")
    }
}
```

- Smart casts
  - [Smart casts](https://kotlinlang.org/docs/typecasts.html#smart-casts)
  - [When expression](https://kotlinlang.org/docs/control-flow.html#when-expression)
- smart casts
  - `x is String` とかでコンパイラが勝手に型をキャストしてくれる
- when expression
  - [Rust の match](https://doc.rust-jp.rs/book-ja/ch06-02-match.html) みたい

```kotlin
when (x) {
  1 -> print("x == 1")
  2 -> print("x == 2")
  else -> {
    print("x is neither 1 nor 2")
  }
}
```