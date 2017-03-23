---
title: "in(제네릭 한정자)(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "반공변성(contravariance), in 키워드[C#]"
  - "in 키워드[C#]"
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# in(제네릭 한정자)(C# 참조)
제네릭 형식 매개 변수의 경우 `in` 키워드는 형식 매개 변수가 반공변\(contravariant\)임을 나타냅니다.  제네릭 인터페이스와 대리자에서 `in` 키워드를 사용할 수 있습니다.  
  
 반공변성\(Contravariance\)을 사용하면 제네릭 매개 변수로 지정된 형식보다 더 적게 파생된 형식을 사용할 수 있습니다.  이 경우 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 가능합니다.  제네릭 형식 매개 변수의 공 분산과 반공 분산은 참조 형식에만 지원되고 값 형식에는 지원되지 않습니다.  
  
 형식이 메서드 인수의 형식으로만 사용되고 메서드 반환 형식으로는 사용되지 않는 경우 제네릭 인터페이스 또는 대리자에서 형식이 반공변\(contravariant\)으로 선언될 수 있습니다.  `Ref` 및 `out` 매개 변수는 variant가 될 수 없습니다.  
  
 반공변\(contravariant\) 형식 매개 변수가 있는 인터페이스의 메서드는 인터페이스 형식 매개 변수로 지정된 형식보다 더 적게 파생된 형식의 인수를 사용할 수 있습니다.  예를 들어 .NET Framework 4의 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 형식 T는 반공변\(contravariant\)이므로 `Employee`이 `Person`를 상속하는 경우 특수 변환 메서드를 사용하지 않고도 `IComparer(Of Person)` 형식의 개체를 `IComparer(Of Employee)` 형식의 개체에 할당할 수 있습니다.  
  
 형식이 같고 더 적게 파생된 제네릭 형식 매개 변수를 사용하는 다른 대리자에 반공변\(contravariant\) 대리자를 할당할 수 있습니다.  
  
 자세한 내용은 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 반공변\(contravariant\) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.  또한 이 인터페이스를 구현하는 클래스의 암시적 변환을 사용하는 방법도 보여 줍니다.  
  
 [!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## 예제  
 다음 예제에서는 반공변\(contravariant\) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.  또한 대리자 형식을 암시적으로 변환하는 방법도 보여 줍니다.  
  
 [!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)