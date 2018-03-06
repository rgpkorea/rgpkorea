---
title: 요기요는 Kotlin을 어떻게 적용했나?
description: 요기요의 Kotlin 적용 과정과 Learning Curve
author: 권태환
image: post-bg.jpg
date: 2018-03-02T10:00:00+00:00
type: post
draft: false
---

RGP Korea는 '요기요'와 '배달통'을 함께 운영중이다. 이 중 필자가 담당하고 있는 요기요 서비스에 최근 Java와 Kotlin을 함께 사용하고 있다. 요기요 앱에 현재까지 약 14%의 Kotlin을 적용한 상태인데, 왜 도입하게 되었으며, 러닝 커브의 해결은 어떻게 했는지 정리하려 한다.


<br />

## Kotlin

[Kotlin](https://kotlinlang.org/)은 JetBrain 사에서 2011년 첫 발표된 후 2016년 1.0 정식 버전이 배포되었고, 현재 1.1.60 버전이 배포 중이다. 2011년 이후 5년이라는 시간을 통해 안정화가 진행되어, 현재 Kotlin은 Java 대신 실 개발에 사용하기 딱 좋은 상태로 안정화되어 있다. 2017년 Google I/O에서 Android 메인 언어인 Java와 함께 Kotlin을 병행으로 사용할 수 있도록 채택해주었다.

이미 Google I/O 신청 페이지에서 종전에 없던 Kotlin 사용률을 조사한 것만 하더라도 필자는 기대하긴 했으며, 듣기론 구글 내부에서도 일부 사람만이 이를 알고 있었다고 한다. [구글 블로그](https://developers-kr.googleblog.com/2017/06/android-announces-support-for-kotlin.html)를 통해 Kotlin을 채택한 이유를 설명하고 있는데, 이미 유명한 회사들(Expedia, Flipboard, Pinterest, Square 등)이 Kotlin을 실 프로덕트에 적용한 사례가 있으며, 안정적으로 사용하고 있다는 이유를 들어 채택 사유에 대해서 설명하고 있다.

특히 필자는 Kotlin을 약 1년간 학습하면서 느꼈던 장점인 Safety Nullable에 대한 만족도가 높았으며, Java에서는 람다식과 스트림 등 최신 기능을 사용하기 위한 제약이 따른다는 점 등이 Kotlin을 학습하면서 굉장히 만족스럽게 생각하고 있었다. 행사 당일에 직접 촬영한 사진을 아래와 같이 추가해보았다.

![kotlin-01]

> Google I/O 2017 Developer Keynote ⓒ 권태환
> 필자는 2017년 Google I/O 행사에 직접 참여하여 Kotlin이 정식 채택되었다는 소식을 들었다.


<br />

## 요기요에 Kotlin 적용하기

다음의 과정이 필요하였다.

- 설득
- 적용
- 러닝 커브는 어떻게 할 것인가?

1. 설득

설득은 생각보다 쉬웠다. Google I/O 이후에 적용을 하였기에 아주 쉽게 설득할 수 있었다. 그전에는 요기요 사장님 앱 (요기요 사장님들을 위한 주문 접수 앱)에서만 하기로 하였으나, Google I/O로 인해 일반 사용자 대상의 요기요 앱에서도 적용할 수 있게 되었다.
그리고 필자가 이미 Kotlin을 학습한 상태였기에 안정성 검증에 대한 부담감을 가지고 생산성을 선택했다. Kotlin을 6개월 정도 실 프로젝트에 적용하고 있는데, Java보다는 높은 생산성을 유지하고 있다.
다만 NullPointerException을 피하는 기법을 제공하고 있는데, 일부 실수로 인해 초반에 NullPointerException이 많았었다.

2. 적용

처음 시작한 부분은 Google I/O 이전에 작업했던 클래스 하나를 Java to Kotlin으로 Convert 하는 과정을 거쳤다. 길지 않은 ViewModel로써 딱 하나만 처리하도록 역할을 구분해둔 상태였다. 그래서 어렵지 않게 작업하였다. 일단 필자가 먼저 프로젝트에 Kotlin을 적용하였다.

3. 러닝 커브는 어떻게 할 것인가?

필자가 혼자서 적용할 수 있긴 하다. 하지만 함께하는 팀원과 팀장님도 이를 적용해야 한다. 다행히도 팀 내에서는 Kotlin에 대한 관심을 가지고 있어 조금이라도 학습한 상태였다. 그리고 웹을 하신 팀장님은 어렵지 않게 Kotlin을 적용하셨고, 오히려 필자보다 큰 문제없이 사용하였다. 오히려 필자는 1년이라는 시간 동안 겪어보지 못한 오류들을 경험하였고, 더 좋은 문법들로 나가는 방법도 터득하였다.

생각보다 간단하게 설득하였고, 적용할 수 있었다. 어떤 것이든 새로운 부분을 적용하는데 있어서 학습 비용은 발생한다. 그 학습 비용은 얼마나 관심을 가지고 하느냐인데 필자가 생각하기엔 회사에서 적용하는 것만큼 좋은 것은 없는 것 같다는 생각이다. 집에 가면 공부를 하지않으니 있는 시간에라도 최대로 학습하는 게 필요한 것이다.


<br />

## 나부터 시작하자

Google I/O 세션 중 [Pinterest - Christina Lee](https://events.google.com/io/schedule/?section=may-19&sid=bad5074c-ffed-4038-abea-8c787370c65f&speaker=5b7d8f98-48f9-4de3-a02a-2a6d52d1a8c3)와 [Jake Wharton](https://events.google.com/io/schedule/?section=may-19&sid=bad5074c-ffed-4038-abea-8c787370c65f&speaker=3d352052-ece4-4f78-9193-3b5b7388809e)이 함께 한 세션은 꼭 시청하기 바란다.

![maxresdefault]

이 세션에서는 핀터레스트에서 새로운 걸 도입하기 위해서 어떻게 접근했을 때 가장 좋았는 지 소개하고 있다. 생산성이 높아지고, 좋은 언어라고 하더라도 결국 나와 함께 할 사람을 설득해야 한다. 그렇게 하기 위해서는 나부터 시작하고, 이들을 한 명씩 설득하는 방법이 가장 좋다. 말로만 떠들기 보다 왜 좋은지를 구체화하고, 함께 할 수 있는 팀원들을 잘 설득해서 모두가 윈윈하는 방법으로 접근해야 한다. 상위자를 설득해서 결국 적용할 수 있는 게 가장 좋겠지만. 이러한 방법을 이 영상을 통해 짧게나마 소개받을 수 있다.

결국 나 잘났으니 써보자가 아닌 왜 효율적이고, 좋은지를 설명할 수 있어야 한다. 혼자라면 이런 게 다 소용없겠지만(내가 선택한 것이 답이다.) 함께할 사람이 있을 때는 설득이라는 게 필요하니 이 영상을 추천한다.

결론은 `정말 꼭 새로운 걸 해보고 싶다면 그냥 하자가 아닌 나부터 학습해서 설득하는 방법을 택해보자.`


<br />

## NullPointerException 발생

아무리 1년 동안 공부를 했다고 하더라도, NullPointerException가 발생해버렸다. NPE을 줄이려고 Kotlin의 장점을 활용해야 하는데 다음을 간과해버렸다.

- Java : 언제나 null을 가질 수 있는 변수를 만들 수 있다
- Kotlin : 기본은 Nullable을 허용하지 않는다. ?을 추가하여 null을 허용해야 한다.

Kotlin의 장점 중 하나인 Safety Nullable을 하지 않았다가 생긴 문제이다. ?표 하나만 추가하면 `Nullable`이지만 `NotNull`을 해버린 부분이다.

> 다행히 Android Support Library 26 이상에서는 Nullable이 필요한 부분을 좀 더 강화했다.

Nullable을 정의하지 않으면 생기는 부분은 바로 Java에서 Kotlin으로 만든 method을 호출할 때 발생한다. Nullable이 가능한 변수를 Kotlin method로 넘길 때 값이 있으면 문제가 없지만, null로 가버리면 Runtime에 NullPointerException이 발생해버린다.

바로 아래와 같은 코드가 이에 해당할 수 있는데 간단한 샘플을 추가해보면. NotNull 변수 String 2개를 받아오고, 이를 문자 2개로 합치는 merge method이다.

```kotlin
// class name String.kt
fun merge(a: String, b: String) = "$a $b"
```

위의 merge method을 kotlin 파일에서 호출하면 a가 Nullable이라서 즉시 오류를 발생시켜준다. (실제 디컴파일하면 Java 코드라서 오류가 안나오는 게 정상이긴 하지만)

```kotlin
class SampleTest {
  val a: String? = null

  @Test
  fun test() {
    StringKt.merge(a, "BC")
  }
}
```

하지만 필자가 실수한 코드는 java에서 Kotlin을 부르는 부분이다.

```java
public class SampleTest {

  private String a = "A";
  private String b = "B";

  @Before
  public void setUp() { a = null; }

  @Test
  public void sample() {
      System.out.println("merge " + StringKt.merge(a, b));
    }
}
```

자바에서는 변수에 언제든 값을 변경하는 게 가능하며, null을 적용하는 게 가능하다. 이 부분이 API을 통해서 내려온 값이고, 그 값이 null이라면 Runtime 오류는 피할 수 없어 아래와 같은 오류가 발생해버린다.

```
java.lang.IllegalArgumentException:
 Parameter specified as non-null is null:
 method kr.co.yogiyo.myapplication.StringKt.merge
```


<br />

## NullPointerException을 피하려면

결국 NullPointerException을 피하려면 다음과 같은 행동을 해야 한다. StringKt.merge(a, b)을 부르는 시점에 if 문으로 NotNull 임을 체크하고, 값을 넘겨주거나, try/catch을 이용하여 예외 처리를 하는 등으로 조치를 취해야 한다.

```java
public class SampleTest {

  // 생략 ...

  @Test
  public void sample() {
    try {
      System.out.println("merge " + StringKt.merge(a, b));
    } catch (NullPointerException e) {}

    // or
    if (a != null && b != null) {
      System.out.println("merge " + StringKt.merge(a, b));
    }
  }
}
```

하지만 `StringKt.merge`을 10곳에서 호출하면 10곳에서 모두 이를 처리해야 하는데 너무 귀찮은 일이다.

그래서 아래와 같이 불리게 될 Method을 예외 처리하는 편이 편하다. 받는 쪽에서 `@Nullable`을 허용하고, 이를 사용하는 것이다. 그럼 보내는 쪽에서는 별도로 신경 써야 할 부분도 없어지고, 받는 곳에서 알아서 return 해주도록 처리한다.

```kotlin
// class name String.kt
fun merge(a: String?, b: String?) = "${a ?: ""} ${b ?: ""}"
```


<br />

## 요기요에서 학습 했던 방법은?

필자는 1년 가까이 Kotlin을 학습한 상태이다. 하지만 혼자서 Kotlin을 적용할 순 없고, 내가 없더라도 다른 팀원이 수정해야 한다. 그렇기에 팀원 간 러닝 커브를 줄이는 방법이 필요하다. 팀장님은 혼자서도 어느 정도 사용하는 게 가능하였고, 잘 모르는 부분만 필자에게 물어보는 정도로 잘 다루고 있으셨고, 팀원과 약 1개월간 페어 프로그래밍을 진행하면서 Kotlin을 학습할 수 있었다.

1. 페어 프로그래밍을 진행
2. 먼저 Java로 클래스 생성
3. Java to Kotlin Convert을 이용하여 코드 컨버팅
4. 이미 Kotlin 파일이 있다면 별도의 temp.java 파일을 만들어 거기서 복사 붙여넣기 한다
   - 옆에서 부족한 부분을 조금씩 서포트
5. 어느 정도 숙련되었을 때 Kotlin으로 직접 작성하는 게 가능

페어 프로그래밍을 약 1개월간 진행했는데 처음같이 진행하였고, Kotlin도 처음 적용하였다. 다행히 이렇게 진행함으로써 팀원도 Kotlin을 잘 활용할 수 있을 정도로 학습이 되었다는 점이다. 그리고 필자도 잘 몰랐던 부분을 기존 보다 코드 축약이 가능해졌다는 점이다.

페어 프로그래밍을 적절히 활용하려면 함께 할 시간을 좀 더 줄이면서 진행해야 하겠지만, 서로 잘 모르는 부분을 봐줄 수 있다면 충분히 성장하기 좋은 방식이었다.

다행히 함께 한 팀원은 나보다 더 오랜 기간 회사를 다녔으며, 누락할 수 있는 부분을 더 꼼꼼히 살펴보면서 페어 프로그래밍을 할 수 있었다.


<br />

## 변환의 조건은?

Java에서 Kotlin으로 전환이 필요하다. 일정 시간을 잡고 전부다 Kotlin으로 작업하면 좋겠지만, 그렇게 하려면 시간이 많이 들어가니 그냥 새로 만드는 편이 빠르다.

하지만 회사에서는 그러지 못하니 다음과 같은 방법으로 Convert 진행하고 있다.

- 새로운 프로젝트 단위로 진행한다
- 기존 코드를 리팩토링 해야 한다

위와 같이 2가지 조건 중 1개라도 적용되면 새로운 패키지와 프로젝트를 따고, 이를 정리한다.

새로운 패키지의 조건은 필자가 운영하는 개인 블로그에 올렸던 [패키지 구조화 방법](http://thdev.tech/androiddev/2017/02/20/Android-MVP-Package-Structure.html)을 회사에서도 사용하고 있다. 코드 수정시에 뷰 단위로 클래스가 모여있기 때문에 하나의 패키지만 확인하면 많은 이동 없이도 빠르게 수정이 가능하다. N Activity의 N Fragment에 속해있는 ViewHolder을 수정해야 한다고 하더라도, 패키지 이름만 잘 만들어두면 빠르게 파악하고, 수정이 가능하다는 장점을 가진다.


<br />

## 현재 '요기요'와 '요기요 사장님' 앱에서는

요기요 앱과 요기요 사장님 앱에서는 Kotlin을 한창 적용 중에 있다.

이 글을 작성하는 현시점에서 요기요 안드로이드앱에서는 약 14% 정도 Kotlin을 적용한 상태이며, 새롭게 추가하는 부분을 대부분 Kotlin으로 작업 중에 있다.

![ygy-android]

요기요 사장님 앱은 거의 대부분을 팀원 혼자서 관리하고 있다. 페어 프로그래밍을 통해 학습한 Kotlin을 한참 적용 중이다.

![ygy-android-owner]

GitHub에서는 marster 기준으로 언어별 %을 알려준다. 그러다 보니 위와 같은 결과를 확인할 수 있다. 추가 작업을 진행 중이더라도, marster에 merge 하지 않으면 올라가지 않는 부분이 있지만, 현재까지는 위와 같이 적용하였다.


<br />

## 후기

최근에 작업한 음식점 리스트이다. 기존 레거시 코드를 제거하기 위해서 전부 새로 작성했는데 Kotlin으로 작업하였다. Activity/ViewPager/Fragment까지 모두 Kotlin으로 새로 작성하였다.

기존 레이아웃이 많이 무겁기도 하였고, 이동 간 처리하는 부분도 상당히 많았다. 현재는 A/B 테스트 중이라서 일부 사용자에게 아래의 화면이 노출되고 있다.

![list]

Kotlin이라는 언어 자체가 주는 생산성은 높다고 생각한다. 처음 공부하는 사람에게는 러닝 커브는 당연한 결과이다. 하지만 Java을 어느 정도 알고 있는 상태라면 Kotlin을 학습하는데 전혀 문제가 없다. 특히나 스크립트 또는 함수형 언어를 사용하던 개발자라면 더 쉽게 Kotlin을 적용하는 게 가능하다. 구글이 정식 언어 채택 이후 생각보다 많은 사람들이 Kotlin을 학습하고 있으며, 실제 프로젝트에 조금이나마 적용하고 있는 게 눈에 띄고 있다.

결국 함께 할 사람을 잘 설득해서 더 좋은 방향으로 이끌 수 있어야 하겠지만...


권태환, 요기요 클라이언트개발 엔지니어 @RGP Korea

[kotlin-01]: ../images/how-did-yogiyo-apply-kotlin/kotlin-01.jpg
[maxresdefault]: ../images/how-did-yogiyo-apply-kotlin/maxresdefault.jpg

[ygy-android]: ../images/how-did-yogiyo-apply-kotlin/ygy-android.png
[ygy-android-owner]: ../images/how-did-yogiyo-apply-kotlin/ygy-android-owner.png

[list]: ../images/how-did-yogiyo-apply-kotlin/list.jpg
