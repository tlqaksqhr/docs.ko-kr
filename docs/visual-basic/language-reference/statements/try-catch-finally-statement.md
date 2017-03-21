---
title: "시도 중... Catch... Finally 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
dev_langs:
- VB
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement, Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement
- When keyword
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 379359e3a338746ccd440dbe1ad58c483e562dbe
ms.lasthandoff: 03/13/2017

---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally 문(Visual Basic)
코드 실행 하면서 코드의 블록에서 발생할 수 있는 일부 또는 모든 가능한 오류를 처리 하는 방법을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`tryStatements`|선택적 요소. 오류가 발생할 수 있는 문을 지정 합니다. 복합 문일 수 있습니다.|  
|`Catch`|선택적 요소. 여러 `Catch` 블록을 사용할 수 있습니다. 예외를 처리할 때 발생 하는 경우는 `Try` 각 차단 `Catch` 문을와 예외를 처리 하는지 여부를 확인 하려면 텍스트 순서 대로 검사 `exception` throw 된 예외를 나타내는 합니다.|  
|`exception`|선택적 요소. 임의의 변수 이름입니다. `exception`의 초기 값은 throw된 오류 값입니다. 사용한 `Catch` 발생 한 예외를 지정 합니다. 생략 한 경우는 `Catch` 문은 예외를 catch 합니다.|  
|`type`|선택적 요소. 필터 클래스의 형식을 지정합니다. 하는 경우의 값 `exception` 로 지정 된 형식의 `type` 또는 파생 형식의 식별자가 예외 개체에 바인딩됩니다.|  
|`When`|선택적 요소. A `Catch` 문을 `When` 절 예외를 catch 합니다. 경우에만 `expression` 계산 `True`합니다. A `When` 절에는 예외의 유형을 확인 한 후에 적용 됩니다 및 `expression` 예외를 나타내는 식별자를 참조할 수 있습니다.|  
|`expression`|선택적 요소. 암시적으로 변환할 수 있어야 `Boolean`합니다. 일반 필터를 설명 하는 모든 식입니다. 일반적으로 오류 번호로 필터링 하는 데 사용 합니다. 사용한 `When` 키워드 오류가 발생 하는 상황을 지정 합니다.|  
|`catchStatements`|선택적 요소. 연결 된에서 발생 하는 오류를 처리 하는 문 `Try` 블록입니다. 복합 문일 수 있습니다.|  
|`Exit Try`|선택적 요소. 밖으로 중단 하는 키워드는 `Try...Catch...Finally` 구조입니다. 실행을 다시 시작 바로 다음 코드는 `End Try` 문입니다. `Finally` 문을 계속 실행 됩니다. 에 사용할 수 없습니다 `Finally` 블록입니다.|  
|`Finally`|선택적 요소. A `Finally` 블록은 실행의 모든 부분을 벗어나면 항상 실행은 `Try...Catch` 문입니다.|  
|`finallyStatements`|선택적 요소. 다른 모든 오류 처리를 수행한 후 실행 되는 문입니다.|  
|`End Try`|종료는 `Try...Catch...Finally` 구조입니다.|  
  
## <a name="remarks"></a>주의  
 특정 예외를 코드의 특정 섹션 중에 발생할 수 있는지를 려 할 경우에 코드를 입력 한 `Try` 블록과 사용 하는 `Catch` 제어 유지 하 고 발생 하는 경우는 예외를 처리 하기 위해 블록입니다.  
  
 A `Try…Catch` 문을 이루어져는 `Try` 블록 뒤에 하나 이상의 `Catch` 다양 한 예외에 대 한 처리기를 지정 하는 절. 예외가 throw 되 면는 `Try` 블록 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 찾습니다는 `Catch` 예외를 처리 하는 문입니다. 일치 하는 경우 `Catch` 문을 발견 되지 않으면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 호출 스택에서 등 현재 메서드를 호출한 메서드를 검사 합니다. 없으면 `Catch` 블록을 찾지 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 처리 되지 않은 예외 메시지가 사용자에 게 표시 하 고 프로그램의 실행을 중지 합니다.  
  
 하나 이상 사용할 수 있습니다 `Catch` 문에서 `Try…Catch` 문입니다. 이 순서는 `Catch` 절은 순서 대로 검사 되므로 중요 합니다. 더 구체적인 예외를 덜 구체적인 예외보다 먼저 catch합니다.  
  
 다음 `Catch` 문 가장 일반적인 조건과 모든 catch 할 <xref:System.Exception>클래스</xref:System.Exception> 에서 파생 되는 예외 마지막으로 이러한 종류의 일반적으로 사용 해야 `Catch` 블록은 `Try...Catch...Finally` 예상 된 특정 한 예외를 catch 한 후 구조입니다. 제어 흐름 도달할 수 없다고는 `Catch` 이러한 차이 중 하나를 따르는 블록입니다.  
  
