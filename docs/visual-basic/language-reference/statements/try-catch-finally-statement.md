---
title: "Try...Catch...Finally Statement (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Try...Catch...Finally"
  - "vb.when"
  - "vb.Finally"
  - "vb.Catch"
  - "vb.Try"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Try...Catch...Finally statements"
  - "Try statement"
  - "try-catch exception handling, Try...Catch...Finally statements"
  - "error handling, while running code"
  - "Try statement, Try...Catch...Finally"
  - "Finally keyword [Visual Basic], Try...Catch...Finally"
  - "Catch statement"
  - "When keyword"
  - "Visual Basic code, handling errors while running"
  - "structured exception handling, Try...Catch...Finally statements"
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
caps.handback.revision: 69
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Try...Catch...Finally Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 문을 사용하면 코드를 실행하면서 특정 코드 블록에서 발생할 수 있는 오류의 일부 또는 전부를 처리할 수 있습니다.  
  
## 구문  
  
```  
Try  
    [ tryStatements ]  
    [ Exit Try ]  
[ Catch [ exception [ As type ] ] [ When expression ]  
    [ catchStatements ]  
    [ Exit Try ] ]  
[ Catch ... ]  
[ Finally  
    [ finallyStatements ] ]  
End Try  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`tryStatements`|선택 사항입니다.  오류가 발생할 수 있는 문입니다.  복합 문도 가능합니다.|  
|`Catch`|선택 사항입니다.  여러 `Catch` 블록을 사용할 수 있습니다.  `Try` 블록을 처리하는 동안 예외가 발생하면 각 `Catch` 문을 텍스트 순서대로 검사하여 예외\(throw된 예외를 나타내는 `exception`\)를 처리했는지 여부를 확인합니다.|  
|`exception`|선택 사항입니다.  임의의 변수 이름입니다.  `exception`의 초기 값은 throw된 오류 값입니다.  `Catch`와 함께 사용되어 catch된 예외를 지정합니다.  이를 생략하면 `Catch` 문에서 모든 예외를 catch합니다.|  
|`type`|선택 사항입니다.  클래스 필터의 형식을 지정합니다.  `exception`의 값이 `type`에 의해 지정된 형식이거나 파생 형식인 경우 식별자가 예외 개체에 바인딩됩니다.|  
|`When`|선택 사항입니다.  `When` 절이 있는 `Catch` 문은 `expression`이 `True`인 경우에만 예외를 catch합니다.  `When` 절은 예외의 형식을 확인한 다음에만 적용되며 `expression`은 예외를 나타내는 식별자를 참조할 수도 있습니다.|  
|`expression`|선택 사항입니다.  `Boolean`으로 암시적으로 변환될 수 있어야 합니다.  일반 필터를 설명하는 임의의 식입니다.  일반적으로 오류 번호로 필터링하는 데 사용됩니다.  `When` 키워드와 함께 사용되어 오류가 catch되는 상황을 지정합니다.|  
|`catchStatements`|선택 사항입니다.  연결된 `Try` 블록에서 발생하는 오류를 처리하는 문입니다.  복합 문도 가능합니다.|  
|`Exit Try`|선택 사항입니다.  `Try...Catch...Finally` 구조를 중단하는 키워드입니다.  `End Try` 문 바로 다음의 코드를 사용하여 실행을 다시 시작합니다.  `Finally` 문도 여전히 실행됩니다.  `Finally` 블록에서는 이 키워드를 사용할 수 없습니다.|  
|`Finally`|선택 사항입니다.  `Finally` 블록은 실행이 `Try...Catch` 문의 일부를 벗어날 때 항상 실행됩니다.|  
|`finallyStatements`|선택 사항입니다.  다른 모든 오류 처리가 완료된 후 실행되는 문입니다.|  
|`End Try`|`Try...Catch...Finally` 구조를 끝냅니다.|  
  
## 설명  
 특정 코드 섹션을 실행하는 동안 특정 예외가 발생할 수 있을 것으로 예상되는 경우에는 해당 코드를 `Try` 블록에 넣고 `Catch` 블록을 사용하여 예외 발생 시 제어를 유지하고 해당 예외를 처리합니다.  
  
 `Try…Catch` 문은 다양한 예외의 처리기를 지정하는 `Try` 블록과 하나 이상의 `Catch` 절로 구성되어 있습니다.  `Try` 블록에 예외가 throw되면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 예외를 처리하는 `Catch` 문을 검색합니다.  일치하는 `Catch` 문을 찾을 수 없는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]이 현재 메서드를 호출한 메서드부터 콜 스택까지 조사합니다.  `Catch` 블록을 찾지 못하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 사용자에게 처리되지 않은 예외 메시지를 표시하고 프로그램 실행을 중지합니다.  
  
 `Try…Catch` 문에서 `Catch` 문을 두 개 이상 사용할 수 있습니다.  이렇게 할 경우 `Catch` 절은 순서대로 검사되므로 해당 절의 순서가 중요합니다.  보다 구체적인 예외를 먼저 catch하십시오.  
  
 다음 `Catch` 문 조건은 가장 일반적인 것이며 <xref:System.Exception> 클래스에서 파생되는 모든 예외를 catch합니다.  이러한 종류의 Catch 문은 일반적으로 `Catch` 구조에서 예상되는 특정 예외를 모두 catch한 후에 마지막 `Try...Catch...Finally` 블록으로 사용해야 합니다.  제어 흐름은 이러한 변형 중 하나를 따르는 `Catch` 블록에 도달할 수 없습니다.  
  
-   `type`은 `Exception`입니다\(예: `Catch ex As Exception`\).  
  
-   이 문에는 `exception` 변수가 없습니다\(예: `Catch`\).  
  
 `Try…Catch…Finally` 문이 다른 `Try` 블록에 중첩되어 있는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 가장 안쪽의 `Try` 블록에 있는 각 `Catch` 문을 먼저 검사합니다.  일치하는 `Catch` 문이 없을 경우 바깥쪽 `Try…Catch…Finally` 블록의 `Catch` 문으로 검색이 계속 진행됩니다.  
  
 `Try` 블록과 `Catch` 블록은 별개의 블록이므로 Try 블록의 지역 변수를 Catch 블록에 사용할 수 없습니다.  둘 이상의 블록에서 변수를 사용하려면 `Try...Catch...Finally` 구조의 외부에서 변수를 선언해야 합니다.  
  
> [!TIP]
>  `Try…Catch…Finally` 문을 IntelliSense 코드 조각으로 사용할 수 있습니다.  코드 조각 관리자에서 **코드 패턴 \- If, For Each, Try Catch, Property 등**을 확장한 다음 **오류 처리\(예외\)**를 확장합니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## Finally 블록  
 `Try` 구조체를 끝내기 전에 실행할 문이 하나 이상 있으면 `Finally` 블록을 사용합니다.  `Try…Catch` 구조체에서 벗어나기 바로 전에 `Finally` 블록으로 제어가 전달됩니다.  `Try` 구조체 내부에서 예외가 발생하더라도 마찬가지입니다.  
  
 예외가 있더라도 반드시 실행해야 하는 코드를 실행하는 데에는 `Finally` 블록이 유용합니다.  제어는 `Try...Catch` 블록이 종료되는 방법에 관계없이 `Finally` 블록으로 전달됩니다.  
  
 `Finally` 블록의 코드는 `Try` 또는 `Catch` 블록에서 코드가 `Return` 문을 만나더라도 실행됩니다.  다음과 같은 경우에는 `Try` 또는 `Catch` 블록에서 해당 `Finally` 블록으로 제어가 전달되지 않습니다.  
  
-   `Try` 또는 `Catch` 블록에서 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)을 만난 경우  
  
-   `Try` 또는 `Catch` 블록에서 <xref:System.StackOverflowException>이 throw된 경우  
  
 명시적으로 실행을 전송할 수 없는 한 `Finally` 블록.  실행 중에 전송 된 `Finally` 블록 올바르지 않습니다 통해 예외를 제외 하 고.  
  
 `Try` 문에 적어도 하나의 `Catch` 블록을 포함하지 않는 경우 `Finally` 블록을 포함해야 합니다.  
  
> [!TIP]
>  특정 예외를 catch할 필요가 없는 경우, `Try…Finally` 블록처럼 동작하는 `Using` 문을 사용하면 블록 종료 방식에 관계없이 리소스를 삭제할 수 있습니다.  이는 처리되지 않은 예외의 경우에도 해당합니다.  자세한 내용은 [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md)을 참조하십시오.  
  
## 예외 인수  
 `Catch` block `exception` 인수는 <xref:System.Exception> 클래스의 인스턴스이거나 `Exception` 클래스에서 파생되는 클래스의 인스턴스입니다.  `Exception` 클래스 인스턴스는 `Try` 블록에서 발생한 오류에 상응합니다.  
  
 `Exception` 개체의 속성을 통해 예외의 원인과 위치를 쉽게 확인할 수 있습니다.  예를 들어, 호출할 때 <xref:System.Exception.StackTrace%2A> 속성에 예외를 발생시킨 메서드가 나열되면 코드에서 오류 발생 위치를 쉽게 찾을 수 있습니다.  <xref:System.Exception.Message%2A>는 예외를 설명하는 메시지를 반환합니다.  <xref:System.Exception.HelpLink%2A>는 연결된 도움말 파일의 링크를 반환합니다.  <xref:System.Exception.InnerException%2A>은 현재 예외를 발생시킨 `Exception` 개체를 반환하고 원본 `Exception`이 없는 경우는 `Nothing`을 반환합니다.  
  
## Try…Catch 문 사용 시 고려 사항  
 `Try…Catch` 문은 비정상적이거나 예상하지 않은 프로그램 이벤트의 발생을 알리기 위해서만 사용합니다.  이유는 다음과 같습니다.  
  
-   런타임에 예외를 catch하면 추가 오버헤드가 발생하며 사전 검사로 예외를 회피하는 경우에 비해 더 느려질 수 있습니다.  
  
-   `Catch` 블록을 올바르게 처리하지 않으면 예외가 사용자에게 올바르게 보고되지 않을 수 있습니다.  
  
-   예외 처리를 사용하면 프로그램이 더 복잡해집니다.  
  
 발생 가능성이 높은 조건을 검사하기 위해 항상 `Try…Catch` 문을 사용할 필요는 없습니다.  다음 예제에서는 파일을 열기 전에 파일이 있는지 여부를 검사합니다.  이는 <xref:System.IO.File.OpenText%2A> 메서드에서 throw한 예외를 catch할 필요성을 줄여 줍니다.  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 `Catch` 블록의 코드가 스레드 보안 또는 적절한 메시지를 통해 사용자에게 예외를 올바르게 보고하는지 확인하십시오.  그렇지 않으면 예외를 알지 못할 수 있습니다.  
  
## 비동기 메서드  
 메서드를 표시 하는 경우는  [비동기](../../../visual-basic/language-reference/modifiers/async.md) 한정자를 사용할 수 있는  [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자 메서드를.  문을 사용 하 여는 `Await` 연산자 바뀌게 작업이 완료 될 때까지 메서드를 실행을 일시 중지 합니다.  작업 진행 중인 작업을 나타냅니다.  때 연관 된 작업의 `Await` 운영자 완료 같은 메서드에서 실행 다시 시작 합니다.  자세한 내용은 [비동기 프로그램의 제어 흐름](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 비동기 메서드가 반환 하는 작업 처리 되지 않은 예외로 인해를 완료 되었음을 나타내는 폴트 상태로 끝날 수 있습니다.  작업 결과 취소 상태에서 또한 끝날 수 있습니다는 `OperationCanceledException` await 식에서 throw 합니다.  어떤 유형의 예외를 catch 하려면 배치는 `Await` 작업에 연결 된 식의 `Try` 차단 하 고 예외를 catch는 `Catch` 블록.  예를 들어가이 항목의 뒷부분에 제공 됩니다.  
  
 여러 예외 해당 오류에 대 한 책임이 있기 때문에 작업 상태에 고장이 발생된 될 수 있습니다.  예를 들어, 작업 결과에 대 한 호출의 수 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  이러한 작업을 기다립니다 때 catch 된 예외는 예외 중 하나입니다 및 예외를 catch 됩니다 예측할 수 없습니다.  예를 들어가이 항목의 뒷부분에 제공 됩니다.  
  
 `Await` 내 식 수 없습니다는 `Catch` 블록 또는 `Finally` 블록.  
  
## 반복기  
 반복기 함수 또는 `Get` 접근자 컬렉션에서 사용자 지정 반복을 수행 합니다.  반복기를 사용 하는  [생성](../../../visual-basic/language-reference/statements/yield-statement.md) 문 컬렉션의 각 요소는 한 번에 반환 합니다.  반복기 함수를 사용 하 여 호출을 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 A `Yield` 문 수 내에 `Try` 블록.  A `Try` 포함 하는 블록을 `Yield` 문이 있을 수 있습니다 `Catch` 차단 하 고 있을 수 있습니다는 `Finally` 블록.  "Visual Basic 블록 시도" 절을 참조 하십시오 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md) 예입니다.  
  
 A `Yield` 문 수 없습니다 내는 `Catch` 블록 또는 `Finally` 블록.  
  
 경우는 `For Each` 본문 반복기 함수\) \(외부 예외를 throw는 `Catch` 함수의 반복기 블록 실행 되지 않는 그저 `Finally` 함수의 반복기 블록에서 실행 됩니다.  A `Catch` 블록 반복기 함수는 내부 catch 반복기 함수 내에서 발생 하는 예외에만 합니다.  
  
## 부분 신뢰 상황  
 네트워크 공유에 호스팅되는 응용 프로그램과 같은 부분 신뢰 상태에서 `Try...Catch...Finally`는 해당 호출이 포함된 메서드가 호출되기 전에 발생하는 보안 예외를 catch하지 않습니다.  다음 예제를 서버 공유에서 실행하면 "Sub System.Security.SecurityException: 요청하지 못했습니다."라는 오류가 발생합니다. 보안 예외에 대한 자세한 내용은 <xref:System.Security.SecurityException> 클래스를 참조하십시오.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 이러한 부분 신뢰 상태에서는 `Process.Start` 문을 별도의 `Sub`에 두어야 합니다.  이렇게 하면 첫 번째 `Sub`를 호출하지 못하며  `Process.Start`를 포함하는 `Sub`가 시작되고 보안 예외가 생성되기 전에 `Try...Catch`에서 이를 catch할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Try...Catch...Finally` 문의 구조를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## 예제  
 다음 예제에서는 `CreateException` 메서드가 `NullReferenceException`을 throw합니다.  예외를 발생시키는 코드가 `Try` 블록에 없습니다.  따라서 `CreateException` 메서드는 예외를 처리하지 않습니다.  `CreateException` 메서드에 대한 호출이 `Try` 블록에 있으므로 `RunSample` 메서드는 예외를 처리하지 않습니다.  
  
 예제에는 몇 가지 예외 형식에 대한 `Catch` 문이 가장 구체적인 형식부터 가장 일반적인 형식의 순서로 포함되어 있습니다.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## 예제  
 다음 예제에서는 조건식에서 필터링하기 위해 `Catch When`을 사용하는 방법을 보여 줍니다.  조건식이 `True`인 경우 `Catch` 블록의 코드가 실행됩니다.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## 예제  
 다음 예제에는 `Try` 블록에 포함된 `Try…Catch` 문이 있습니다.  내부의 `Catch` 블록은 그 `InnerException` 속성이 원래 예외로 설정된 예외를 throw합니다.  외부 `Catch` 블록은 자체 예외와 내부 예외를 보고합니다.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## 예제  
 다음 예제에서는 예외를 처리에 대 한 비동기 메서드를 보여 줍니다.  비동기 작업에 적용 되는 예외를 catch 하는 `Await` 식이 `Try` 호출자 및 예외 블록에서 메일이 `Catch` 블록.  
  
 주석 표시는 `Throw New Exception` 줄 예외 처리를 보여 주는 예제입니다.  예외에 `Catch` 차단 작업의 `IsFaulted` 속성을 설정 `True`, 및 작업의 `Exception.InnerException` 속성을 설정 하는 예외.  
  
 주석 표시는 `Throw New OperationCancelledException` 줄 비동기 프로세스를 취소 한 경우를 보여 줍니다.  예외에 `Catch` 블록과 작업 `IsCanceled` 속성을 설정 `True`.  그러나이 예제에 적용 되지 않는 어떤 조건 `IsFaulted` 설정 `True` 및 `IsCanceled` 설정 `False`.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## 예제  
 다음 예제에서는 예외 처리를 여러 작업에 여러 예외 발생할 수 있습니다 위치를 보여 줍니다.  `Try` 블록이 있습니다는 `Await` 작업에 대 한 식을 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 반환 합니다.  세 하에서 작업 하는 경우 작업이 완료 된 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 적용 완료 됩니다.  
  
 각각의 세 가지 작업 중에 예외가 발생합니다.  `Catch` 블록 반복에서 발견 되는 예외를 통해의 `Exception.InnerExceptions` 작업의 속성은 `Task.WhenAll` 반환.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception>   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [코드 조각을 사용하는 방법에 대한 유용한 정보](/visual-studio/ide/best-practices-for-using-code-snippets)   
 [예외 처리](../Topic/Exception%20Handling%20\(Task%20Parallel%20Library\).md)   
 [Throw Statement](../../../visual-basic/language-reference/statements/throw-statement.md)