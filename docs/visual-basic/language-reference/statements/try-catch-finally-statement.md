---
title: Try...Catch...Finally 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.openlocfilehash: 5e7037d1f89d56d1c65fe94e7c5fbafc7b3c40f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally 문(Visual Basic)
코드 실행 하는 동안 코드 블록에서 발생할 수 있는 일부 또는 모든 가능한 오류를 처리 하는 방법을 제공 합니다.  
  
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
|`tryStatements`|선택 사항입니다. 문에 오류가 발생할 수 있습니다. 복합 문일 수 있습니다.|  
|`Catch`|선택 사항입니다. 여러 `Catch` 블록을 사용할 수 있습니다. 예외를 처리할 때 발생 하는 경우는 `Try` 각각 차단 `Catch` 문을와 예외를 처리 하는지 여부를 확인 하려면 텍스트 순서 대로 검사 `exception` throw 된 예외를 나타내는입니다.|  
|`exception`|선택 사항입니다. 임의의 변수 이름입니다. `exception`의 초기 값은 throw된 오류 값입니다. 함께 사용할 `Catch` 발생 한 예외를 지정 합니다. 생략 하는 경우는 `Catch` 문은 예외를 catch 합니다.|  
|`type`|선택 사항입니다. 클래스 필터의 유형을 지정합니다. 하는 경우의 값 `exception` 로 지정 된 형식의 `type` 또는 파생 형식인 식별자가 예외 개체에 바인딩됩니다.|  
|`When`|선택 사항입니다. A `Catch` 문을 `When` 절에서 예외를 catch 경우에만 `expression` 계산 `True`합니다. A `When` 절은 예외의 유형을 확인 한 후에 적용 되 고 `expression` 예외를 나타내는 식별자를 참조할 수 있습니다.|  
|`expression`|선택 사항입니다. 암시적으로 변환할 수 있어야 `Boolean`합니다. 일반 필터를 설명 하는 모든 식입니다. 일반적으로 오류 숫자 기준으로 필터링 하는 데 사용 합니다. 함께 사용할 `When` 키워드 오류가 발생 하는 상황을 지정 합니다.|  
|`catchStatements`|선택 사항입니다. 연결 된에서 발생 하는 오류를 처리 하는 문 `Try` 블록입니다. 복합 문일 수 있습니다.|  
|`Exit Try`|선택 사항입니다. 받았거나 키워드는 `Try...Catch...Finally` 구조입니다. 실행을 다시 시작 바로 다음 코드는 `End Try` 문. `Finally` 문이 실행 계속 됩니다. 에 사용할 수 없습니다 `Finally` 블록입니다.|  
|`Finally`|선택 사항입니다. A `Finally` 실행의 모든 부분을 벗어나면 블록은 항상 실행는 `Try...Catch` 문.|  
|`finallyStatements`|선택 사항입니다. 모든 다른 오류 처리가 발생 한 후 실행 되는 문입니다.|  
|`End Try`|종료는 `Try...Catch...Finally` 구조입니다.|  
  
## <a name="remarks"></a>설명  
 특정 예외를 코드의 특정 섹션 중 발생할 수 예상 되는 경우에 코드를 입력 한 `Try` 차단 하 고 사용 하 여는 `Catch` 제어를 유지 하 고 발생 하는 경우 예외를 처리 하는 블록입니다.  
  
 A `Try…Catch` 문을 이루어져는 `Try` 블록 뒤에 하나 이상의 `Catch` 다양 한 예외에 대 한 처리기를 지정 하는 절. 예외가 throw 되는 경우는 `Try` 차단, Visual Basic을 찾습니다는 `Catch` 예외를 처리 하는 문입니다. 일치 하는 경우 `Catch` 문을 찾을 수 없습니다, Visual Basic에서 호출 스택까지 등 현재 메서드를 호출한 메서드를 검사 합니다. 되지 않은 경우 `Catch` 블록이 발견, Visual Basic 처리 되지 않은 예외 메시지가 사용자에 게 표시 하 고 프로그램의 실행을 중지 합니다.  
  
 여러 개 사용할 수 있습니다 `Catch` 의 문에서 `Try…Catch` 문. 이 순서는 `Catch` 절은 순서 대로 검사 되므로 중요 합니다. 더 구체적인 예외를 덜 구체적인 예외보다 먼저 catch합니다.  
  
 다음 `Catch` 문 조건은 가장 일반적인 것 이며 하며 모든 catch에서 파생 되는 예외는 <xref:System.Exception> 클래스입니다. 마지막으로 이러한 종류의 일반적으로 사용 해야 `Catch` 의 블록은 `Try...Catch...Finally` 예상 된 특정 한 예외를 catch 한 후 구조입니다. 제어 흐름 도달할 수 없습니다는 `Catch` 블록 뒤에 오는 이러한 변형 중 하나입니다.  
  
