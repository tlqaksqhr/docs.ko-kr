---
title: "Partial 클래스 및 메서드(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, partial 클래스 및 메서드"
  - "partial 클래스[C#]"
  - "partial 메서드[C#]"
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 35
---
# Partial 클래스 및 메서드(C# 프로그래밍 가이드)
[클래스](../../../csharp/language-reference/keywords/class.md)나 [구조체](../../../csharp/language-reference/keywords/struct.md), [인터페이스](../../../csharp/language-reference/keywords/interface.md) 또는 메서드의 정의를 둘 이상의 소스 파일로 분할할 수 있습니다.  각 소스 파일에는 형식이나 메서드 정의 섹션이 들어 있고 이 모든 부분은 응용 프로그램을 컴파일할 때 결합됩니다.  
  
## Partial 클래스  
 클래스 정의는 다음과 같은 여러 가지 상황에서 분할할 수 있습니다.  
  
-   대규모 프로젝트를 진행하는 경우 클래스를 개별 파일로 분할하면 여러 프로그래머가 동시에 작업을 수행할 수 있습니다.  
  
-   자동으로 생성된 소스를 사용하여 작업하는 경우 소스 파일을 다시 만들지 않고도 클래스에 코드를 추가할 수 있습니다.  Visual Studio에서는 Windows Forms, 웹 서비스 래퍼 코드 등을 만들 때 이러한 방식을 사용합니다.  따라서 Visual Studio에서 자동으로 만든 파일을 수정할 필요 없이 이러한 클래스를 사용하는 코드를 만들 수 있습니다.  
  
-   클래스 정의를 분할하려면 다음과 같이 [partial](../../../csharp/language-reference/keywords/partial-type.md) 키워드 한정자를 사용합니다.  
  
 [!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_1.cs)]  
  
 `partial` 키워드는 클래스, 구조체 또는 인터페이스의 다른 부분을 네임스페이스 안에서 정의할 수 있음을 나타냅니다.  모든 부분에 `partial` 키워드를 사용해야 합니다.  최종 형식을 생성하려면 컴파일할 때 모든 부분을 사용할 수 있어야 합니다.  모든 부분은 `public`, `private` 등과 같이 액세스 가능성이 동일해야 합니다.  
  
 부분이 추상으로 선언되면 전체 형식이 추상으로 간주됩니다.  부분이 봉인으로 선언되면 전체 형식이 봉인으로 간주됩니다.  부분이 기본 형식으로 선언되면 전체 형식이 해당 클래스를 상속합니다.  
  
 기본 클래스를 지정하는 모든 부분이 일치해야 하지만 기본 클래스를 생략하는 부분에서도 기본 형식을 상속합니다.  부분은 서로 다른 기본 인터페이스를 지정할 수 있으며 이 경우 최종 형식에는 모든 partial 선언에 나열된 모든 인터페이스가 구현됩니다.  partial 정의에 선언된 모든 클래스, 구조체 또는 인터페이스 멤버를 다른 모든 부분에 사용할 수 있습니다.  최종 형식은 컴파일 타임에 모든 부분의 조합이 됩니다.  
  
> [!NOTE]
>  대리자나 열거형 선언에는 `partial` 한정자를 사용할 수 없습니다.  
  
 다음 예제에서는 중첩 형식을 포함하는 형식 자체가 partial이 아니어도 중첩 형식이 partial이 될 수 있음을 보여 줍니다.  
  
 [!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_2.cs)]  
  
 컴파일 타임에 부분 형식\(Partial Type\) 정의의 특성이 병합됩니다.  예를 들어, 다음 선언을 참조하십시오.  
  
 [!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_3.cs)]  
  
 이러한 선언은 다음 선언과 같습니다.  
  
 [!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_4.cs)]  
  
 다음은 모든 부분 형식\(Partial Type\) 정의에서 병합됩니다.  
  
-   XML 주석  
  
-   인터페이스  
  
-   제네릭 형식 매개 변수 특성  
  
-   클래스 특성  
  
-   members  
  
 예를 들어, 다음 선언을 참조하십시오.  
  
 [!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_5.cs)]  
  
 이러한 선언은 다음 선언과 같습니다.  
  
 [!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_6.cs)]  
  
### 제한  
 partial 클래스 정의를 사용하여 작업할 때는 다음과 같은 몇 가지 규칙을 따라야 합니다.  
  
-   동일한 형식의 일부를 의미하는 모든 부분 형식\(Partial Type\) 정의는 `partial`을 사용하여 한정해야 합니다.  예를 들어, 다음 클래스 선언에서는 오류가 발생합니다.  
  
     [!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_7.cs)]  
  
-   `partial` 한정자는 `class`, `struct` 또는 `interface` 키워드 바로 앞에만 사용할 수 있습니다.  
  
-   다음 예제와 같이 중첩된 부분 형식\(Partial Type\)은 부분 형식\(Partial Type\) 정의에 사용할 수 있습니다.  
  
     [!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_8.cs)]  
  
-   동일한 형식의 일부를 의미하는 모든 부분 형식\(Partial Type\) 정의는 동일한 어셈블리와 동일한 모듈\(.exe 또는 .dll 파일\)에서 정의해야 합니다.  partial 정의는 여러 모듈에 분산될 수 없습니다.  
  
