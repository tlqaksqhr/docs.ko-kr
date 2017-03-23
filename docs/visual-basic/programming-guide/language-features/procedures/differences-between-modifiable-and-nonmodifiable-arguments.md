---
title: "Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, arguments"
  - "procedure arguments"
  - "arguments [Visual Basic], nonmodifiable"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], modifiable"
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저를 호출할 경우 일반적으로 하나 이상의 인수를 프로시저에 전달합니다.  각 인수는 내부 프로그래밍 요소에 해당합니다.  내부 요소와 인수 자체는 수정이 가능하거나 불가능할 수 있습니다.  
  
## 수정할 수 있는 요소와 수정할 수 없는 요소  
 프로그래밍 요소는 해당 값이 변경될 수 있는 *수정할 수 있는 요소*이거나 만든 후 고정 값을 가지는 *수정할 수 없는 요소*일 수 있습니다.  
  
 다음 표에서는 수정할 수 있는 프로그래밍 요소와 수정할 수 없는 프로그래밍 요소를 보여 줍니다.  
  
|수정할 수 있는 요소|수정할 수 없는 요소|  
|-----------------|-----------------|  
|개체 변수를 비롯한 지역 변수\(프로시저 내에서 선언\), 읽기 전용 제외|읽기 전용 변수, 필드 및 속성|  
|필드\(모듈, 클래스 및 구조체의 멤버 변수\), 읽기 전용 제외|상수 및 리터럴|  
|속성, 읽기 전용 제외|열거형 멤버|  
|배열 요소|식\(해당 요소를 수정할 수 있는 경우 포함\)|  
  
## 수정할 수 있는 인수와 수정할 수 없는 인수  
 *수정할 수 있는 인수*는 수정할 수 있는 내부 요소가 포함된 인수입니다.  호출 코드는 새 값을 언제든지 저장할 수 있으며 인수를 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 전달할 경우 프로시저의 코드도 호출 코드의 내부 요소를 수정할 수 있습니다.  
  
 *수정할 수 없는 인수*는 수정할 없는 내부 요소를 가지거나 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 전달되는 인수입니다.  프로시저는 호출 코드에서 내부 요소를 수정할 수 없으며 해당 요소가 수정할 수 있는 요소인 경우에도 마찬가지입니다.  수정할 수 없는 요소인 경우 호출 코드 자체에서 이를 수정할 수 없습니다.  
  
 호출된 프로시저는 수정할 수 없는 인수의 로컬 복사본을 수정할 수 있지만 이러한 수정 작업이 호출 코드에 있는 내부 요소에 영향을 주지는 않습니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)