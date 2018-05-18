---
title: 명시적 인터페이스 구현(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 7494f7d6a3897d56419f9d3aa96668fd9dab5f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>명시적 인터페이스 구현(C# 프로그래밍 가이드)
[클래스](../../../csharp/language-reference/keywords/class.md)가 시그니처가 동일한 멤버를 포함하는 두 인터페이스를 구현하는 경우, 해당 멤버를 클래스에 구현하면 양쪽 인터페이스 모두가 해당 멤버를 구현에 사용합니다. 다음 예제에서 `Paint`에 대한 모든 호출은 같은 메서드를 호출합니다.  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 그러나 두 [인터페이스](../../../csharp/language-reference/keywords/interface.md)가 동일한 기능을 수행하지 않을 경우, 인터페이스 둘 중 하나 또는 둘 다 잘못 구현될 수 있습니다. 인터페이스를 통해서만 호출되고 특정 인터페이스에만 관련되는 클래스 멤버를 만드는 방식으로 인터페이스 멤버를 명시적으로 구현할 수 있습니다. 이렇게 하려면 인터페이스 이름과 마침표를 사용하여 클래스 멤버의 이름을 지정해야 합니다. 예:  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 클래스 멤버 `IControl.Paint`는 `IControl` 인터페이스를 통해서만 사용할 수 있고 `ISurface.Paint`는 `ISurface`를 통해서만 사용할 수 있습니다. 두 메서드 구현은 서로 별개이며 어느 쪽도 클래스에서 직접 사용할 수 없습니다. 예:  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 명시적 구현은 또한 두 인터페이스가 속성과 메서드와 같이 동일한 이름을 가진 서로 다른 멤버를 선언하는 사례를 해결하는 데 사용됩니다.  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 두 인터페이스를 모두 구현하려면 클래스는 P 속성이나 P 메서드 중 하나 또는 모두에 대해 명시적 구현을 사용하여 컴파일러 오류를 방지해야 합니다. 예:  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)  
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
