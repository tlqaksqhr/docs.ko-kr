---
title: "In (Generic Modifier) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.VarianceIn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "contravariance, In keyword [Visual Basic]"
  - "In keyword [Visual Basic]"
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# In (Generic Modifier) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

제네릭 형식 매개 변수의 경우 `In` 키워드는 형식 매개 변수가 반공변\(contravariant\)임을 나타냅니다.  
  
## 설명  
 반공변성\(Contravariance\)을 사용하면 제네릭 매개 변수로 지정된 형식보다 더 적게 파생된 형식을 사용할 수 있습니다.  이 경우 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 가능합니다.  
  
 자세한 내용은 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 규칙  
 제네릭 인터페이스와 대리자에서 `In` 키워드를 사용할 수 있습니다.  
  
 형식 매개 변수가 메서드 인수의 형식으로만 사용되고 메서드 반환 형식으로는 사용되지 않는 경우 제네릭 인터페이스나 대리자에서 반공변\(contravariant\)으로 선언될 수 있습니다.  `ByRef` 매개 변수는 공변\(covariant\) 또는 반공변\(contravariant\)이 될 수 없습니다.  
  
 공 분산 또는 반공 분산은 참조 형식에만 지원되고 값 형식에는 지원되지 않습니다.  
  
 Visual Basic에서 대리자 형식을 지정하지 않으면 반공변\(contravariant\) 인터페이스에서 이벤트를 선언할 수 없습니다.  또한 반공변\(contravariant\) 인터페이스에서는 중첩 클래스, 열거형 또는 구조체만 사용할 수 있고 중첩 인터페이스는 사용할 수 없습니다.  
  
## 동작  
 반공변\(contravariant\) 형식 매개 변수가 있는 인터페이스의 메서드는 인터페이스 형식 매개 변수로 지정된 형식보다 더 적게 파생된 형식의 인수를 사용할 수 있습니다.  예를 들어 .NET Framework 4의 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 형식 T는 반공변\(contravariant\)이므로 `Person`이 `Employee`를 상속하는 경우 특수 변환 메서드를 사용하지 않고도 `IComparer(Of Person)` 형식의 개체를 `IComparer(Of Employee)` 형식의 개체에 할당할 수 있습니다.  
  
 형식이 같고 더 적게 파생된 제네릭 형식 매개 변수를 사용하는 다른 대리자에 반공변\(contravariant\) 대리자를 할당할 수 있습니다.  
  
## 예제  
 다음 예제에서는 반공변\(contravariant\) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.  또한 이 인터페이스를 구현하는 클래스의 암시적 변환을 사용하는 방법도 보여 줍니다.  
  
 [!code-vb[vbVarianceKeywords#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_1.vb)]  
  
## 예제  
 다음 예제에서는 반공변\(contravariant\) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.  또한 대리자 형식을 암시적으로 변환하는 방법도 보여 줍니다.  
  
 [!code-vb[vbVarianceKeywords#2](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_2.vb)]  
  
## 참고 항목  
 [제네릭 인터페이스의 가변성](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)