-   `type` 는 `Exception`, 예:`Catch ex As Exception`  
  
-   문이 아무런 `exception` 예를 들어 변수:`Catch`  
  
 때는 `Try…Catch…Finally` 다른 문이 중첩 되 `Try` 블록 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 먼저 각 검사 `Catch` 문의 가장 안쪽에서 `Try` 블록입니다. 일치 하는 경우 `Catch` 문을 발견 되 면 검색 진행는 `Catch` 외부 문을 `Try…Catch…Finally` 블록입니다.  
  
 지역 변수는 `Try` 블록에서 사용할 수 없는 `Catch` 별도 블록 있기 때문에 차단 합니다. 둘 이상의 블록에서 변수를 사용 하려는 경우 외부에서 변수 선언에서 `Try...Catch...Finally` 구조입니다.  
  
> [!TIP]
>  `Try…Catch…Finally` 문을 IntelliSense 코드 조각으로 제공 됩니다. 코드 조각 관리자에서 확장 **코드 패턴-경우, 각각에 대해 Try Catch 속성 등**, 차례로 **오류 처리 (예외)**합니다. 자세한 내용은 [코드 조각](https://docs.microsoft.com/visualstudio/ide/code-snippets)을 참조하세요.  
  
## <a name="finally-block"></a>Finally 블록  
 종료 하기 전에 실행 해야 하는 하나 이상의 문이 있으면는 `Try` 구조를 사용 하 여 한 `Finally` 블록입니다. 제어 전달는 `Finally` 부재 중 전달 하기 직전 차단는 `Try…Catch` 구조입니다. 내에서 예외가 발생 하는 경우에 마찬가지입니다는 `Try` 구조입니다.  
  
 A `Finally` 블록은 예외가 있을 경우에 실행 해야 하는 모든 코드를 실행 하는 데 유용 합니다. 제어가 전달 됩니다는 `Finally` 방식과 관계 없이 블록 `Try...Catch` 종료를 차단 합니다.  
  
 코드는 `Finally` 블록이 실행 코드에서 발견 한 경우에는 `Return` 문에서 `Try` 또는 `Catch` 블록입니다. 제어를 전달 하지 않는 한 `Try` 또는 `Catch` 블록에서 해당 `Finally` 다음과 같은 경우에 차단:  
  
-   [End 문](../../../visual-basic/language-reference/statements/end-statement.md) 에서 발견 되는 `Try` 또는 `Catch` 블록입니다.  
  
-   A <xref:System.StackOverflowException>에서 throw 되는 `Try` 또는 `Catch` 블록.</xref:System.StackOverflowException>  
  
 유효 하지 않은 명시적으로 실행을 전송할 수에 `Finally` 블록입니다. 실행을 전송는 `Finally` 블록이 예외 사항을 제외 하 고 잘못 되었습니다.  
  
 경우는 `Try` 문을 하나 이상 포함 하지 않는 `Catch` 블록을 포함 해야는 `Finally` 블록입니다.  
  
> [!TIP]
>  특정 예외를 catch 하지 않은 경우는 `Using` 문 처럼 동작을 `Try…Finally` 블록과 블록을 종료 하는 방법에 관계 없이 리소스를 삭제할 수 있습니다. 처리 되지 않은 예외가 있는 경우에 마찬가지입니다. 자세한 내용은 참조 [문을 사용 하 여](../../../visual-basic/language-reference/statements/using-statement.md)합니다.  
  
## <a name="exception-argument"></a>예외 인수입니다.  
 `Catch` 블록 `exception` 인수는의 인스턴스는 <xref:System.Exception>클래스 또는 클래스에서 파생 되는 `Exception` 클래스</xref:System.Exception> `Exception` 에서 발생 한 오류에 해당 하는 클래스 인스턴스는 `Try` 블록입니다.  
  
 속성은 `Exception` 원인과 예외 위치를 식별 하는 도움말 개체입니다. 예를 들어는 <xref:System.Exception.StackTrace%2A>속성 코드에 오류가 발생 하는 위치를 찾을 수 있도록 하는 예외를 초래한 호출된 메서드를 보여 줍니다.</xref:System.Exception.StackTrace%2A> <xref:System.Exception.Message%2A>예외를 설명 하는 메시지를 반환 합니다.</xref:System.Exception.Message%2A> <xref:System.Exception.HelpLink%2A>연결된 된 도움말 파일에 대 한 링크를 반환합니다.</xref:System.Exception.HelpLink%2A> <xref:System.Exception.InnerException%2A>반환 된 `Exception` 현재 예외를 발생 시킨 개체를 반환 `Nothing` 원본 있으면 `Exception`합니다.</xref:System.Exception.InnerException%2A>  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Try 사용 시 고려 사항 중... Catch 문  
 사용 하는 `Try…Catch` 프로그램 비정상적 이거나 예기치 않은 이벤트의 발생을 신호에 문. 이 문제의 원인은 다음과 같습니다.  
  
-   추가 오버 헤드를를 만들고 예외를 방지 하려면 사전 검사 보다 속도가 떨어지므로 런타임 시 예외를 catch 합니다.  
  
-   경우에 `Catch` 블록을 올바르게 처리 하지 않으면, 예외 사용자에 게 제대로 보고 하지 않을 수 있습니다.  
  
-   예외 처리를 사용 하면 프로그램이 더 복잡 한 합니다.  
  
 항상 원하지 않는 한 `Try…Catch` 발생할 가능성이 있는 조건을 확인 하는 문이 있습니다. 다음 예제에서는 파일을 열기 전에 있는지 여부를 확인 합니다. Throw 된 예외를 catch 하기 위한 필요성을 줄이고이 <xref:System.IO.File.OpenText%2A>메서드.</xref:System.IO.File.OpenText%2A>  
  
 [!code-vb[VbVbalrStatements #&94;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 해당 코드를 확인 `Catch` 블록 스레드로부터 안전한 로깅 또는 적절 한 메시지 통해 사용자에 게 예외를 올바르게 보고할 수 있습니다. 그렇지 않으면 예외를 알 수 없는 남아 있을 수 있습니다.  
  
## <a name="async-methods"></a>비동기 메서드  
 사용 하 여 메서드를 표시 하는 경우는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 사용할 수 있습니다 한정자는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 메서드에서. 사용 하 여 문을 `Await` 연산자 대기 중인된 작업이 완료 될 때까지 메서드 실행을 일시 중단 합니다. 작업은 진행 중인 작업을 나타냅니다. 때 연결 된 작업은 `Await` 연산자가 완료 되 면 동일한 메서드에서 실행이 다시 시작 합니다. 자세한 내용은 참조 [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)합니다.  
  
 비동기 메서드에서 반환 된 작업은 처리 되지 않은 예외로 인해 완료 되었음을 나타내는 오류 상태로 종료 될 수 있습니다. 그 결과 취소 된 상태에서 작업을 종료할 수 있습니다는 `OperationCanceledException` await 식에서 throw 되 고 있습니다. 어떤 유형의 예외를 catch 하는 경우, 배치는 `Await` 식에서 해당 작업을 연관 된는 `Try` 블록을에서 예외를 catch는 `Catch` 블록입니다. 예제는이 항목의 뒷부분에 제공 됩니다.  
  
 작업 여러 예외가 그 안에서 오류가 발생 하는 일을 담당 되었기 때문에 오류가 발생 한 상태가 될 수 있습니다. 예를 들어, 작업 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 에 대 한 호출의 결과 수 있습니다. 이러한 작업을 기다리는 경우 예외가 발생 했습니다 예외 중 하나만 이며 예외는 발생을 예측할 수 없습니다. 예제는이 항목의 뒷부분에 제공 됩니다.  
  
 `Await` 내 식이 될 수 없습니다는 `Catch` 블록 또는 `Finally` 블록입니다.  
  
## <a name="iterators"></a>반복기  
 반복기 함수 또는 `Get` 접근자 컬렉션 사용자 지정 반복을 수행 합니다. 반복기를 사용 하 여는 [생성](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 한 번에 컬렉션의 각 요소를 반환 합니다. 반복기 함수를 사용 하 여 호출을 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
 A `Yield` 내부 문을 수는 `Try` 블록입니다. A `Try` 포함 된 블록은 `Yield` 문의 `Catch` 을 차단 하 고 있을 수 있습니다는 `Finally` 블록입니다. "Visual Basic에서 시도 블록" 섹션을 참조 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) 대 한 예제입니다.  
  
 A `Yield` 문 내 야는 `Catch` 블록 또는 `Finally` 블록입니다.  
  
 하는 경우는 `For Each` 예외를 throw 하는 본문 (반복기 함수) 외부는 `Catch` 블록 반복기 함수에이 실행 되지 않으면 하지만 `Finally` 반복기 함수 블록이 실행 됩니다. A `Catch` 반복기 함수 내의 블록 반복기 함수 내 발생 하는 예외에만 catch 합니다.  
  
## <a name="partial-trust-situations"></a>부분 신뢰 상황  
 네트워크 공유에서 호스팅되는 응용 프로그램과 같은 부분 신뢰 상황에서 `Try...Catch...Finally` 호출을 포함 하는 메서드를 호출 하기 전에 발생 하는 보안 예외를 catch 하지 않습니다. 다음 예제에서는 할 때 서버 공유 및 실행에 여기에서 오류가 발생 하는 "System.Security.SecurityException: 실패 한 요청입니다." 보안 예외에 대 한 자세한 내용은 <xref:System.Security.SecurityException>클래스</xref:System.Security.SecurityException> 를 참조 하십시오.  
  
 [!code-vb[VbVbalrStatements #&85;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 이러한 부분 신뢰 상황에서 입력할 필요가 `Process.Start` 문을 별도의 `Sub`합니다. 에 대 한 초기 호출은 `Sub` 실패 합니다. 이 통해 `Try...Catch` 를 하기 전에 catch는 `Sub` 포함 하는 `Process.Start` 시작 되 고 보안 예외를 생성 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 구조는 `Try...Catch...Finally` 문입니다.  
  
 [!code-vb[VbVbalrStatements #&86;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CreateException` 메서드가 throw 한 `NullReferenceException`합니다. 예외를 생성 하는 코드에 없는 `Try` 블록입니다. 따라서는 `CreateException` 메서드는 예외를 처리 하지 않습니다. `RunSample` 때문에 메서드는 예외를 처리에 대 한 호출의 `CreateException` 방법은에 `Try` 블록입니다.  
  
 이 예제에서는 포함 `Catch` 에서 정렬 된 여러 유형의 예외에 대 한 문을 가장 일반적인 가장 구체적인 합니다.  
  
 [!code-vb[VbVbalrStatements #&91;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>예제  
 다음 예제를 사용 하는 방법을 보여 줍니다는 `Catch When` 문을 조건 식에 필터를 적용 합니다. 조건 식에 계산 되는 경우 `True`의 코드는 `Catch` 블록이 실행 됩니다.  
  
 [!code-vb[VbVbalrStatements #&92;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에는 `Try…Catch` 에 포함 된 문에 `Try` 블록입니다. 내부 `Catch` 있는 예외를 throw 하는 블록의 `InnerException` 속성이 원래 예외로 설정 합니다. 외부 `Catch` 블록 자체 예외와 내부 예외를 보고 합니다.  
  
 [!code-vb[VbVbalrStatements #&93;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 메서드에 대한 예외 처리를 보여 줍니다. 비동기 작업에 적용 되는 예외를 catch 하는 `Await` 식이 `Try` 호출자에 게, 그리고 예외 블록에 걸린는 `Catch` 블록입니다.  
  
 예제에서 `Throw New Exception` 줄의 주석 처리를 제거하여 예외 처리를 보여 줍니다. 예외에 걸린는 `Catch` 블록을 작업의 `IsFaulted` 속성이 `True`, 및 작업의 `Exception.InnerException` 예외 속성입니다.  
  
 주석 처리를 제거는 `Throw New OperationCancelledException` 줄에는 비동기 프로세스를 취소 하면 결과 보여 줍니다. 예외에 걸린는 `Catch` 블록과 작업의 `IsCanceled` 속성이 `True`합니다. 그러나이 예에는 적용 되지 않는 몇 가지 상황에서 `IsFaulted` 로 설정 된 `True` 및 `IsCanceled` 로 설정 된 `False`합니다.  
  
 [!code-vb[csAsyncExceptions&#1;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 작업에서 여러 예외가 발생할 수 있는 경우 예외 처리를 보여 줍니다. `Try` 블록에는 `Await` 작업에 대 한 식을 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>반환 됩니다.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 세 가지 작업을 하는 경우 작업이 완료 되 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>적용 완료.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>  
  
 세 작업에서 각각 예외가 발생합니다. `Catch` 블록에 있는 예외를 통해 반복 하는 `Exception.InnerExceptions` 는 작업의 속성 하 `Task.WhenAll` 반환 합니다.  
  
 [!code-vb[csAsyncExceptions&#3;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Information.Err%2A></xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception></xref:System.Exception>   
 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [코드 조각 사용 모범 사례](https://docs.microsoft.com/visualstudio/ide/best-practices-for-using-code-snippets)   
 [예외 처리](https://msdn.microsoft.com/library/dd997415)   
 [Throw 문](../../../visual-basic/language-reference/statements/throw-statement.md)
