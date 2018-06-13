---
title: Using 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 725eeb42dc5462022ac1a021c537d701929398ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604967"
---
# <a name="using-statement-visual-basic"></a>Using 문(Visual Basic)
시작을 선언는 `Using` 차단 하 고 블록이 제어 되는 시스템 리소스를 선택적으로 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`resourcelist`|지정 하지 않은 경우 필요한 `resourceexpression`합니다. 하나 이상의 시스템 리소스가이 목록 `Using` 쉼표로 구분 하 여 컨트롤을 차단 합니다.|  
|`resourceexpression`|지정 하지 않은 경우 필요한 `resourcelist`합니다. 참조 변수 또는 시스템 리소스에 대 한이 제어를 참조 하는 식을 `Using` 블록입니다.|  
|`statements`|선택 사항입니다. 문 블록을 하는 `Using` 블록이 실행 됩니다.|  
|`End Using`|필수. 정의 종료는 `Using` 블록 및 제어 하는 모든 리소스를 삭제 합니다.|  
  
 각 리소스에는 `resourcelist` 부분은 다음과 같은 구문과 요소가 있습니다.  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -또는-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist 부분  
  
|용어|정의|  
|---|---|  
|`resourcename`|필수. 참조 변수를 시스템 리소스를 참조 하는 `Using` 컨트롤을 차단 합니다.|  
|`New`|필요한 경우에는 `Using` 문이 리소스를 가져오는 합니다. 이미 리소스를 확보 하는 경우에 두 번째 대체 구문을 사용 합니다.|  
|`resourcetype`|필수. 리소스의 클래스입니다. 클래스를 구현 해야 합니다는 <xref:System.IDisposable> 인터페이스입니다.|  
|`arglist`|선택 사항입니다. 인스턴스를 만드는 생성자에 전달 하는 인수 목록 `resourcetype`합니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.|  
|`resourceexpression`|필수. 변수 또는 식의 요구 사항을 만족 하는 시스템 리소스를 가리키는 `resourcetype`합니다. 컨트롤을 전달 하기 전에 리소스를 획득 해야 두 번째 대체 구문을 사용 하는 경우는 `Using` 문.|  
  
## <a name="remarks"></a>설명  
 경우에 따라 코드는 열려 있는 파일 핸들, COM 래퍼 SQL 연결 등의 관리 되지 않는 리소스를 필요합니다. A `Using` 블록 코드는 작업을 마칠 때 하나 이상의 이러한 리소스의 삭제를 보장 합니다. 이 사용할 수 있도록 사용 하기 위해 다른 코드입니다.  
  
 관리 되는 리소스를 사용자의 추가 코딩 없이.NET Framework 가비지 수집기 (GC)에서 처리 합니다. 불필요 한 `Using` 관리 되는 리소스에 대 한 블록입니다. 그러나 계속 사용할 수 있습니다는 `Using` 블록을 가비지 수집기에 대 한 대기 하지 않고 관리 되는 리소스를 삭제 합니다.  
  
 A `Using` 블록에는 세 부분으로 구성: 취득, 사용 및 삭제 합니다.  
  
-   *취득* 변수를 만들고 시스템 리소스를 참조 하 여 초기화 하는 것을 의미 합니다. `Using` 문은 하나 이상의 리소스를 획득할 수 또는 블록에 들어가기 전에 정확히 한 개의 리소스를 획득 하 고에 제공할 수 있습니다는 `Using` 문. 제공 하는 경우 `resourceexpression`, 제어를 전달 하기 전에 해당 리소스를 취득 해야 합니다는 `Using` 문.  
  
-   *사용 현황* 리소스에 액세스 하 고 사용 하 여 작업을 수행 합니다. 사이 있는 문은 `Using` 및 `End Using` 리소스 사용을 나타냅니다.  
  
-   *폐기* 호출 의미는 <xref:System.IDisposable.Dispose%2A> 개체에서 메서드 `resourcename`합니다. 따라서 개체를를 해당 리소스를 완전히 종료할 수 있습니다. `End Using` 문 아래에 있는 리소스를 삭제는 `Using` 블록의 제어 합니다.  
  
## <a name="behavior"></a>동작  
 A `Using` 블록 처럼 작동 한 `Try`... `Finally` 구문은 `Try` 리소스를 사용 하는 블록 및 `Finally` 처럼 합니다. 이 인해는 `Using` 블록은 블록을 종료 하는 방법에 관계 없이 리소스의 삭제 합니다. 이 경우에 처리 되지 않은 예외를 제외 하 고는 <xref:System.StackOverflowException>합니다.  
  
 에 의해 획득 되는 모든 리소스 변수의 범위는 `Using` 문을로 제한 됩니다.는 `Using` 블록입니다.  
  
 하나 이상의 시스템 리소스를 지정 하는 경우는 `Using` 중첩 문, 효과 동일 `Using` 내에 다른 하나를 차단 합니다.  
  
 경우 `resourcename` 은 `Nothing`에 대 한 호출이 <xref:System.IDisposable.Dispose%2A> 설정 되 면 예외가 throw 됩니다.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>구조적된 예외 처리를 사용 하 여 블록 내에서  
 내에서 발생할 수 있는 예외를 처리 해야 하는 경우는 `Using` 블록 전체를 추가할 수 있습니다 `Try`... `Finally` 를 생성 합니다. 한 경우를 처리 하는 경우 여기서는 `Using` 문을 아닙니다. 리소스를 획득 하기 위한 성공 여부를 테스트할 수 `resourcename` 은 `Nothing`합니다.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Using 블록 대신 구조적된 예외 처리  
 보다 세부적인 제어를 사용 하는 리소스를 확보 하거나 추가 코드가 필요는 `Finally` 블록, 다시 작성할 수 있습니다는 `Using` 차단는 `Try`... `Finally` 생성 합니다. 다음 예제에서는 스 켈 레 톤 `Try` 및 `Using` 가져오기 및 삭제에 해당 하는 구문을 `resource`합니다.  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  내의 코드는 `Using` 블록에 있는 개체를 할당 안 `resourcename` 변수입니다. 종료 하면는 `Using` 블록, 리소스가 삭제 되 고 다른 변수 가리키는 리소스에 액세스할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 log.txt의 이름이 고 두 줄 텍스트 파일에 기록 하는 파일을 만듭니다. 이 예제에서는 또한 파일 읽고 줄의 텍스트를 표시 합니다.  
  
 때문에 <xref:System.IO.TextWriter> 및 <xref:System.IO.TextReader> 클래스 구현에서 <xref:System.IDisposable> 는 코드에서 사용할 수 있는 인터페이스를 `Using` 문을 파일 올바르게 닫힌 쓰기 및 읽기 작업을 합니다.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IDisposable>  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [방법: 시스템 리소스 해제](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
