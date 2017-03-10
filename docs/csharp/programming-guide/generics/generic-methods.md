---
title: "제네릭 메서드(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "제네릭[C#], 메서드"
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# 제네릭 메서드(C# 프로그래밍 가이드)
제네릭 메서드는 다음과 같이 형식 매개 변수를 사용하여 선언한 메서드입니다.  
  
 [!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_1.cs)]  
  
 다음 코드 예제에서는 형식 인수에 `int`를 사용하여 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_2.cs)]  
  
 형식 인수를 생략하고 컴파일러에서 이를 자동으로 유추하도록 할 수도 있습니다.  `Swap`에 대한 다음 호출은 위 예제의 호출과 동일한 작업을 수행합니다.  
  
 [!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_3.cs)]  
  
 정적 메서드와 인스턴스 메서드에는 형식 유추를 위한 동일한 규칙이 적용됩니다.  컴파일러에서는 사용자가 전달하는 메서드 인수를 기준으로 형식 매개 변수를 유추할 수 있지만 제약 조건이나 반환 값만으로는 형식 매개 변수를 유추할 수 없습니다.  따라서 매개 변수가 없는 메서드에 대해서는 형식 유추가 실행되지 않습니다.  형식 유추는 컴파일러에서 오버로드된 메서드 시그니처를 확인하려고 하기 전에 컴파일 타임에 진행됩니다.  컴파일러는 동일한 이름을 공유하는 모든 제네릭 메서드에 형식 유추 논리를 적용합니다.  오버로드 확인 단계에서 컴파일러는 형식 유추에 성공한 제네릭 메서드만 포함합니다.  
  
 제네릭 클래스 내에서 제네릭이 아닌 메서드는 다음과 같이 클래스 수준 형식 매개 변수에 액세스할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_4.cs)]  
  
 포함하는 클래스와 동일한 형식 매개 변수를 사용하는 제네릭 메서드를 정의하면 컴파일러에서 CS0693 경고가 발생합니다. 이는 메서드 범위 내에서 내부 `T`에 대해 제공한 인수가 외부 `T`에 대해 제공한 인수를 숨기기 때문입니다.  클래스를 인스턴스화할 때 제공한 인수가 아닌 다른 형식 인수를 사용하여 제네릭 클래스 메서드를 호출할 수 있으려면 다음 예제의 `GenericList2<T>`에서와 같이 메서드의 형식 매개 변수에 다른 식별자를 제공하는 것이 좋습니다.  
  
 [!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_5.cs)]  
  
 메서드에서 형식 매개 변수에 대한 더 구체적인 작업을 수행하려면 제약 조건을 사용합니다.  `SwapIfGreater<T>`라는 이 버전의 `Swap<T>`은 <xref:System.IComparable%601>을 구현하는 형식 인수와만 함께 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_6.cs)]  
  
 제네릭 메서드는 여러 형식 매개 변수에 대해 오버로드할 수 있습니다.  예를 들어 다음 메서드는 모두 동일한 클래스에 지정할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_7.cs)]  
  
## C\# 언어 사양  
 자세한 내용은 [C\# 언어 사양](../../../csharp/language-reference/language-specification.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)