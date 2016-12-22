---
title: "Override 및 New 키워드를 사용하여 버전 관리(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, override 및 new"
  - "C# 언어, 버전 관리"
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Override 및 New 키워드를 사용하여 버전 관리(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

서로 다른 라이브러리 내의 [기본](../../../csharp/language-reference/keywords/base.md) 클래스와 파생 클래스 간에 버전 관리 기능을 향상시키며 이전 버전과 호환될 수 있도록 C\# 언어가 설계되었습니다.  예를 들어, C\#에서는 기본 [클래스](../../../csharp/language-reference/keywords/class.md)에 새 멤버를 추가하고 파생 클래스의 멤버와 동일한 이름을 부여해도 오류나 예기치 않은 동작이 발생하지 않습니다.  또한 클래스에서 메서드가 상속된 메서드를 무시하도록 의도되었는지 또는 메서드가 유사하게 명명된 상속된 메서드를 숨기는 새 메서드인지를 명시적으로 표시해야 합니다.  
  
 C\#에서는 파생 클래스에 기본 클래스 메서드와 이름이 동일한 메서드를 포함할 수 있습니다.  
  
-   기본 클래스 메서드는 [virtual](../../../csharp/language-reference/keywords/virtual.md)로 정의해야 합니다.  
  
-   파생 클래스의 메서드 앞에 [new](../../../csharp/language-reference/keywords/new.md) 또는 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하지 않으면 컴파일러에서 경고가 발생하고 메서드에 `new` 키워드가 있는 것처럼 작동합니다.  
  
-   파생 클래스의 메서드 앞에 `new` 키워드를 사용하면 메서드가 기본 클래스의 메서드에 종속되지 않은 것으로 정의됩니다.  
  
-   파생 클래스의 메서드 앞에 `override` 키워드를 사용하면 파생 클래스의 개체에서 기본 클래스 메서드 대신 이 메서드를 호출합니다.  
  
-   기본 클래스 메서드는 `base` 키워드를 사용하여 파생 클래스 내에서 호출할 수 있습니다.  
  
-   `override`, `virtual` 및 `new` 키워드는 속성, 인덱서 및 이벤트에도 적용할 수 있습니다.  
  
 C\# 메서드는 기본적으로 비가상 메서드입니다.  메서드를 가상 메서드로 선언하면 이 메서드를 상속하는 클래스에서 자체 버전을 구현할 수 있습니다.  메서드를 가상 메서드로 만들려면 기본 클래스의 메서드 선언에 `virtual` 한정자를 사용해야 합니다.  그러면 파생 클래스가 `override` 키워드를 사용하여 기본 가상 메서드를 재정의하거나 `new` 키워드를 사용하여 기본 클래스의 가상 메서드를 숨길 수 있습니다.  `override` 키워드나 `new` 키워드를 모두 지정하지 않으면 컴파일러에서 경고가 발생하고 파생 클래스의 메서드가 기본 클래스의 메서드를 숨기게 됩니다.  
  
 이러한 경우를 구체적으로 살펴보기 위하여 A라는 회사에서 프로그램에 사용되는 `GraphicsClass`라는 클래스를 만든 경우를 가정해 보겠습니다.  `GraphicsClass`는 다음과 같습니다.  
  
 [!code-cs[csProgGuideInheritance#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_1.cs)]  
  
 회사에서는 이 클래스를 사용하며, 개발자는 이 클래스로 고유한 클래스를 파생시켜 새 메서드를 추가합니다.  
  
 [!code-cs[csProgGuideInheritance#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_2.cs)]  
  
 회사 A에서 다음 코드와 같은 새 버전의 `GraphicsClass`를 릴리스하기 전까지는 응용 프로그램을 아무런 문제 없이 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideInheritance#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_3.cs)]  
  
 새 버전의 `GraphicsClass`에는 `DrawRectangle`이라는 메서드가 들어 있습니다.  처음에는 아무런 일도 일어나지 않습니다.  새 버전은 이전 버전과 이진 호환됩니다.  새 클래스가 컴퓨터 시스템에 설치된 경우에도 배포한 소프트웨어는 계속 작동합니다.  메서드 `DrawRectangle`에 대한 기존의 모든 호출은 파생 클래스에서 기존 버전을 계속하여 참조합니다.  
  
 그러나 새 버전의 `GraphicsClass`를 사용하여 응용 프로그램을 다시 컴파일하면 컴파일러에서 CS0108 경고가 발생합니다.  이 경고는 응용 프로그램에서 `DrawRectangle` 메서드가 동작하는 방식을 고려해야 한다는 사실을 알립니다.  
  
 사용자의 메서드로 새 기본 클래스 메서드를 재정의하려면 `override` 키워드를 사용합니다.  
  
 [!code-cs[csProgGuideInheritance#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_4.cs)]  
  
 `override` 키워드를 사용하면 `YourDerivedGraphicsClass`에서 파생된 모든 개체에 파생 클래스 버전의 `DrawRectangle`이 사용됩니다.  `YourDerivedGraphicsClass`에서 파생된 개체는 base 키워드를 사용하여 기본 클래스 버전의 `DrawRectangle`에 액세스할 수 있습니다.  
  
 [!code-cs[csProgGuideInheritance#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_5.cs)]  
  
 사용자의 메서드로 새 기본 클래스 메서드를 재정의하지 않으려면 다음 사항을 고려해야 합니다.  두 메서드를 혼동하지 않도록 메서드의 이름을 변경할 수 있습니다.   이렇게 하는 데는 많은 시간이 걸리고 오류가 발생할 수 있으며 상황에 따라서는 불가능한 작업일 수도 있습니다.  그러나 프로젝트가 비교적 작은 경우에는 Visual Studio의 리팩터링 옵션을 사용하여 메서드의 이름을 바꿀 수 있습니다.  자세한 내용은 [Refactoring Classes and Types \(Class Designer\)](/visual-studio/ide/refactoring-classes-and-types-class-designer)을 참조하십시오.  
  
 또는 파생 클래스 정의에 `new` 키워드를 사용하여 경고를 방지할 수 있습니다.  
  
 [!code-cs[csProgGuideInheritance#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_6.cs)]  
  
 `new` 키워드를 사용하는 것은 사용자의 정의가 기본 클래스에 포함된 정의를 숨긴다는 점을 컴파일러에 알리는 것입니다.  이것은 기본적인 동작입니다.  
  
## 재정의 및 메서드 선택  
 클래스에서 메서드 이름을 지정한 경우, 이름이 동일한 메서드가 두 개이고 전달된 매개 변수와 호환되는 매개 변수가 있는 경우와 같이 호출할 수 있는 메서드가 여러 개 있으면 C\# 컴파일러에서 가장 적합한 메서드를 선택합니다.  다음은 호환될 수 있는 메서드입니다.  
  
 [!code-cs[csProgGuideInheritance#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_7.cs)]  
  
 `Derived`의 인스턴스에 대한 `DoWork`를 호출할 때 C\# 컴파일러는 우선 `Derived`에 원래 선언된 버전의 `DoWork`와 호환되는 호출을 시도합니다.  재정의 메서드는 클래스에서 선언된 것으로 간주되지 않으며 기본 클래스에서 선언된 메서드의 새 구현으로 간주됩니다.  C\# 컴파일러가 `Derived`의 원래 메서드에 메서드 호출을 일치시킬 수 없는 경우에만 동일한 이름과 호환되는 매개 변수를 사용하여 재정의된 메서드에 호출을 일치시키려 시도합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideInheritance#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_8.cs)]  
  
 변수 `val`은 double로 암시적으로 변환할 수 있으므로 C\# 컴파일러에서는 `DoWork(double)`를 `DoWork(int)` 대신 호출합니다.  이를 방지하는 데는 두 가지 방법이 있습니다.  첫 번째 방법은 동일한 이름의 새 메서드를 가상 메서드로 선언하지 않는 것입니다.  두 번째 방법으로는 `Derived`의 인스턴스를 `Base`로 캐스팅하여 기본 클래스 메서드 목록을 검색하여 가상 메서드를 호출하도록 C\# 컴파일러에 지시할 수 있습니다.  이 메서드는 가상이므로 `Derived`에 대한 `DoWork(int)`의 구현이 호출됩니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideInheritance#34](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_9.cs)]  
  
 예제 `new` 및 `override`를 참조 하십시오 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [메서드](../../../fsharp/language-reference/members/methods.md)   
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)