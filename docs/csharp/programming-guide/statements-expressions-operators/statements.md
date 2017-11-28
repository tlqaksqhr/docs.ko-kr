---
title: "문(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 166130ca7a63127d0bd1df8328dc08b4a8cd7845
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="statements-c-programming-guide"></a>문(C# 프로그래밍 가이드)
프로그램이 수행하는 작업은 문으로 표현됩니다. 일반적인 작업으로 지정된 조건에 따라 변수 선언, 값 할당, 메서드 호출, 컬렉션 반복, 하나 또는 다른 코드 블록으로 분기 등이 있습니다. 프로그램에서 문이 실행되는 순서를 제어 흐름 또는 실행 흐름이라고 합니다. 제어 흐름은 프로그램이 런타임 시 수신하는 입력에 대응하는 방식에 따라 프로그램을 실행할 때마다 달라질 수 있습니다.  
  
 문은 세미콜론으로 끝나는 코드 한 줄이나 일련의 한 줄 문으로 이루어진 블록일 수 있습니다. 문 블록은 {} 괄호로 묶여 있으며 중첩 블록을 포함할 수 있습니다. 다음 코드는 한 줄 문과 여러 줄 문 블록의 두 가지 예제를 보여 줍니다.  
  
 [!code-csharp[csProgGuideStatements#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_1.cs)]  
  
## <a name="types-of-statements"></a>문 유형  
 다음 표에는 다양한 유형의 C# 문과 관련 키워드가 나와 있으며 자세한 정보를 포함하는 항목에 대한 링크가 있습니다.  
  
|범주|C# 키워드/참고 사항|  
|--------------|---------------------------|  
|선언문|선언문은 새 변수 또는 상수를 소개합니다. 필요에 따라 변수 선언에서 변수에 값을 할당할 수 있습니다. 상수 선언에서 대입은 필수입니다.<br /><br /> [!code-csharp[csProgGuideStatements#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_2.cs)]|  
|식 문|값을 계산하는 식 문은 값을 변수에 저장해야 합니다.<br /><br /> [!code-csharp[csProgGuideStatements#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_3.cs)]|  
|[선택 문](../../../csharp/language-reference/keywords/selection-statements.md)|선택 문을 사용하면 하나 이상의 지정된 조건에 따라 코드의 다른 섹션으로 분기할 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)|반복 문을 사용하면 배열과 같은 컬렉션을 반복하거나, 지정한 조건이 충족될 때까지 동일한 문 집합을 반복해서 수행할 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[점프 문](../../../csharp/language-reference/keywords/jump-statements.md)|점프 문은 컨트롤을 다른 코드 섹션으로 전송합니다. 자세한 내용은 다음 항목을 참조하세요.<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[예외 처리 문](../../../csharp/language-reference/keywords/exception-handling-statements.md)|예외 처리 문을 사용하면 런타임 시 발생하는 예외 조건에서 정상적으로 복구할 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try-catch](../../../csharp/language-reference/keywords/try-catch.md), [try-finally](../../../csharp/language-reference/keywords/try-finally.md), [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|checked 및 unchecked 문을 사용하면 결과가 저장되는 변수가 너무 작아서 결과 값을 수용할 수 없는 경우 수치 연산에서 오버플로가 발생할 수 있는지 여부를 지정할 수 있습니다. 자세한 내용은 [checked](../../../csharp/language-reference/keywords/checked.md) 및 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)를 참조하세요.|  
|`await` 문|메서드에 [async](../../../csharp/language-reference/keywords/async.md) 한정자를 표시하면 메서드에서 [await](../../../csharp/language-reference/keywords/await.md) 연산자를 사용할 수 있습니다. 컨트롤이 비동기 메서드의 `await` 식에 도달하면 컨트롤이 호출자로 돌아가고 대기 중인 작업이 완료될 때까지 메서드의 진행이 일시 중단됩니다. 작업이 완료되면 메서드가 실행이 다시 시작될 수 있습니다.<br /><br /> 간단한 예제는 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)의 "Async 메서드" 섹션을 참조하세요. 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md)을 참조하세요.|  
|`yield return` 문|반복기는 배열 목록과 같은 컬렉션에 대해 사용자 지정 반복을 수행합니다. 반복기는 [yield return](../../../csharp/language-reference/keywords/yield.md) 문을 사용하여 각 요소를 한 번에 하나씩 반환합니다. `yield return` 문에 도달하면 코드의 현재 위치가 기억됩니다. 다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.<br /><br /> 자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.|  
|`fixed` 문|fixed 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다. 자세한 내용은 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)를 참조하세요.|  
|`lock` 문|lock 문을 사용하면 한 번에 하나의 스레드만 코드 블록에 액세스할 수 있도록 제한할 수 있습니다. 자세한 내용은 [lock](../../../csharp/language-reference/keywords/lock-statement.md)을 참조하세요.|  
|레이블 문|문에 레이블을 지정한 다음 [goto](../../../csharp/language-reference/keywords/goto.md) 키워드를 사용하여 레이블 문으로 점프합니다. 다음 행의 예제를 참조하세요.|  
|빈 문|빈 문은 하나의 세미콜론으로 구성됩니다. 아무 작업도 수행하지 않으며, 문이 필요하지만 아무 작업도 수행할 필요가 없는 위치에서 사용할 수 있습니다. 다음 예제에서는 빈 문의 두 가지 사용을 보여 줍니다.<br /><br /> [!code-csharp[csProgGuideStatements#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_4.cs)]|  
  
## <a name="embedded-statements"></a>포함 문  
 [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) 및 [foreach](../../../csharp/language-reference/keywords/foreach-in.md)를 비롯한 일부 문은 항상 포함 문이 뒤에 나옵니다. 이 포함 문은 단일 문이나 문 블록에서 {} 괄호로 묶인 여러 문일 수 있습니다. 한 줄로 된 각 포함 문을 다음 예제와 같이 {} 괄호로 묶을 수 있습니다.  
  
 [!code-csharp[csProgGuideStatements#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_5.cs)]  
  
 {} 괄호로 묶이지 않은 포함 문은 선언문 또는 레이블 문이 될 수 없습니다. 이는 다음 예제에서 확인할 수 있습니다.  
  
 [!code-csharp[csProgGuideStatements#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_6.cs)]  
  
 오류를 해결하려면 포함 문을 블록에 배치합니다.  
  
 [!code-csharp[csProgGuideStatements#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_7.cs)]  
  
## <a name="nested-statement-blocks"></a>중첩된 문 블록  
 다음 코드와 같이 문 블록을 중첩할 수 있습니다.  
  
 [!code-csharp[csProgGuideStatements#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_8.cs)]  
  
## <a name="unreachable-statements"></a>연결할 수 없는 문  
 상황에 따라 제어 흐름이 특정 문에 연결할 수 없다고 확인될 경우 컴파일러는 다음 예제와 같이 경고 CS0162를 생성합니다.  
  
 [!code-csharp[csProgGuideStatements#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_9.cs)]  
  
## <a name="related-sections"></a>관련 단원  
  
-   [문 키워드](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [식](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
