---
title: "Procedures in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "procedures, structured code"
  - "Visual Basic code, procedures"
  - "procedures, types of"
  - "structured code, procedures"
  - "procedures"
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Procedures in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*프로시저*는 선언문\(`Function`, `Sub`, `Operator`, `Get`, `Set`\)과 짝이 되는 `End` 선언 사이에 포함된 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문 블록입니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 모든 실행문은 일부 프로시저 안에 있어야 합니다.  
  
## 프로시저 호출  
 프로시저는 코드의 다른 위치에서 호출됩니다.  이를 *프로시저 호출*이라고 합니다.  프로시저는 실행을 마치면 자신을 *호출 코드*로 제어를 반환합니다.  호출 코드는 문 또는 문 내의 식이며, 프로시저 이름을 지정하여 제어를 전달합니다.  
  
## 프로시저에서 반환  
 프로시저는 실행을 마치면 호출 코드로 제어를 반환합니다.  프로시저는 [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), 해당 프로시저에 적합한 [Exit Statement](../../../../visual-basic/language-reference/statements/exit-statement.md) 또는 해당 프로시저의 [End \<keyword\> Statement](../../../../visual-basic/language-reference/statements/end-keyword-statement.md) 문을 사용하여 제어를 반환합니다.  그러면 제어가 프로시저 호출 점을 따라 호출 코드로 전달됩니다.  
  
-   `Return` 문을 사용하면 제어가 호출 코드로 즉시 반환됩니다.  `Return` 문 뒤에 오는 문은 실행되지 않습니다.  같은 프로시저 내에서 `Return` 문을 두 개 이상 사용할 수 있습니다.  
  
-   `Exit Sub` 또는 `Exit Function` 문을 사용하면 제어가 호출 코드로 즉시 반환됩니다.  `Exit` 문 뒤에 오는 문은 실행되지 않습니다.  같은 프로시저 내에서 `Exit` 문을 두 개 이상 사용할 수 있으며 `Return` 문과 `Exit` 문을 함께 사용할 수 있습니다.  
  
-   프로시저에 `Return` 또는 `Exit` 문이 없는 경우 프로시저는 프로시저 본문의 마지막 문 뒤에 오는 `End Sub` 또는 `End Function`, `End Get` 또는 `End Set` 문으로 끝납니다.  `End` 문은 제어를 호출 코드로 즉시 반환합니다.  단일 프로시저에서 `End` 문은 하나만 사용할 수 있습니다.  
  
## 매개 변수 및 인수  
 대부분의 경우 프로시저는 호출될 때마다 다른 데이터에서 작업을 수행해야 합니다.  이 정보를 프로시저에 프로시저 호출의 일부로 전달할 수 있습니다.  프로시저는 0개 이상의 *매개 변수*를 정의하며 각 매개 변수는 전달되어야 하는 값을 나타냅니다.  프로시저 정의의 각 매개 변수는 프로시저 호출의 *인수*에 해당합니다.  인수는 지정한 프로시저 호출의 해당 매개 변수에 전달하는 값을 나타냅니다.  
  
## 프로시저 유형  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 다음과 같은 여러 유형의 프로시저를 사용합니다.  
  
-   [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)는 동작만 수행하고 호출 코드에 값을 반환하지는 않습니다.  
  
-   이벤트 처리 프로시저는 사용자 동작이나 프로그램 실행으로 인해 발생한 이벤트에 응답하여 실행되는 `Sub` 프로시저입니다.  
  
-   [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)는 호출 코드에 값을 반환할 뿐만 아니라  값을 반환하기 전에 다른 작업을 수행할 수 있습니다.  
  
-   [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)는 개체나 모듈의 속성 값을 반환하고 할당합니다.  
  
-   [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)는 피연산자 하나 또는 둘 다가 새로 정의된 클래스 또는 구조체인 경우 표준 연산자의 동작을 정의합니다.  
  
-   [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)는 일반 매개 변수 외에도 하나 이상의 *형식 매개 변수*를 정의하므로 호출 코드는 호출할 때마다 특정 데이터 형식을 전달할 수 있습니다.  
  
## 프로시저 및 구조적 코드  
 응용 프로그램의 모든 코드 줄은 특정 프로시저\(예: `Main`, `calculate`, `Button1_Click`\) 내에 있어야 합니다.  큰 프로시저를 보다 작게 세분화하면 더 이해하기 쉬운 응용 프로그램을 만들 수 있습니다.  
  
 프로시저는 자주 사용하는 계산, 텍스트 및 컨트롤 조작, 데이터베이스 운영 등과 같이 반복적인 작업이나 공유 작업을 수행하는 경우에 유용합니다.  코드의 서로 다른 위치에서 프로시저를 호출할 수 있기 때문에 프로시저를 응용 프로그램의 빌드 블록으로 사용할 수 있습니다.  
  
 프로시저를 사용하여 코드를 작성하면 다음과 같은 장점이 있습니다.  
  
-   프로시저를 사용하면 프로그램을 개별적인 논리 단위로 구분할 수 있습니다.  개별 단위로 디버깅하는 것이 프로시저 없이 프로그램 전체를 디버깅하는 것보다 쉽습니다.  
  
-   어떤 프로그램에 맞게 개발한 프로시저를 거의 수정하지 않고 다른 프로그램에 사용할 수 있습니다.  이렇게 하면 코드 중복을 방지할 수 있습니다.  
  
## 참고 항목  
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)