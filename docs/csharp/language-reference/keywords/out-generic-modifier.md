---
title: "out(제네릭 한정자)(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "공 분산, out 키워드[C#]"
  - "out 키워드[C#]"
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# out(제네릭 한정자)(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

제네릭 형식 매개 변수의 경우 `out` 키워드는 형식 매개 변수가 공변\(covariant\)임을 나타냅니다.  제네릭 인터페이스와 대리자에서 `out` 키워드를 사용할 수 있습니다.  
  
 공 분산을 사용하면 제네릭 매개 변수로 지정된 형식보다 더 많이 파생된 형식을 사용할 수 있습니다.  이 경우 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 가능합니다.  공 분산 및 반공 분산은 참조 형식에만 지원되고 값 형식에는 지원되지 않습니다.  
  
 공변\(covariant\) 형식 매개 변수가 있는 인터페이스의 메서드는 형식 매개 변수로 지정된 형식보다 더 많이 파생된 형식을 반환할 수 있습니다.  예를 들어, .NET Framework 4의 <xref:System.Collections.Generic.IEnumerable%601>에서 형식 T가 공변\(covariant\)이므로 특수 변환 메서드를 사용하지 않고도 `IEnumerabe(Of String)` 형식의 개체를 `IEnumerable(Of Object)` 형식의 개체에 할당할 수 있습니다.  
  
 공변\(covariant\) 대리자는 같은 형식이지만 더 많이 파생된 제네릭 형식 매개 변수를 사용하는 다른 대리자에게 할당할 수 있습니다.  
  
 자세한 내용은 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 공변\(covariant\) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.  또한 공변\(covariant\) 인터페이스를 구현하는 클래스의 암시적 변환을 사용하는 방법도 보여 줍니다.  
  
 [!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 제네릭 인터페이스에서 다음 조건을 충족하는 경우 형식 매개 변수를 공변\(covariant\)으로 선언할 수 있습니다.  
  
-   형식 매개 변수가 인터페이스 메서드의 반환 형식으로만 사용되고 메서드 인수의 형식으로 사용되지 않는 경우.  
  
    > [!NOTE]
    >  그러나 이 규칙에는 한 가지 예외가 있습니다.  공변\(covariant\) 인터페이스에서 반공변\(contravariant\) 제네릭 대리자가 메서드 매개 변수인 경우에는 공변\(covariant\) 형식을 이 대리자에 대한 제네릭 형식 매개 변수로 사용할 수 있습니다.  공변\(covariant\) 및 반공변\(contravariant\) 제네릭 대리자에 대한 자세한 내용은 [대리자의 가변성](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md) 및 [Func 및 Action 제네릭 대리자에 가변성 사용](../Topic/Using%20Variance%20for%20Func%20and%20Action%20Generic%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
-   형식 매개 변수가 인터페이스 메서드에 대한 제네릭 제약 조건으로 사용되지 않는 경우  
  
## 예제  
 다음 예제에서는 공변\(covariant\) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.  대리자 형식을 암시적으로 변환하는 방법도 보여 줍니다.  
  
 [!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 메서드 반환 형식으로만 사용되고 메서드 인수로는 사용되지 않는 형식의 경우 제네릭 대리자에서 해당 형식을 공변\(covariant\)으로 선언할 수 있습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [제네릭 인터페이스의 가변성](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [in](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)