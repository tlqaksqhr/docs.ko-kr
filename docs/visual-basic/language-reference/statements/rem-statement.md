---
title: "REM Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.'"
  - "vb.Rem"
  - "Rem"
  - "'"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "REM statement"
  - "comments, Visual Basic code"
  - "code comments, Visual Basic"
  - "Visual Basic code, comments"
  - "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# REM Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

프로그램의 소스 코드에 설명 주석을 포함하는 데 사용합니다.  
  
## 구문  
  
```  
REM comment  
' comment  
```  
  
## 요소  
 `comment`  
 선택적 요소.  포함시킬 주석의 텍스트입니다.  사이 공백이 필요는 `REM` 키워드 및 `comment`.  
  
## 설명  
 한 줄에 `REM` 문만 두거나 다른 문 다음에 오는 줄에 `REM` 문을 둘 수도 있습니다.  `REM` 문은 해당 줄에서 마지막 문이어야 합니다.  다른 문 다음에 `REM` 문이 오는 경우 `REM` 문과 다른 문을 공백으로 분리해야 합니다.  
  
 `REM` 대신 작은따옴표\(`'`\)를 사용할 수 있습니다.  같은 줄에서 다른 문 다음에 주석이 오거나, 줄에 단독으로 사용되는 경우에도 작은따옴표를 사용할 수 있습니다.  
  
> [!NOTE]
>  줄 연속 시퀀스\(`_`\)를 사용하여 `REM` 문을 계속할 수는 없습니다.  주석이 시작되면 컴파일러에서는 문자에 특별한 의미가 있는지 확인하지 않습니다.  여러 줄로 이루어진 주석의 경우에는 줄마다 `REM` 문 또는 주석 기호\(`'`\)를 각각 사용해야 합니다.  
  
## 예제  
 다음 예제에서는 프로그램에 설명 주석을 포함할 때 사용하는 `REM` 문을 보여 줍니다.  또한 `REM` 대신 작은따옴표\(`'`\)를 사용하는 방법도 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## 참고 항목  
 [Comments in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)   
 [방법: 코드에서 문 분리 및 결합](../Topic/How%20to:%20Break%20and%20Combine%20Statements%20in%20Code%20\(Visual%20Basic\).md)