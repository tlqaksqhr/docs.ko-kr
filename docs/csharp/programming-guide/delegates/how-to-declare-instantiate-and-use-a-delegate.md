---
title: "방법: 대리자 선언, 인스턴스화 및 사용(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5a5329b9e99fcd5830a57eb8f97b4edb67ad8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a>방법: 대리자 선언, 인스턴스화 및 사용(C# 프로그래밍 가이드)
C# 1.0 이상 버전에서는 다음 예제와 같이 대리자를 선언할 수 있습니다.  
  
 [!code-csharp[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 C# 2.0에서는 다음 예제와 같이 더욱 간단한 방법으로 이전 선언을 쓸 수 있습니다.  
  
 [!code-csharp[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 C# 2.0 이상 버전에서는 다음 예제와 같이 익명 메서드를 사용하여 [delegate](../../../csharp/language-reference/keywords/delegate.md)를 선언하고 초기화할 수도 있습니다.  
  
 [!code-csharp[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 C# 3.0 이상에서는 다음 예제와 같이 람다 식을 사용하여 대리자를 선언하고 인스턴스화할 수도 있습니다.  
  
 [!code-csharp[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.  
  
 다음 예제에서는 대리자를 선언, 인스턴스화 및 사용하는 방법을 보여 줍니다. `BookDB` 클래스는 책 데이터베이스를 유지 관리하는 서점 데이터베이스를 캡슐화합니다. 그리고 데이터베이스의 모든 문고판 책을 찾아 각 책에 대해 대리자를 호출하는 `ProcessPaperbackBooks` 메서드를 표시합니다. 이때 사용되는 `delegate` 형식의 이름은 `ProcessBookDelegate`입니다. `Test` 클래스는 이 클래스를 사용하여 문고판 책의 제목과 평균 가격을 인쇄합니다.  
  
 대리자를 사용하면 서점 데이터베이스와 클라이언트 코드 간에 기능을 효율적으로 구분할 수 있습니다. 클라이언트 코드는 책이 저장되는 방식이나 서점 코드가 문고판 책을 찾는 방식을 알 수 없습니다. 서점 코드는 발견된 문고판 책에 대해 수행되는 처리를 알 수 없습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
-   대리자 선언  
  
     다음 문은 새 대리자 형식을 선언합니다.  
  
     [!code-csharp[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     각 대리자 형식은 인수의 수와 형식 및 캡슐화 가능한 메서드의 형식과 반환 값을 설명합니다. 새 인수 형식 또는 반환 값 형식 집합이 필요할 때마다 새 대리자 형식을 선언해야 합니다.  
  
-   대리자 인스턴스화  
  
     대리자 형식을 선언한 후에는 대리자 개체를 생성하여 특정 메서드와 연결해야 합니다. 이전 예제의 경우 다음 예제와 같이 `PrintTitle` 메서드를 `ProcessPaperbackBooks` 메서드에 전달하여 이 작업을 수행합니다.  
  
     [!code-csharp[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     이렇게 하면 [정적](../../../csharp/language-reference/keywords/static.md) 메서드 `Test.PrintTitle`에 연결된 새 대리자 개체가 생성됩니다. 마찬가지로 개체 `totaller`의 비정적 메서드 `AddBookToTotal`도 다음 예제와 같이 전달됩니다.  
  
     [!code-csharp[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     두 경우 모두 새 대리자 개체가 `ProcessPaperbackBooks` 메서드로 전달됩니다.  
  
     대리자를 만든 후에도 대리자가 연결된 메서드는 변경되지 않습니다. 대리자 개체는 변경이 불가능합니다.  
  
-   대리자 호출  
  
     생성된 대리자 개체는 대개 대리자를 호출하는 다른 코드로 전달됩니다. 대리자 개체의 이름 뒤에 대리자로 전달할 인수를 괄호로 묶어 추가한 형식을 사용하여 대리자 개체를 호출합니다. 아래에 대리자 호출의 예가 나와 있습니다.  
  
     [!code-csharp[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     대리자는 이 예제와 같이 동기적으로 호출할 수도 있고 `BeginInvoke` 및 `EndInvoke` 메서드를 사용하여 비동기적으로 호출할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [이벤트](../../../csharp/programming-guide/events/index.md)  
 [대리자](../../../csharp/programming-guide/delegates/index.md)
