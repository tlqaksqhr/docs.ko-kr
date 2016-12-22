---
title: "Error Statement | Microsoft Docs"
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
  - "vb.error"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Error statement, syntax"
  - "Error statement"
  - "Error keyword"
  - "run-time errors, codes"
  - "errors [Visual Basic], simulating"
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error Statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

오류 발생을 시뮬레이션합니다.  
  
## 구문  
  
```  
Error errornumber  
```  
  
## 요소  
 `errornumber`  
 필수 요소.  임의의 유효한 오류 번호를 사용할 수 있습니다.  
  
## 설명  
 `Error` 문은 이전 버전과 호환됩니다.  특히 새 코드에서 개체를 만들 때 런타임 오류를 생성하려면 `Err` 개체의 `Raise` 메서드를 사용합니다.  
  
 `errornumber`가 정의되어 있는 경우 `Error` 문은 `Err` 개체의 속성에 다음과 같은 기본값을 할당한 후 오류 처리기를 호출합니다.  
  
|Property|값|  
|--------------|-------|  
|`Number`|`Error` 문에 인수로 지정된 값  임의의 유효한 오류 번호를 사용할 수 있습니다.|  
|`Source`|현재 Visual Basic 프로젝트의 이름입니다.|  
|`Description`|지정된 `Number`에 대해 `Error` 함수의 반환 값에 해당하는 문자열이 있으면 문자열 식을 가지고,  문자열이 없는 경우 `Description`은 길이가 0인 문자열\(""\)을 가집니다.|  
|`HelpFile`|적합한 Visual Basic 도움말 파일의 정규화된 드라이브, 경로 및 파일 이름.|  
|`HelpContext`|`Number` 속성에 해당하는 오류에 대한 Visual Basic 도움말 파일 컨텍스트 ID입니다.|  
|`LastDLLError`|0입니다.|  
  
 오류 처리기가 없거나 사용 가능한 오류 처리기가 없는 경우 `Err` 개체 속성으로부터 오류 메시지가 만들어지고 표시됩니다.  
  
> [!NOTE]
>  일부 Visual Basic 호스트 응용 프로그램은 개체를 만들 수 없습니다.  호스트 응용 프로그램이 클래스와 개체를 만들 수 있는지 확인하려면 해당 호스트 응용 프로그램의 설명서를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Error` 문을 사용하여 오류 번호 11을 생성합니다.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## 요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리\(Microsoft.VisualBasic.dll\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>   
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Resume Statement](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Error Messages](../../../visual-basic/language-reference/error-messages/index.md)