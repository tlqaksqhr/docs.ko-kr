---
title: "문(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 문"
  - "문[C#], 문 정보"
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# 문(C# 프로그래밍 가이드)
프로그램이 취하는 동작은 문으로 표현됩니다.  일반적인 동작에는 지정된 조건에 따라 변수 선언, 값 할당, 메서드 호출, 컬렉션 반복, 다른 코드 블록으로 분기 등이 포함됩니다.  프로그램에서 문이 실행되는 순서는 제어 흐름 또는 실행 흐름이라고 합니다.  제어 흐름은 런타임에 들어 오는 입력에 프로그램이 대응하는 방식에 따라 프로그램이 실행될 때마다 달라집니다.  
  
 문은 세미콜론으로 끝나는 한 줄의 코드로 구성될 수도 있고 한 줄로 된 문이 여러 개가 포함된 블록이 될 수도 있습니다.  문 블록은 {} 괄호로 묶이며 중첩된 블록을 포함할 수 있습니다.  다음 코드에서는 한 줄로 된 문과 여러 줄로 된 문 블록의 예를 보여 줍니다.  
  
 [!code-cs[csProgGuideStatements#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_1.cs)]  
  
## 문의 종류  
 다음 표에서는 C\#의 다양한 문 종류와 관련 키워드 및 자세한 정보를 포함하는 항목에 대한 링크를 보여 줍니다.  
  
|범주|C\# 키워드\/참고|  
|--------|-----------------|  
|선언 문|선언 문은 새 변수 또는 상수를 소개합니다.  필요한 경우 변수 선언에서 변수에 값을 할당할 수도 있습니다.  상수 선언에서는 반드시 값을 할당해야 합니다.<br /><br /> [!code-cs[csProgGuideStatements#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_2.cs)]|  
|식 문|값을 계산하는 식 문에서는 변수에 값을 저장해야 합니다.<br /><br /> [!code-cs[csProgGuideStatements#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_3.cs)]|  
|[선택 문](../../../csharp/language-reference/keywords/selection-statements.md)|선택 문을 사용하면 하나 이상의 지정된 조건에 따라 다른 코드 섹션으로 분기할 수 있습니다.  자세한 내용은 다음 항목을 참조하십시오.<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)|반복 문을 사용하면 배열과 같은 컬렉션을 반복하거나 지정된 조건이 충족될 때까지 동일한 문 집합을 반복적으로 수행할 수 있습니다.  자세한 내용은 다음 항목을 참조하십시오.<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[점프 문](../../../csharp/language-reference/keywords/jump-statements.md)|점프 문을 사용하면 제어를 다른 코드 섹션으로 이동할 수 있습니다.  자세한 내용은 다음 항목을 참조하십시오.<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[예외 처리문](../../../csharp/language-reference/keywords/exception-handling-statements.md)|예외 처리문을 사용하면 런타임에 발생하는 예외 조건으로부터 적절하게 복구할 수 있습니다.  자세한 내용은 다음 항목을 참조하십시오.<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try\-catch](../../../csharp/language-reference/keywords/try-catch.md), [try\-finally](../../../csharp/language-reference/keywords/try-finally.md), [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Checked 및 unchecked 문을 사용하면 너무 작아서 결과 값을 보유할 수 없는 변수에 결과가 저장될 때 숫자 연산에서 오버플로가 발생할 수 있는지 여부를 지정할 수 있습니다.  자세한 내용은 [checked](../../../csharp/language-reference/keywords/checked.md) 및 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)를 참조하십시오.|  
|`await` 문|메서드를 표시 하는 경우는  [비동기](../../../csharp/language-reference/keywords/async.md) 한정자를 사용할 수 있습니다에서  [기다립니다](../../../csharp/language-reference/keywords/await.md) 연산자 메서드를.  때 충전을 제어는 `await` 식의 비동기 메서드에 제어를 호출자에 게 반환 하 고 메서드가 진행 바뀌게 작업이 완료 될 때까지 일시 중단 됩니다.  작업이 완료 되 면 실행 메서드를 다시 시작할 수 있습니다.<br /><br /> "비동기 방법" 섹션의 간단한 예제를 참조 하십시오 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md).  자세한 내용은 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.|  
|`yield return` 문|목록 또는 배열 등의 컬렉션에서 사용자 지정 반복을 수행 하는 반복기입니다.  반복기를 사용 하는  [수익률 반환](../../../csharp/language-reference/keywords/yield.md) 문은 각 요소는 한 번에 반환 합니다.  경우는 `yield return` 코드에서 현재 위치 문의 도달 기억 됩니다.  다음에 반복기가 호출 되 면 해당 위치에서 실행이 다시 시작 됩니다.<br /><br /> 자세한 내용은 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.|  
|`fixed` 문|fixed 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다.  자세한 내용은 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)를 참조하십시오.|  
|`lock` 문|lock 문을 사용하면 코드 블록에 대한 액세스를 한 번에 하나의 스레드로 제한할 수 있습니다.  자세한 내용은 [lock](../../../csharp/language-reference/keywords/lock-statement.md)을 참조하십시오.|  
|레이블 문|문에 레이블을 지정한 다음 [goto](../../../csharp/language-reference/keywords/goto.md) 키워드를 사용하여 해당 레이블이 지정된 문으로 이동할 수 있습니다.  다음 행의 예제를 참조하십시오.|  
|빈 문|빈 문은 하나의 세미콜론으로 구성됩니다.  빈 문은 아무런 작업도 수행하지 않으므로 문이 필요하지만 동작을 수행할 필요가 없는 경우에 사용됩니다.  다음 예제에서는 빈 문을 사용하는 두 가지 경우를 보여 줍니다.<br /><br /> [!code-cs[csProgGuideStatements#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_4.cs)]|  
  
## 포함 문  
 [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) 및 [foreach](../../../csharp/language-reference/keywords/foreach-in.md)를 비롯한 일부 문의 뒤에는 반드시 포함 문이 옵니다.  이러한 포함 문은 하나의 문일 수도 있고 여러 개의 문이 {} 괄호로 묶인 문 블록일 수도 있습니다.  한 줄로 된 포함 문도 다음 예제와 같이 {} 괄호로 묶일 수 있습니다.  
  
 [!code-cs[csProgGuideStatements#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_5.cs)]  
  
 {} 괄호로 묶이지 않은 포함 문은 선언 문이나 레이블 문이 될 수 없습니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cs[csProgGuideStatements#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_6.cs)]  
  
 오류를 수정하려면 포함 문을 블록 안에 배치합니다.  
  
 [!code-cs[csProgGuideStatements#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_7.cs)]  
  
## 중첩 문 블록  
 다음 예제에서와 같이 문 블록은 중첩될 수 있습니다.  
  
 [!code-cs[csProgGuideStatements#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_8.cs)]  
  
## 접근할 수 없는 문  
 컴파일러가 제어 흐름이 어떤 경우에도 특정 문에 도달할 수 없다고 판단하는 경우 다음 예제와 같이 경고 CS0162가 생성됩니다.  
  
 [!code-cs[csProgGuideStatements#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_9.cs)]  
  
## 관련 단원  
  
-   [문 키워드](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [식](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)