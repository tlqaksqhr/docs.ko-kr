---
title: "End Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.End"
  - "End"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "execution, ending"
  - "files, closing"
  - "End keyword, End statements"
  - "programs, quitting"
  - "code, exiting"
  - "program termination"
  - "End statement"
  - "execution, stopping"
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# End Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

실행을 즉시 끝냅니다.  
  
## 구문  
  
```  
End  
```  
  
## 설명  
 전체 응용 프로그램 실행을 강제로 중지시키는 절차 아무 곳에나 `End` 문을 배치할 수 있습니다.  `End`는 `Open` 문으로 연 파일을 닫고 응용 프로그램 값을 모두 지웁니다.  다른 프로그램에 해당 개체에 대한 참조가 없거나 해당 코드가 실행되지 않는 경우 응용 프로그램이 즉시 종료됩니다.  
  
> [!NOTE]
>  `End` 문은 `Dispose` 또는 `Finalize` 메서드나 다른 Visual Basic 코드를 호출하지 않고 코드 실행을 즉시 중지합니다.  다른 프로그램의 개체 참조는 모두 무효가 됩니다.  `Try` 또는 `Catch` 블록에 `End` 문이 있는 경우 해당 `Finally` 블록에 제어가 전달되지 않습니다.  
  
 `Stop` 문은 프로그램의 실행을 일시 중지하지만, `End` 문과는 달리 컴파일된 실행 파일\(.exe\)에 Stop 문이 없는 경우 파일을 닫거나 변수를 지우지 않습니다.  
  
 `End`는 열려 있는 리소스를 처리하지 않고 응용 프로그램을 종료하기 때문에 이 문을 사용하기 전에 열려 있는 모든 리소스를 닫아야 합니다.  예를 들어, 응용 프로그램에 폼이 열려 있는 경우에는 `End` 문에 제어가 전달되기 전에 해당 폼을 닫아야 합니다.  
  
 `End`는 즉시 중지해야 하는 경우에만 사용하여 그 사용을 최소화해야 합니다.  [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) 및 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)과 같은 프로시저를 일반적으로 종료하는 경우에는 해당 프로시저를 완전히 종료할 뿐만 아니라 이러한 작업을 수행할 수 있는 호출 코드를 제공합니다.  예를 들어, 콘솔 응용 프로그램은 단순히 `Main` 프로시저에서 `Return`될 수 있습니다.  
  
> [!IMPORTANT]
>  `End` 문은 <xref:System> 네임스페이스에서 <xref:System.Environment> 클래스의 <xref:System.Environment.Exit%2A> 메서드를 호출합니다.  <xref:System.Environment.Exit%2A>는 `UnmanagedCode` 권한이 있어야 합니다.  해당 권한이 없으면 <xref:System.Security.SecurityException> 오류가 발생합니다.  
  
 [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md)에 키워드를 추가하여 해당 프로시저나 블록 정의의 끝을 나타낼 수 있습니다.  예를 들어, `End Function`은 `Function` 프로시저 정의를 종료합니다.  
  
## 예제  
 다음 예제에서는 사용자가 요청할 경우 `End` 문을 사용하여 코드 실행을 종료합니다.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVersHelp60Controls/Form1.vb#64)]  
  
## 스마트 장치 개발자 참고 사항  
 이 문은 지원되지 않습니다.  
  
## 참고 항목  
 <xref:System.Security.Permissions.SecurityPermissionFlag>   
 [Stop Statement](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md)