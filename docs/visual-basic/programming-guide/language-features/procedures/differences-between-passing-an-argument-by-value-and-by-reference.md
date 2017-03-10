---
title: "Differences Between Passing an Argument By Value and By Reference (Visual Basic) | Microsoft Docs"
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
  - "ByRef keyword, passing arguments by reference"
  - "Visual Basic code, procedures"
  - "procedures, passing arguments"
  - "ByVal keyword, passing arguments by value"
  - "arguments [Visual Basic], passing by value or by reference"
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Differences Between Passing an Argument By Value and By Reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 인수를 프로시저에 전달할 때 각 인수는 호출 코드의 내부 프로그래밍 요소에 해당합니다.  이 내부 요소의 값이나 내부 요소에 대한 참조를 전달할 수 있습니다.  이를 *전달 메커니즘*이라고 합니다.  
  
## 값으로 전달  
 프로시저 정의에서 해당 매개 변수에 대해 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 키워드를 지정하여 인수를 *값으로* 전달합니다.  이 전달 메커니즘을 사용하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 내부 프로그래밍 요소의 값을 프로시저의 지역 변수에 복사합니다.  프로시저 코드는 호출 코드의 내부 요소에 액세스할 수 없습니다.  
  
## 참조로 전달  
 프로시저 정의에서 해당 매개 변수에 대해 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 지정하여 인수를 *참조로* 전달합니다.  이 전달 메커니즘을 사용하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 호출 코드의 내부 프로그래밍 요소에 대한 직접 참조를 프로시저에 제공합니다.  
  
## 전달 메커니즘 및 요소 형식  
 전달 메커니즘의 선택 기준과 내부 요소 형식의 분류 기준은 서로 다릅니다.  값으로 전달이나 참조로 전달은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 프로시저 코드에 제공하는 내용을 참조합니다.  값 형식이나 참조 형식은 프로그래밍 요소가 메모리에 저장되는 방법을 참조합니다.  
  
 그러나 전달 메커니즘과 요소 형식은 서로 연관되어 있습니다.  참조 형식의 값은 메모리의 다른 위치에 있는 데이터에 대한 포인터입니다.  즉, 값으로 참조 형식을 전달하는 경우 프로시저 코드는 내부 요소 자체에는 액세스할 수 없지만 내부 요소의 데이터에 대한 포인터를 포함합니다.  예를 들어, 요소가 배열 변수인 경우 프로시저 코드는 변수 자체에는 액세스할 수 없지만 배열 멤버에는 액세스할 수 있습니다.  
  
## 수정 기능  
 비가변 요소를 인수로 전달할 경우 `ByVal`이든 `ByRef`든 관계없이 프로시저는 호출 코드에서 비가변 요소를 수정할 수 없습니다.  
  
 다음 표에서는 수정 가능한 요소에 대한 요소 형식과 전달 메커니즘 간의 상호 작용을 요약 설명합니다.  
  
|요소 형식|`ByVal` 전달인 경우|`ByRef` 전달인 경우|  
|-----------|--------------------|--------------------|  
|값 형식\(값만 포함\)|프로시저가 변수나 변수의 멤버를 변경할 수 없습니다.|프로시저가 변수 및 변수의 멤버를 변경할 수 있습니다.|  
|참조 형식\(클래스나 구조체의 인스턴스에 대한 포인터 포함\)|프로시저가 변수를 변경할 수는 없지만 변수가 가리키는 인스턴스의 멤버는 변경할 수 있습니다.|프로시저가 변수 및 변수가 가리키는 인스턴스의 멤버를 변경할 수 있습니다.|  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)