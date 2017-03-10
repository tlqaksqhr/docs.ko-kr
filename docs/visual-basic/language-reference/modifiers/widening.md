---
title: "Widening (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.widening"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversions, type"
  - "type conversion"
  - "conversions, data type"
  - "Widening keyword"
  - "data type conversion"
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Widening (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변환 연산자\(`CType`\)가 클래스나 구조체를 원래 클래스나 구조체의 모든 가능한 값을 보유할 수 있는 형식으로 변환함을 나타냅니다.  
  
## Widening 키워드로 변환  
 변환 프로시저에는 `Widening`과 함께 `Public Shared`를 지정해야 합니다.  
  
 확대 변환은 런타임에 항상 성공하며 데이터 손실이 없습니다.  `Single`을 `Double`로 변환하거나 `Char`를 `String`으로 변환하거나 파생된 형식을 해당 기본 형식으로 변환하는 예를 들 수 있습니다.  파생된 형식에는 기본 형식의 모든 멤버가 포함되어 기본 형식의 인스턴스가 되므로 파생된 형식을 해당 기본 형식으로 변환하는 것은 확대 변환입니다.  
  
 `Option Strict`가 `On`으로 설정되어 있는 경우에도 사용하는 코드에서 확대 변환에 대해 `CType`을 사용할 필요가 없습니다.  
  
 `Widening` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 확대 변환 및 축소 변환 연산자의 예제 정의는 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조하십시오.  
  
## 참고 항목  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)