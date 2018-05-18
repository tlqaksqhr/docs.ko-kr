---
title: '방법: 대리자 조합(멀티캐스트 대리자)(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: e1214a4d281dbcb9d8186770b68510d3d9a4b15f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>방법: 대리자 조합(멀티캐스트 대리자)(C# 프로그래밍 가이드)
이 예제에서는 멀티캐스트 대리자를 만드는 방법을 보여 줍니다. [대리자](../../../csharp/language-reference/keywords/delegate.md) 개체의 유용한 속성은 `+` 연산자를 사용하여 하나의 대리자 인스턴스에 여러 개체를 할당할 수 있다는 것입니다. 멀티캐스트 대리자는 할당된 대리자 목록을 포함합니다. 멀티캐스트 대리자가 호출되면 목록에 있는 대리자가 순서대로 호출됩니다. 같은 형식의 대리자만 결합할 수 있습니다.  
  
 `-` 연산자는 멀티캐스트 대리자에서 구성 요소 대리자를 제거하는 데 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.MulticastDelegate>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [이벤트](../../../csharp/programming-guide/events/index.md)
