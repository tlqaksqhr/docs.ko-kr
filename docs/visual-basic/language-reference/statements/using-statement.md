---
title: "Using Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.using"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "resource disposal"
  - "Try...Catch...Finally statements, equivalent to Using statement"
  - "resources [Visual Basic], disposing"
  - "Using statement"
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 36
---
# Using Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Using` 블록의 시작을 선언하며 선택적으로 블록이 제어하는 시스템 리소스를 가져옵니다.  
  
## 구문  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`resourcelist`|`resourceexpression`을 제공하지 않는 경우 필수적 요소입니다.  목록에 하나 이상의 시스템 리소스는이 `Using` 컨트롤을 쉼표로 구분 하 여 차단 합니다.|  
|`resourceexpression`|`resourcelist`를 제공하지 않는 경우 필수적 요소입니다.  이 `Using` 블록이 제어하는 시스템 리소스를 참조하는 참조 변수나 식입니다.|  
|`statements`|선택 사항입니다.  `Using` 블록이 실행하는 문 블록입니다.|  
|`End Using`|필수 요소.  `Using` 블록의 정의를 종료하고 이 블록이 제어하는 모든 리소스를 삭제합니다.|  
  
 `resourcelist` 구성 요소에서 각 리소스의 구문과 구성 요소는 다음과 같습니다.  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 또는  
  
 `resourcename As resourcetype = resourceexpression`  
  
## resourcelist 구성 요소  
  
|||  
|-|-|  
|용어|정의|  
|`resourcename`|필수 요소.  `Using` 블록이 제어하는 시스템 리소스를 참조하는 참조 변수입니다.|  
|`New`|`Using` 문이 리소스를 가져오는 경우 필수적 요소입니다.  리소스를 이미 가져온 경우에는 둘째 대체 구문을 사용합니다.|  
|`resourcetype`|필수 요소.  리소스의 클래스입니다.  클래스는 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.|  
|`arglist`|선택 사항입니다.  `resourcetype`의 인스턴스를 만들기 위해 생성자에 전달하는 인수의 목록입니다.  자세한 내용은 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)를 참조하십시오.|  
|`resourceexpression`|필수 요소.  `resourcetype`의 요구 사항에 맞는 시스템 리소스를 참조하는 변수 또는 식입니다.  둘째 대체 구문을 사용하는 경우 `Using` 문에 제어를 전달하기 전에 리소스를 가져와야 합니다.|  
  
## 설명  
 경우에 따라 코드에 파일 핸들, COM 래퍼 또는 SQL 연결과 같은 관리되지 않는 리소스가 필요합니다.  `Using` 블록은 코드가 이러한 리소스로 작업을 마칠 때 해당 리소스를 하나 이상 삭제합니다.  따라서 다른 코드에서 이러한 리소스를 사용할 수 있습니다.  
  
 관리되는 리소스는 구성 요소의 추가 코딩 없이 .NET Framework GC\(가비지 수집기\)에서 삭제됩니다.  관리되는 리소스에 대해서는 `Using` 블록이 필요하지 않습니다.  그래도 `Using` 블록을 사용하여 가비지 수집기를 기다리지 않고 관리 리소스를 강제로 삭제할 수 있습니다.  
  
 `Using` 블록은 가져오기, 사용 및 삭제의 세 부분으로 구성됩니다.  
  
-   *가져오기*는 시스템 리소스를 참조하기 위해 변수를 만들고 이를 초기화하는 것을 의미합니다.  `Using` 문은 하나 이상의 리소스를 가져오고 블록에 들어가기 전에 하나의 리소스만 가져와서 이 리소스를 `Using` 문에 제공할 수 있습니다.  `resourceexpression`을 제공하는 경우 `Using` 문에 제어를 전달하기 전에 리소스를 가져와야 합니다.  
  
-   *사용*은 리소스에 액세스하고 이러한 리소스를 사용하여 작업을 수행하는 것을 의미합니다.  `Using`과 `End Using` 사이에 있는 문은 리소스 사용을 나타냅니다.  
  
-   *삭제*는 `resourcename`에 있는 개체의 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하는 것을 의미합니다.  따라서 개체에서 리소스를 완전히 종료할 수 있습니다.  `End Using` 문은 `Using` 블록의 제어를 받는 리소스를 삭제합니다.  
  
## 동작  
 `Using` 블록은 `Try` 블록이 리소스를 사용하고 `Finally` 블록이 리소스를 삭제하는 `Try`...`Finally` 구문처럼 동작합니다.  따라서 블록을 종료하는 방법에 관계없이 `Using` 블록은 리소스를 삭제합니다.  <xref:System.StackOverflowException>을 제외하고 처리되지 않은 예외의 경우에도 이와 같이 동작합니다.  
  
 `Using` 문을 사용하여 가져오는 각 리소스 변수의 범위는 `Using` 블록으로 제한됩니다.  
  
 `Using` 문에 둘 이상의 시스템 리소스를 지정하면 `Using` 블록을 다른 Using 블록 내에 중첩한 것과 같습니다.  
  
 경우 `resourcename` 입니다 `Nothing`에 대 한 호출이 <xref:System.IDisposable.Dispose%2A> 변경 되 고 예외가 throw 되지 않습니다.  
  
## Using 블록 내의 구조적 예외 처리  
 `Using` 블록 내에 발생할 수도 있는 예외를 처리해야 하는 경우 전체 `Try`...`Finally` 구문을 이 블록에 추가할 수 있습니다.  `Using` 문이 리소스를 제대로 가져오지 못하는 경우를 처리할 때는 `resourcename`이 `Nothing`인지 테스트할 수 있습니다.  
  
## Using 블록 이외의 구조적 예외 처리  
 리소스 가져오기를 보다 세밀하게 제어해야 하거나 `Finally` 블록에 추가 코드가 필요한 경우 `Using` 블록을 `Try`...`Finally` 구문으로 다시 작성할 수 있습니다.  다음 예제에서는 `resource` 가져오기 및 삭제에 해당하는 기본 `Try` 및 `Using` 구문을 보여 줍니다.  
  
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
>  `Using` 블록 내부에 있는 코드는 `resourcename`에 있는 개체를 다른 변수에 할당하지 않아야 합니다.  `Using` 블록을 종료하면 리소스가 삭제되고 다른 변수는 이 블록이 가리키는 리소스에 액세스할 수 없습니다.  
  
## 예제  
 다음 예제에서는 log.txt 라는 텍스트의 두 줄을 파일에 씁니다 파일을 만듭니다.  예제에서는 또한 동일한 파일이 읽고 텍스트의 줄을 표시 합니다.  
  
 때문에 <xref:System.IO.TextWriter> 및 <xref:System.IO.TextReader> 클래스 구현에서 <xref:System.IDisposable> 인터페이스를 코드 사용할 수 있는 `Using` 파일이 닫힌 이후에 쓰기가 제대로 및 읽기 작업을 확인 하는 문을.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## 참고 항목  
 <xref:System.IDisposable>   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [How to: Dispose of a System Resource](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)