-   `type` 은 `Exception`, 예: `Catch ex As Exception`  
  
-   문이 아무런 `exception` 변수 예: `Catch`  
  
 경우는 `Try…Catch…Finally` 다른 문이 중첩 되 `Try` 블록, Visual Basic에 각 항목을 먼저 검사 `Catch` 가장 안쪽의 문에서 `Try` 블록입니다. 일치 하는 경우 `Catch` 검색 진행, 문이 발견 되는 `Catch` 문 외부 `Try…Catch…Finally` 블록.  
  
 지역 변수는 `Try` 블록에서 사용할 수 없는 `Catch` 별도 블록 되기 때문에 차단 합니다. 둘 이상의 블록에서 변수를 사용 하려는 경우 외부 변수 선언에서 `Try...Catch...Finally` 구조입니다.  
  
> [!TIP]
>  `Try…Catch…Finally` IntelliSense 코드 조각으로 취급 합니다. 코드 조각 관리자에서 확장 **코드 패턴-If, 각 항목에 대해 Try Catch, 속성, 등**, 차례로 **오류 처리 (예외)** 합니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.  
  
## <a name="finally-block"></a>Finally 블록  
 종료 하기 전에 실행 해야 하는 하나 이상의 문이 있는 경우는 `Try` 구조을 사용 하 여 한 `Finally` 블록입니다. 컨트롤을 전달는 `Finally` 블록 밖으로 전달 하기 바로 전에 `Try…Catch` 구조입니다. 내에서 예외가 발생 하는 경우에 마찬가지입니다는 `Try` 구조입니다.  
  
 A `Finally` 블록은 예외 경우에 실행 해야 하는 코드를 실행 한 경우에 유용 합니다. 컨트롤에 전달 되는 `Finally` 방식과 관계 없이 블록 `Try...Catch` 종료 되거나 차단 합니다.  
  
 코드는 `Finally` 코드에서 발견 하는 경우에 블록이 실행은 `Return` 의 문에서 `Try` 또는 `Catch` 블록입니다. 컨트롤에서 전달 하지 않습니다는 `Try` 또는 `Catch` 블록에서 해당 `Finally` 다음과 같은 경우에 차단 합니다.  
  
-   [End 문](../../../visual-basic/language-reference/statements/end-statement.md) 에서 발견 되는 `Try` 또는 `Catch` 블록입니다.  
  
-   A <xref:System.StackOverflowException> 에서 throw 되는 `Try` 또는 `Catch` 블록입니다.  
  
 유효 하지 않은에 실행을 명시적으로 전송 하는 `Finally` 블록입니다. 실행을 전송는 `Finally` 블록이 예외를 통해 제외 하 고 잘못 되었습니다.  
  
 경우는 `Try` 문을 하나 이상 포함 하지 않습니다 `Catch` 블록을 포함 해야 합니다는 `Finally` 블록입니다.  
  
> [!TIP]
>  특정 예외를 catch 하지 않은 경우는 `Using` 문 처럼 작동 하며는 `Try…Finally` 블록과 블록을 종료 하는 방법에 상관 없이 리소스를 삭제할 수 있습니다. 처리 되지 않은 예외가 된 경우에 마찬가지입니다. 자세한 내용은 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.  
  
