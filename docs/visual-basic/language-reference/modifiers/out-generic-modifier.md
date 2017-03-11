---
title: "Out (Generic Modifier) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.VarianceOut"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Out keyword [Visual Basic]"
  - "covariance, Out keyword [Visual Basic]"
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Out (Generic Modifier) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

제네릭 형식 매개 변수의 경우 `Out` 키워드는 형식이 공변\(covariant\)임을 나타냅니다.  
  
## 설명  
 공 분산을 사용하면 제네릭 매개 변수로 지정된 형식보다 더 많이 파생된 형식을 사용할 수 있습니다.  이 경우 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 가능합니다.  
  
 자세한 내용은 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 규칙  
 제네릭 인터페이스와 대리자에서 `Out` 키워드를 사용할 수 있습니다.  
  
 제네릭 인터페이스에서 다음 조건을 충족하는 경우 형식 매개 변수를 공변\(covariant\)으로 선언할 수 있습니다.  
  
-   형식 매개 변수가 인터페이스 메서드의 반환 형식으로만 사용되고 메서드 인수의 형식으로 사용되지 않는 경우.  
  
    > [!NOTE]
    >  그러나 이 규칙에는 한 가지 예외가 있습니다.  공변\(covariant\) 인터페이스에서 반공변\(contravariant\) 제네릭 대리자가 메서드 매개 변수인 경우에는 공변\(covariant\) 형식을 이 대리자에 대한 제네릭 형식 매개 변수로 사용할 수 있습니다.  공변\(covariant\) 및 반공변\(contravariant\) 제네릭 대리자에 대한 자세한 내용은 [대리자의 가변성](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md) 및 [Func 및 Action 제네릭 대리자에 가변성 사용](../Topic/Using%20Variance%20for%20Func%20and%20Action%20Generic%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
-   형식 매개 변수가 인터페이스 메서드에 대한 제네릭 제약 조건으로 사용되지 않는 경우  
  
 제네릭 대리자에서 형식 매개 변수가 메서드 반환 형식으로만 사용되고 메서드 인수로는 사용되지 않는 경우에만 공변\(covariant\)으로 선언될 수 있습니다.  
  
 공 분산 및 반공 분산은 참조 형식에만 지원되고 값 형식에는 지원되지 않습니다.  
  
 Visual Basic에서는 대리자 형식을 지정하지 않으면 공변\(covariant\) 인터페이스에서 이벤트를 선언할 수 없습니다.  또한 공변\(covariant\) 인터페이스에서는 중첩 클래스, 열거형 또는 구조체를 사용할 수 없고 중첩 인터페이스만 사용할 수 있습니다.  
  
## 동작  
 공변\(covariant\) 형식 매개 변수가 있는 인터페이스의 메서드는 형식 매개 변수로 지정된 형식보다 더 많이 파생된 형식을 반환할 수 있습니다.  예를 들어, .NET Framework 4의 <xref:System.Collections.Generic.IEnumerable%601>에서 형식 T가 공변\(covariant\)이므로 특수 변환 메서드를 사용하지 않고도 `IEnumerabe(Of String)` 형식의 개체를 `IEnumerable(Of Object)` 형식의 개체에 할당할 수 있습니다.  
  
 공변\(covariant\) 대리자는 같은 형식이지만 더 많이 파생된 제네릭 형식 매개 변수를 사용하는 다른 대리자에게 할당할 수 있습니다.  
  
## 예제  
 다음 예제에서는 공변\(covariant\) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.  또한 공변\(covariant\) 인터페이스를 구현하는 클래스의 암시적 변환을 사용하는 방법도 보여 줍니다.  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/out-generic-modifier_1.vb)]  
  
## 예제  
 다음 예제에서는 공변\(covariant\) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.  또한 대리자 형식을 암시적으로 변환하는 방법도 보여 줍니다.  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/out-generic-modifier_2.vb)]  
  
## 참고 항목  
 [제네릭 인터페이스의 가변성](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)