-   클래스 이름과 제네릭 형식 매개 변수는 모든 부분 형식\(Partial Type\) 정의에서 일치해야 합니다.  제네릭 형식은 부분 형식\(Partial Type\)이 될 수 있습니다.  각 partial 선언에서는 동일한 매개 변수 이름을 동일한 순서대로 사용해야 합니다.  
  
-   부분 형식\(Partial Type\) 정의에 대한 다음 키워드는 선택적이지만 부분 형식\(Partial Type\) 정의 하나에 이러한 키워드가 있으면 동일한 형식의 다른 partial 정의에 지정된 키워드와 충돌하지 말아야 합니다.  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   기본 클래스  
  
    -   [new](../../../csharp/language-reference/keywords/new.md) 한정자\(중첩된 부분\)  
  
    -   제네릭 제약 조건  
  
         자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)를 참조하십시오.  
  
## 예제 1  
  
### 설명  
 다음 예제에서는 `CoOrds` 클래스의 필드와 생성자를 partial 클래스 정의 하나에서 선언하고 `PrintCoOrds` 멤버를 다른 partial 클래스 정의에서 선언합니다.  
  
### 코드  
 [!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_9.cs)]  
  
## 예제 2  
  
### 설명  
 다음 예제에서는 partial 구조체와 인터페이스를 개발하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_10.cs)]  
  
## 부분 메서드\(Partial Method\)  
 partial 클래스 또는 구조체는 부분 메서드\(Partial Method\)를 포함할 수 있습니다.  클래스의 한 부분에는 메서드 시그니처가 포함됩니다.  같은 부분이나 다른 부분에 선택적 구현을 정의할 수 있습니다.  구현을 정의하지 않으면 컴파일할 때 메서드 및 메서드에 대한 모든 호출이 제거됩니다.  
  
 클래스의 한 부분을 구현하는 사용자는 부분 메서드를 사용하여 이벤트와 비슷한 메서드를 정의할 수 있습니다.  이 경우 클래스의 다른 부분을 구현하는 사용자는 해당 메서드를 구현할지 여부를 결정할 수 있습니다.  메서드를 구현하지 않을 경우, 컴파일러에서 메서드 시그니처와 메서드에 대한 모든 호출을 제거합니다.  호출의 인수 평가 시  발생할 수 있는 결과를 포함하여 메서드에 대한 호출은 런타임 시 영향이 없습니다.  따라서 partial 클래스의 코드에는 구현을 정의하지 않고도 부분 메서드를 마음대로 사용할 수 있습니다.  메서드를 호출만 하고 구현하지 않더라도 컴파일 타임 오류나 런타임 오류가 발생하지 않습니다.  
  
 부분 메서드는 생성된 코드를 사용자 지정할 때 특히 유용합니다.  부분 메서드를 사용하면 메서드 이름과 시그니처를 예약할 수 있습니다. 이렇게 하면 생성된 코드에서 메서드를 호출해도 메서드를 구현할지 여부를 개발자가 결정할 수 있습니다.  partial 클래스와 마찬가지로 부분 메서드를 사용해도 별도의 런타임 비용 없이 코드 생성기에서 만든 코드와 개발자가 직접 만든 코드를 함께 사용할 수 있습니다.  
  
 부분 메서드 선언은 메서드 정의와 메서드 구현이라는 두 부분으로 구성됩니다.  이 두 부분은 partial 클래스에서 각각 별도의 부분에 포함되거나 동일한 부분에 포함될 수 있습니다.  구현을 선언하지 않으면 컴파일러에서 정의하는 선언 및 메서드에 대한 모든 호출을 최적화합니다.  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   부분 메서드 선언은 [partial](../../../csharp/language-reference/keywords/partial-type.md) 키워드로 시작해야 하고 메서드는 [void](../../../csharp/language-reference/keywords/void.md)를 반환해야 합니다.  
  
-   부분 메서드에는 [ref](../../../csharp/language-reference/keywords/ref.md) 매개 변수만 사용할 수 있고 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수는 사용할 수 없습니다.  
  
-   부분 메서드는 암시적으로 [private](../../../csharp/language-reference/keywords/private.md)이므로 [virtual](../../../csharp/language-reference/keywords/virtual.md)이 될 수 없습니다.  
  
-   부분 메서드는 본문이 있는지 여부에 따라 정의 부분인지 구현 부분인지가 결정되기 때문에 [extern](../../../csharp/language-reference/keywords/extern.md)이 될 수 없습니다.  
  
-   부분 메서드에는 [static](../../../csharp/language-reference/keywords/static.md) 및 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 한정자를 사용할 수 있습니다.  
  
-   부분 메서드는 제네릭 메서드일 수 있습니다.  제약 조건은 정의하는 부분 메서드 선언에 포함되며, 필요한 경우 구현하는 부분 메서드 선언에 반복될 수 있습니다.  매개 변수 및 형식 매개 변수 이름은 구현하는 선언과 정의하는 선언에서 동일하지 않아도 됩니다.  
  
-   [대리자](../../../csharp/language-reference/keywords/delegate.md)를 정의 및 구현된 부분 메서드에 대해 만들 수 있지만 단지 정의된 부분 메서드에 대해서는 만들 수 없습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)   
 [부분\(형식\)](../../../csharp/language-reference/keywords/partial-type.md)