---
title: "제네릭 인터페이스(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0326a7bc459c641cbfafe39fe36525a947051c16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generic-interfaces-c-programming-guide"></a>제네릭 인터페이스(C# 프로그래밍 가이드)
제네릭 컬렉션 클래스에 대한 인터페이스 또는 컬렉션의 항목을 나타내는 제네릭 클래스에 대한 인터페이스를 정의하는 것이 대개 유용합니다. 값 형식에 대해 boxing 및 unboxing 연산을 하지 않으려면 제네릭 클래스에서 <xref:System.IComparable> 대신 <xref:System.IComparable%601>과 같은 제네릭 인터페이스를 사용하는 것이 좋습니다. .NET Framework 클래스 라이브러리에는 <xref:System.Collections.Generic> 네임스페이스의 컬렉션 클래스에 사용할 제네릭 인터페이스가 여러 개 정의되어 있습니다.  
  
 인터페이스를 형식 매개 변수에 대한 제약 조건으로 지정한 경우 이 인터페이스를 구현하는 형식만 사용할 수 있습니다. 다음 코드 예제는 `GenericList<T>` 클래스에서 파생되는 `SortedList<T>` 클래스를 보여 줍니다. 자세한 내용은 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)를 참조하세요. `SortedList<T>`는 `where T : IComparable<T>` 제약 조건을 추가합니다. 이렇게 하면 `SortedList<T>`의 `BubbleSort` 메서드가 목록 요소에서 제네릭 <xref:System.IComparable%601.CompareTo%2A> 메서드를 사용할 수 있게 됩니다. 이 예제에서 목록 요소는 `IComparable<Person>`을 구현하는 단순 클래스인 `Person`입니다.  
  
 [!code-csharp[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 단일 형식에 다음과 같이 여러 인터페이스를 제약 조건으로 지정할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 하나의 인터페이스는 다음과 같은 두 개 이상의 형식 매개 변수를 정의할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 클래스에 적용되는 상속 규칙은 인터페이스에도 적용됩니다.  
  
 [!code-csharp[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 제네릭 인터페이스에 반공변성(Contravariance)이 있는 경우, 즉 형식 매개 변수만 반환 값으로 사용하는 경우 제네릭 인터페이스는 제네릭이 아닌 인터페이스에서 상속할 수 있습니다. .NET Framework 클래스 라이브러리에서 <xref:System.Collections.Generic.IEnumerable%601>은 <xref:System.Collections.IEnumerable>에서 상속하는데, 이는 <xref:System.Collections.Generic.IEnumerable%601>이 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>의 반환 값과 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 속성 getter에 `T`만 사용하기 때문입니다.  
  
 구체적인 클래스는 다음과 같이 폐쇄형으로 생성된 인터페이스를 구현할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 클래스 매개 변수 목록이 다음과 같이 인터페이스에 필요한 모든 인수를 제공하는 경우에 한해 제네릭 클래스는 제네릭 인터페이스 또는 폐쇄형으로 생성된 인터페이스를 구현할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 제네릭 클래스, 제네릭 구조체 또는 제네릭 인터페이스 내의 메서드에는 메서드 오버로드를 제어하는 규칙이 동일하게 적용됩니다. 자세한 내용은 [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [interface](../../../csharp/language-reference/keywords/interface.md)  
 [제네릭](~/docs/standard/generics/index.md)
