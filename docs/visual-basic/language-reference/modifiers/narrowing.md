---
title: "Narrowing (Visual Basic) | Microsoft Docs"
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
  - "vb.narrowing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversions, type"
  - "type conversion"
  - "conversions, data type"
  - "Narrowing keyword"
  - "data type conversion"
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Narrowing (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변환 연산자\(`CType`\)가 클래스나 구조체를 원래 클래스나 구조체에 사용하던 일부 값을 저장하지 못할 수도 있는 형식으로 변환하도록 지정합니다.  
  
## Narrowing 키워드를 사용한 변환  
 변환 프로시저에는 `Narrowing`과 함께 `Public Shared`를 지정해야 합니다.  
  
 축소 변환은 런타임에 항상 성공하는 것은 아니며 실패하거나 데이터가 손실될 수 있습니다.  예를 들어, `Long`에서 `Integer`로, `String`에서 `Date`로, 기본 형식에서 파생 형식으로 등이 있습니다.  기본 형식은 파생 형식의 모든 멤버가 포함되지 않을 수 있기 때문에 파생된 형식의 인스턴스가 아니므로 위에서 나열한 변환 중 마지막 변환도 축소 변환입니다.  
  
 `Option Strict`가 `On`이면 사용하는 코드에서 모든 축소 변환에 `CType`을 사용해야 합니다.  
  
 `Narrowing` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## 참고 항목  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)