---
title: "How to: Create a Procedure (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "Visual Basic code, reusing"
  - "procedure declarations"
  - "procedures, about procedures"
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

선언문의 시작\(`Sub` 또는 `Function`\)과 선언문의 끝\(`End Sub` 또는 `End Function`\) 사이에 프로시저를 삽입합니다.  모든 프로시저의 코드가 이 두 문 사이에 위치합니다.  
  
 프로시저 안에 다른 프로시저가 포함될 수 없으므로, 프로시저의 시작 문과 끝 문은 다른 모든 프로시저의 밖에 있어야 합니다.  
  
 여러 위치에서 같은 작업을 수행하는 코드를 사용할 경우에는 해당 작업을 프로시저로 한 번 작성해 놓고 코드의 여러 위치에서 호출할 수 있습니다.  
  
### 값을 반환하지 않는 프로시저를 만들려면  
  
1.  다른 모든 프로시저 밖에서 `Sub` 문을 먼저 사용하고 `End Sub` 문을 사용합니다.  
  
2.  `Sub` 문에서 `Sub` 키워드와 프로시저 이름을 지정한 다음 매개 변수 목록을 괄호 안에 지정합니다.  
  
3.  프로시저의 코드 문을 `Sub` 문과 `End Sub` 문 사이에 삽입합니다.  
  
### 값을 반환하는 프로시저를 만들려면  
  
1.  다른 모든 프로시저 밖에서 `Function` 문을 먼저 사용하고 `End Function` 문을 사용합니다.  
  
2.  `Function` 문에서 `Function` 키워드와 프로시저 이름을 지정한 다음 매개 변수 목록을 괄호 안에 지정하고 그 뒤에 반환 값의 데이터 형식을 나타내는 `As` 절을 지정합니다.  
  
3.  프로시저의 코드 문을 `Function` 문과 `End Function` 문 사이에 삽입합니다.  
  
4.  `Return` 문을 사용하여 값을 호출 코드로 반환합니다.  
  
### 새 프로시저를 이전의 반복 코드 블록과 연결하려면  
  
1.  이전 코드에서 액세스할 수 있는 위치에 새 프로시저를 정의해야 합니다.  
  
2.  이전의 반복 코드 블록에서 반복 작업을 수행하는 여러 문을 `Sub` 또는 `Function` 프로시저를 호출하는 단일 문으로 바꿉니다.  
  
3.  프로시저가 값을 반환하는 `Function`이면 호출 문에서 반환된 값을 사용하여 변수에 저장하는 등의 작업을 수행하도록 합니다. 그렇지 않으면 값이 손실됩니다.  
  
## 예제  
 다음 `Function` 프로시저는 직각 삼각형의 두 변의 값을 사용하여 가장 긴 변\(빗변\)의 길이를 계산합니다.  
  
 [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [개체 지향 프로그래밍](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)