## <a name="exception-argument"></a>예외 인수  
 `Catch` 블록 `exception` 인수가의 인스턴스는 <xref:System.Exception> 클래스 또는 클래스에서 파생 되는 `Exception` 클래스입니다. `Exception` 에서 발생 한 오류에 해당 하는 클래스 인스턴스는 `Try` 블록입니다.  
  
 속성은 `Exception` 원인과 예외의 위치를 식별 하는 도움말 개체입니다. 예를 들어는 <xref:System.Exception.StackTrace%2A> 속성 코드에서 오류가 발생 한 위치를 찾을 수 있도록 하는 예외를 발생 시킨 호출된 메서드를 보여 줍니다. <xref:System.Exception.Message%2A> 예외를 설명 하는 메시지를 반환 합니다. <xref:System.Exception.HelpLink%2A> 연결된 된 도움말 파일에 대 한 링크를 반환합니다. <xref:System.Exception.InnerException%2A> 반환 된 `Exception` 현재 예외를 발생 시킨 개체를 반환 `Nothing` 원본 이면 `Exception`합니다.  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Try 사용 시 고려 사항 중... Catch 문  
 사용 하 여 한 `Try…Catch` 을 비정상적인 또는 예기치 않은 프로그램 이벤트의 발생을 알리기 위해서만 문. 이 대 한 이유는 다음과 같습니다.  
  
-   런타임 시 예외를 catch 추가 오버 헤드가 발생 하며 예외를 방지 하기 위해 사전 검사 보다 느려질 수  
  
-   경우는 `Catch` 블록 올바르게 처리 하지 않으면, 사용자에 게 예외 올바르게 보고 하지 수도 있습니다.  
  
-   예외 처리를 사용 하면 프로그램이 더 복잡 한 합니다.  
  
 항상 필요 하지 않습니다는 `Try…Catch` 발생할 가능성이 있는 조건을 확인 하는 문입니다. 다음 예제에서는 파일을 열기 전에 있는지 여부를 확인 합니다. 발생 한 예외를 catch 하기 위한 작업의 필요성을 줄이고이 <xref:System.IO.File.OpenText%2A> 메서드.  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 해당 코드를 확인 `Catch` 적절 한 메시지 또는 스레드로부터 안전한 로깅을 통해 블록, 사용자에 게 예외를 제대로 보고할 수 있습니다. 그렇지 않으면 예외를 알 수 없는 남아 있을 수 있습니다.  
  
## <a name="async-methods"></a>비동기 메서드  
 메서드를 표시 하는 경우는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 사용할 수 있습니다 한정자는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 메서드에서 합니다. 사용 하 여 문을 `Await` 연산자는 대기 중인된 작업이 완료 될 때까지 메서드의 실행을 일시 중단 합니다. 작업은 진행 중인 작업을 나타냅니다. 때 연관 된 태스크는 `Await` 연산자가 완료 되 면 동일한 메서드에서 실행이 다시 시작 합니다. 자세한 내용은 참조 [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)합니다.  
  
 비동기 메서드에서 반환 된 작업 처리 되지 않은 예외로 인해 완료 되었음을 나타내는 오류 상태로 종료 될 수 있습니다. 작업으로 인해 취소 된 상태에도 종료 될 수 있습니다는 `OperationCanceledException` await 식에서 throw 되 고 있습니다. 어떤 유형의 예외를 catch 하려면 배치는 `Await` 식에서 해당 작업을 연관 된 한 `Try` 블록과에서 예외를 catch는 `Catch` 블록입니다. 이 항목의 뒷부분에 나오는 예가 제공 됩니다.  
  
 작업은 해당 오류에 대 한 여러 예외가 있었던 있으므로 오류 상태에 수 있습니다. 예를 들어 작업은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 호출의 결과일 수 있습니다. 이러한 작업을 기다릴 때 예외가 예외 중 하나만 이며 예외를 포착 합니다 예측할 수 없습니다. 이 항목의 뒷부분에 나오는 예가 제공 됩니다.  
  
 `Await` 식 내에 있을 수 없습니다는 `Catch` 블록 또는 `Finally` 블록입니다.  
  
