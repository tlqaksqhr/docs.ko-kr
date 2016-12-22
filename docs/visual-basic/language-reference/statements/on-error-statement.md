---
title: "On Error Statement (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.OnError"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, control flow"
  - "Resume Next statement"
  - "errors [Visual Basic], trapping"
  - "error handling, On Error statement"
  - "Next statement, On Error"
  - "control flow, branching"
  - "Error keyword"
  - "execution, conditional"
  - "Resume statement, and On Error statement"
  - "Error statement, and On Error statement"
  - "GoTo statement, and On Error statement"
  - "branching, on error"
  - "conditional statements, On Error"
  - "On Error statement, syntax"
  - "On keyword"
  - "run-time errors, handling"
  - "On Error statement"
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# On Error Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

오류 처리 루틴을 사용하고 프로시저에서 루틴의 위치를 지정합니다. 이 문은 오류 처리 루틴의 사용을 해제하는 데에도 사용할 수 있습니다.  
  
 `On Error` 문을 사용하지 않은 상태에서 발생하는 런타임 오류는 모두 심각한 오류로, 이러한 경우에는 오류 메시지가 표시되면서 실행이 중단됩니다.  
  
 가능 하면 구조적된 예외가 비구조적된 예외 처리를 사용 하지 않고 코드에서 처리를 사용 하면 단어 추천 하는 `On Error` 문의입니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
> [!NOTE]
>  `Error` 키워드는 또한 이전 버전과의 호환성을 위해 지원되는 [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md)에서도 사용됩니다.  
  
## 구문  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`GoTo` `line`|필수적 요소인 `line` 인수에 지정된 줄에서 시작하는 오류 처리 루틴을 사용합니다.  `line` 인수에는 임의의 줄 레이블이나 줄 번호를 사용할 수 있습니다.  런타임 오류가 발생하면 제어가 지정된 줄로 분기하여 오류 처리기를 활성화합니다.  지정된 줄은 `On Error` 문과 같은 프로시저에 있어야 합니다. 그렇지 않으면 컴파일 타임 오류가 발생합니다.|  
|`GoTo` 0|현재 프로시저에서 사용 가능한 오류 처리기를 사용하지 않고 `Nothing`으로 다시 설정합니다.|  
|`GoTo` \-1|현재 프로시저에서 사용 가능한 예외 처리를 사용하지 않고 `Nothing`으로 다시 설정합니다.|  
|`Resume Next`|런타임 오류가 발생하면 오류가 발생한 문 바로 다음으로 제어를 이동하고 이 지점에서 계속 실행하도록 지정합니다.  개체에 액세스할 때는 `On Error GoTo` 대신 이 폼을 사용합니다.|  
  
## 설명  
  
> [!NOTE]
>  가능 하면 코드에서 구조적된 예외 처리는 비구조적된 예외 처리를 사용 하 여 대신 사용 하는 것이 좋습니다 하는 `On Error` 문의입니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
 "사용 가능한" 오류 처리기는 `On Error` 문에 의해 사용 가능하도록 설정된 오류 처리기이며  "활성화된" 오류 처리기는 현재 오류를 처리하고 있는 사용 가능한 처리기입니다.  
  
 오류 처리기가 활성화되어 있을 때 오류 발생과 `Resume`, `Exit Sub`, `Exit Function` 또는 `Exit Property` 문의 사이에서 오류가 발생하면 현재 프로시저의 오류 처리기가 오류를 처리할 수 없으며  제어가 호출 프로시저로 반환됩니다.  
  
 호출 프로시저에 사용 가능한 오류 처리기가 있으면 해당 오류 처리기가 활성화되어 오류를 처리합니다.  호출 프로시저의 오류 처리기도 활성화되어 있는 경우 사용 가능하지만 비활성화된 오류 처리기를 찾을 때까지 이전의 호출 프로시저로 제어가 다시 전달됩니다.  이러한 오류 처리기를 찾지 못한 상태에서 실제로 발생하는 오류는 치명적인 오류가 됩니다.  
  
 오류 처리기가 제어를 다시 특정 호출 프로시저로 넘길 때마다 해당 프로시저가 현재 프로시저가 됩니다.  프로시저에서 오류 처리기가 오류를 처리하고 나면 현재 프로시저의 `Resume` 문에 지정된 지점에서 실행이 재개됩니다.  
  
> [!NOTE]
>  오류 처리 루틴은 `Sub` 프로시저나 `Function` 프로시저가 아닙니다.  이 루틴은 줄 레이블이나 줄 번호로 표시된 코드의 일부입니다.  
  
## Number 속성  
 오류 처리 루틴은 `Err` 개체의 `Number` 속성 값에 따라 오류의 원인을 판단합니다.  다른 오류가 발생하거나 오류를 발생시킬 수 있는 프로시저가 호출되기 전에 오류 처리 루틴은 `Err` 개체의 관련 속성 값을 테스트하거나 저장해야 합니다.  `Err` 개체의 속성 값에는 가장 최근의 오류만 반영됩니다.  `Err.Number`와 관련된 오류 메시지는 `Err.Description`에 포함되어 있습니다.  
  
## Throw 문  
 `Err.Raise` 메서드로 인해 오류가 발생하면 <xref:System.Exception> 클래스의 새로 생성된 인스턴스에 `Exception` 속성이 설정됩니다.  파생 예외 형식의 예외 발생에 대해 언어에서 `Throw` 문을 사용할 수 있습니다.  이 문은 throw될 예외 인스턴스인 단일 매개 변수를 갖습니다.  다음 예제는 기존의 예외 처리 지원 기능과 이 기능들을 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 `On Error GoTo` 문은 예외 클래스와 관계없이 모든 오류를 포착합니다.  
  
