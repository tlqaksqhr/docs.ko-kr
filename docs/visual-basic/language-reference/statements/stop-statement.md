---
title: "Stop Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Stop"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "breakpoints, Stop statements"
  - "Stop statements, syntax"
  - "Stop statements"
  - "execution, suspending"
  - "processing, interrupting"
  - "processes, interrupting"
  - "execution, stopping"
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Stop Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

실행을 일시 중지합니다.  
  
## 구문  
  
```  
Stop  
```  
  
## 설명  
 프로시저 내의 임의의 위치에 `Stop` 문을 사용하여 프로그램의 실행을 일시 중지할 수 있습니다.  `Stop` 문을 사용하는 것은 코드에 중단점을 설정하는 것과 비슷합니다.  
  
 `Stop` 문은 프로그램의 실행을 일시 중지하지만, `End` 문과는 달리 컴파일된 실행 파일\(.exe\)에 Stop 문이 없는 경우 파일을 닫거나 변수를 지우지 않습니다.  
  
> [!NOTE]
>  IDE\(통합 개발 환경\) 외부에서 실행되는 코드에 `Stop` 문이 있는 경우 디버거가 호출됩니다.  이때 코드가 디버그 모드에서 컴파일되었는지, 아니면 정품\(retail\) 모드에서 컴파일되었는지에 관계없이 디버거가 호출됩니다.  
  
## 예제  
 다음 예제에서는 `Stop` 문을 사용하여 `For...Next` 루프를 통해 반복되는 실행을 일시 중지합니다.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## 참고 항목  
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)