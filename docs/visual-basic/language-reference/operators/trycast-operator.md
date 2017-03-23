---
title: "TryCast Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.trycast"
  - "trycast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TryCast keyword"
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# TryCast Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

예외를 throw하지 않는 형식 변환 연산을 정의합니다.  
  
## 설명  
 변환이 실패하면 `CType`과 `DirectCast` 모두 <xref:System.InvalidCastException> 오류를 throw합니다.  이로 인해 응용 프로그램의 성능이 저하될 수 있습니다.  `TryCast`는 [Nothing](../../../visual-basic/language-reference/nothing.md)을 반환하므로, 발생 가능한 예외를 처리할 필요는 없고 반환된 결과를 `Nothing`에 대해 테스트하기만 하면 됩니다.  
  
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)와 [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) 키워드를 사용할 때와 같은 방법으로 `TryCast` 키워드를 사용합니다.  첫 번째 인수로 식을 제공하고 두 번째 인수로 식을 변환할 형식을 제공합니다.  `TryCast`는 클래스와 인터페이스 같은 참조 형식에서만 작동합니다.  이 키워드를 사용하려면 두 형식 사이에 상속 또는 구현 관계가 있어야 합니다.  즉, 한 형식이 다른 형식에서 상속되거나 구현된 경우라야 합니다.  
  
## 오류 및 실패  
 `TryCast`는 상속 또는 구현 관계가 존재하지 않을 경우 컴파일러 오류를 생성합니다.  그러나 컴파일러 오류가 없다고 해서 변환이 반드시 성공적으로 완료되는 것은 아닙니다.  원하는 변환이 축소 변환인 경우에는 런타임에 변환이 실패할 수 있습니다.  그럴 경우 `TryCast`는 [Nothing](../../../visual-basic/language-reference/nothing.md)을 반환합니다.  
  
## 변환 키워드  
 다음 표에서는 형식 변환 키워드를 비교하여 보여 줍니다.  
  
|||||  
|-|-|-|-|  
|키워드|데이터 형식|인수 관계|런타임 오류|  
|[CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의해야 합니다.|<xref:System.InvalidCastException>을 throw합니다.|  
|[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md)|모든 데이터 형식|한 형식이 다른 형식에서 상속되거나 구현된 경우라야 합니다.|<xref:System.InvalidCastException>을 throw합니다.|  
|`TryCast`|참조 형식만|한 형식이 다른 형식에서 상속되거나 구현된 경우라야 합니다.|[Nothing](../../../visual-basic/language-reference/nothing.md) 반환|  
  
## 예제  
 다음 예제에서는 `TryCast`의 사용 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## 참고 항목  
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)