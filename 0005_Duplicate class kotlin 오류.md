```
Duplicate class kotlin.collections.jdk8.CollectionsJDK8Kt found in modules kotlin-stdlib-1.8.0 (org.jetbrains.kotlin:kotlin-stdlib:1.8.0) and kotlin-stdlib-jdk8-1.7.20 (org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.7.20)
```
```
Execution failed for task ':app:checkDebugDuplicateClasses'.
A failure occurred while executing com.android.build.gradle.internal.tasks.CheckDuplicatesRunnable ~
```

으아... 분명 2023년 2월까지는 앱 apk 생성이 잘 되었는데,
자바로 작성하였는데도 불구하고 위의 오류가 자꾸 뜨면서 빌드오류가 생겼다.

날 살린 건,,, 바로 이 링크이다.

[Velog](https://velog.io/@mraz3068/Duplicate-class-kotlin.collections.jdk8.CollectionsJDK8Kt-found-in-modules-kotlin-stdlib-1.8.0-org.jetbrains.kotlinkotlin-stdlib1.8.0-and-kotlin-stdlib-jdk8-1.7.20-org.jetbrains.kotlinkotlin-stdlib-jdk81.7.20)

Kotlin 버전 두 개가 같은 프로젝트 내에 있어서 중복되어 있는 에러라고 한다.

아래 코드를 build.gradle 추가하면 된다.

```
dependencies {
    modules {
        module("org.jetbrains.kotlin:kotlin-stdlib-jdk7") {
            replacedBy("org.jetbrains.kotlin:kotlin-stdlib", "kotlin-stdlib-jdk7 is now part of kotlin-stdlib")
        }
        module("org.jetbrains.kotlin:kotlin-stdlib-jdk8") {
            replacedBy("org.jetbrains.kotlin:kotlin-stdlib", "kotlin-stdlib-jdk8 is now part of kotlin-stdlib")
        }
    }
}
```