## On Error Resume Next  
 `On Error Resume Next` 문은 런타임 오류를 발생시킨 문의 다음 문 또는 `On Error Resume Next` 문을 포함하는 프로시저의 외부에서 가장 최근에 호출한 문의 다음 문이 계속 실행됩니다.  이 문을 사용하면 런타임 오류가 발생해도 계속 실행할 수 있습니다.  프로시저 안의 다른 위치로 제어를 전송하지 않고 오류가 발생할 위치에 오류 처리 루틴을 배치할 수 있습니다.  다른 프로시저를 호출하면 `On Error Resume Next` 문이 비활성화되므로 해당 루틴 내에서 인라인 오류 처리를 수행하려는 경우 호출되는 각 루틴에서 `On Error Resume Next` 문을 실행해야 합니다.  
  
> [!NOTE]
>  다른 개체에 액세스하는 동안 발생한 오류를 처리할 때는 `On Error GoTo` 대신 `On Error Resume Next` 구문을 사용하는 것이 좋습니다.  각 개체와의 상호 작용 후에 `Err`를 검사하면 코드에서 액세스한 개체를 확인할 수 있습니다.  원래 오류를 발생시킨 개체\(`Err.Source`에 지정된 개체\)는 물론 `Err.Number`에 오류 코드를 넣은 개체도 확인할 수 있습니다.  
  
## On Error GoTo 0  
 `On Error GoTo 0`은 현재 프로시저에서 오류 처리를 해제합니다.  이 문이 오류 처리 코드의 시작으로 0번 줄을 지정하지는 않습니다. 이는 프로시저에 0번 줄이 있더라도 마찬가지입니다.  `On Error GoTo 0` 문을 사용하지 않으면 프로시저 종료 시 오류 처리기가 자동으로 비활성화됩니다.  
  
## On Error GoTo \-1  
 `On Error GoTo -1`은 현재 프로시저에서 예외 처리를 해제합니다.  이 문이 오류 처리 코드의 시작으로 \-1번 줄을 지정하지는 않습니다. 이는 프로시저에 \-1번 줄이 있더라도 마찬가지입니다.  `On Error GoTo -1` 문을 사용하지 않으면 프로시저 종료 시 예외가 자동으로 비활성화됩니다.  
  
 오류가 발생하지 않은 경우에 오류 처리 코드가 실행되지 않도록 하려면 다음과 같이 오류 처리 루틴 바로 앞에 `Exit Sub`, `Exit Function` 또는 `Exit Property` 문을 넣습니다.  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 여기에서 오류 처리 코드가 `Exit Sub` 문 다음과 `End Sub` 문 앞에 나오므로 프로시저 흐름과 구분할 수 있습니다.  오류 처리 코드는 프로시저의 어느 위치에나 배치할 수 있습니다.  
  
## 포착되지 않은 오류  
 개체에서 포착되지 않은 오류들은 해당 개체가 실행 파일로 실행 중인 경우 제어 응용 프로그램으로 반환됩니다.  개발 환경에서 포착되지 않은 오류들은 적절한 옵션이 설정된 경우에만 제어 응용 프로그램으로 반환됩니다.  디버깅 동안 설정할 수 있는 옵션, 이러한 옵션을 설정하는 방법 및 호스트가 클래스를 만들 수 있는지에 대한 자세한 내용은 호스트 응용 프로그램의 설명서를 참조하십시오.  
  
 다른 개체들에 액세스하는 개체를 만들 경우 해당 개체가 다시 전달하는 모든 처리되지 않은 오류를 처리해야 합니다.  이러한 오류를 처리할 수 없는 경우 `Err.Number`의 오류 코드를 사용자 오류 중 하나로 매핑한 후 사용자 개체 호출자에게 다시 전달합니다.  오류 코드를 `VbObjectError` 상수에 추가하여 오류를 지정해야 합니다.  예를 들어, 오류 코드가 1052이면 다음과 같이 할당합니다.  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  Windows DLL\(동적 연결 라이브러리\)을 호출하는 동안 발생한 시스템 오류는 예외를 발생시키지 않으며 Visual Basic 오류 잡기를 사용하여 포착할 수 없습니다.  DLL 함수를 호출할 때는 각 반환 값을 검사하여 API 사양에 따라 성공 또는 실패를 확인하고 실패일 경우 `Err` 개체의 `LastDLLError` 속성에 있는 값을 확인합니다.  
  
## 예제  
 다음 예제에서는 먼저 `On Error GoTo` 문을 사용하여 프로시저 내에서의 오류 처리 루틴 위치를 지정합니다.  예를 들어, 0으로 나누려고 시도하면 오류 번호 6이 생성됩니다.  오류는 오류 처리 루틴에서 처리되고 컨트롤은 오류를 일으킨 문으로 돌아갑니다.  `On Error GoTo 0` 문은 오류 잡기를 해제합니다.  그런 다음 `On Error Resume Next` 문을 사용하여 오류 잡기를 늦춰 뒤에 나오는 문에 의해 생성되는 오류 컨텍스트가 파악되도록 합니다.  오류가 처리된 후 `Err.Clear`를 사용하여 `Err` 개체의 속성을 지웁니다.  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## 요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리\(Microsoft.VisualBasic.dll\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Resume Statement](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Error Messages](../../../visual-basic/language-reference/error-messages/index.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)