## <a name="iterators"></a>반복기  
 반복기 함수 또는 `Get` 접근자 컬렉션 사용자 지정 반복을 수행 합니다. 반복기를 사용 하 여 한 [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 한 번에 하나씩 컬렉션의 각 요소를 반환 합니다. 반복기 함수를 사용 하 여 호출 된 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
 A `Yield` 문 내에 있을 수는 `Try` 블록입니다. A `Try` 포함 된 블록은 `Yield` 문의 `Catch` 을 차단 하 고 있을 수 있습니다는 `Finally` 블록입니다. "Visual Basic에서 시도 블록" 섹션을 참조 [반복기](../../programming-guide/concepts/iterators.md) 예에 대 한 합니다.  
  
 A `Yield` 문 내에 있을 수 없습니다는 `Catch` 블록 또는 `Finally` 블록입니다.  
  
 경우는 `For Each` 본문 (반복기 함수) 외부 예외를 throw 하지는 `Catch` 블록에 반복기 함수가 실행 되지 않으며 하지만 `Finally` 반복기 함수에는 블록이 실행 됩니다. A `Catch` 반복기 함수 내의 블록 반복기 함수 내에서 발생 하는 예외만을 catch 합니다.  
  
## <a name="partial-trust-situations"></a>부분 신뢰 상태  
 네트워크 공유에서 호스팅되는 응용 프로그램 같은 부분 신뢰 상황에서 `Try...Catch...Finally` 호출을 포함 하는 메서드를 호출 하기 전에 발생 하는 보안 예외를 catch 하지 않습니다. 다음 예제에서는 할 때 서버 공유 및 실행에 여기에서 오류를 생성 합니다. "System.Security.SecurityException: 실패 한 요청입니다." 보안 예외에 대 한 자세한 내용은 참조는 <xref:System.Security.SecurityException> 클래스입니다.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 이러한 부분 신뢰 상황에서 입력할 필요가 `Process.Start` 문을 별도의 `Sub`합니다. 에 대 한 초기 호출에서 `Sub` 실패 합니다. 이 통해 `Try...Catch` 를 catch 하기 전에 `Sub` 포함 된 `Process.Start` 시작 되 고 보안 예외가 발생 했습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 구조는 `Try...Catch...Finally` 문.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CreateException` 메서드가 throw 한 `NullReferenceException`합니다. 예외를 생성 하는 코드에 속하지 않는 한 `Try` 블록입니다. 따라서는 `CreateException` 메서드 예외를 처리 하지 않습니다. `RunSample` 메서드 예외를 처리할지 않습니다에 대 한 호출에서 `CreateException` 방법은에 `Try` 블록입니다.  
  
 예제에 포함 되어 `Catch` 에서 정렬 된 여러 유형의 예외에 대 한 문을 가장 일반적인 가장 구체적인 합니다.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `Catch When` 문을 조건 식에 필터를 적용 합니다. 조건부 식이 `True`의 코드는 `Catch` 블록이 실행 됩니다.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에는 `Try…Catch` 에 포함 된 문에 `Try` 블록입니다. 내부 `Catch` 있는 예외를 throw 하는 블록의 `InnerException` 속성이 원래 예외를 설정 합니다. 외부 `Catch` 블록 자체 예외 및 내부 예외를 보고 합니다.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 메서드에 대한 예외 처리를 보여 줍니다. 비동기 작업에 적용 되는 예외를 catch 하는 `Await` 해당 식을 `Try` 호출자 및 예외 블록에 들어갈는 `Catch` 블록입니다.  
  
 예제에서 `Throw New Exception` 줄의 주석 처리를 제거하여 예외 처리를 보여 줍니다. 예외에 들어갈는 `Catch` 차단 작업의 `IsFaulted` 속성이로 설정 되어 `True`, 및 작업의 `Exception.InnerException` 예외에 속성이 설정 되어 있습니다.  
  
 `Throw New OperationCancelledException` 줄의 주석 처리를 제거하여 비동기 프로세스를 취소할 수 있을 때 발생하는 동작을 보여 줍니다. 예외에 들어갈는 `Catch` 블록과 작업의 `IsCanceled` 속성이 `True`합니다. 그러나이 예제에 적용 되지 않는 몇몇 조건 `IsFaulted` 로 설정 된 `True` 및 `IsCanceled` 로 설정 된 `False`합니다.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 작업에서 여러 예외가 발생할 수 있는 경우 예외 처리를 보여 줍니다. `Try` 블록에는 `Await` 작업에 대 한 식을 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 반환 합니다. 세 가지 작업을 하는 경우 작업이 완료 될 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 적용 조건이 완료 합니다.  
  
 세 작업에서 각각 예외가 발생합니다. `Catch` 블록에 있는 예외를 반복는 `Exception.InnerExceptions` 태스크의 속성은 `Task.WhenAll` 반환 합니다.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:System.Exception>  
 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [코드 조각 사용에 대한 모범 사례](/visualstudio/ide/best-practices-for-using-code-snippets)  
 [예외 처리](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)  
 [Throw 문](../../../visual-basic/language-reference/statements/throw-statement.md)
