---
title: "DirectCast Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.directCast"
  - "directCast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DirectCast keyword"
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# DirectCast Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

상속 또는 구현을 기반으로 형식 변환 작업을 소개합니다.  
  
## 설명  
 `DirectCast`는 변환을 위해 Visual Basic 런타임 도우미 루틴을 사용하지 않기 때문에 `Object` 데이터 형식 변환에 있어서 `CType`보다 나은 성능을 제공할 수 있습니다.  
  
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md) 및 [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드를 사용할 때와 같은 방법으로 `DirectCast` 키워드를 사용합니다.  첫 번째 인수로 식을 제공하고 두 번째 인수로 식을 변환할 형식을 제공합니다.  `DirectCast`를 사용하려면 두 인수의 데이터 형식 간에 상속 또는 구현 관계가 있어야 합니다.  즉, 한 형식이 다른 형식에서 상속되거나 구현된 경우라야 합니다.  
  
## 오류 및 실패  
 `DirectCast`는 상속 또는 구현 관계가 존재하지 않는 경우 컴파일러 오류를 생성합니다.  그러나 컴파일러 오류가 없다고 해서 변환이 반드시 성공적으로 완료되는 것은 아닙니다.  원하는 변환이 축소 변환인 경우에는 런타임에 변환이 실패할 수 있습니다.  이런 경우 런타임에 <xref:System.InvalidCastException> 오류가 throw됩니다.  
  
## 변환 키워드  
 다음 표에서는 형식 변환 키워드를 비교하여 보여 줍니다.  
  
|||||  
|-|-|-|-|  
|키워드|데이터 형식|인수 관계|런타임 오류|  
|[CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의해야 합니다.|<xref:System.InvalidCastException>을 throw합니다.|  
|`DirectCast`|모든 데이터 형식|한 형식이 다른 형식에서 상속되거나 구현된 경우라야 합니다.|<xref:System.InvalidCastException>을 throw합니다.|  
|[TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)|참조 형식만|한 형식이 다른 형식에서 상속되거나 구현된 경우라야 합니다.|[Nothing](../../../visual-basic/language-reference/nothing.md) 반환|  
  
## 예제  
 다음 예제에서는 런타임에서 `DirectCast`의 두 가지 사용\(실패 및 성공\)을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 앞의 예제에서 `q`의 런타임 형식은 `Double`입니다.  `Double`을 `Integer`로 변환할 수 있기 때문에 `CType`이 성공합니다.  그러나 변환이 존재하더라도 `Double`의 런타임 형식은 `Integer`와 상속 관계가 없기 때문에 첫 번째 `DirectCast`가 런타임에 실패합니다.  두 번째 `DirectCast`는 <xref:System.Windows.Forms.Form> 형식에서 <xref:System.Windows.Forms.Form>이 상속하는 <xref:System.Windows.Forms.Control> 형식으로 변환되기 때문에 성공합니다.  
  
## 참고 항목  
 <xref:System.Convert.ChangeType%2A?displayProperty=fullName>   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)