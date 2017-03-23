---
title: "override(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "override"
  - "override_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "override 키워드[C#]"
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# override(C# 참조)
`override` 한정자는 상속된 메서드, 속성, 인덱서 또는 이벤트의 추상 또는 가상 구현을 확장하거나 수정하는 데 필요합니다.  
  
## 예제  
 이 예제에서 `Area`는 추상 `ShapesClass`에서 상속되므로 `Square` 클래스는 `Area`의 재정의된 구현을 제공해야 합니다.  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 `override` 메서드는 기본 클래스에서 상속된 멤버를 새로 구현합니다.  `override` 선언에 의해 재정의된 메서드를 재정의된 기본 메서드라고 합니다.  재정의된 기본 메서드의 시그니처는 `override` 메서드의 시그니처와 같아야 합니다.  상속에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하십시오.  
  
 비 가상 메서드 또는 정적 메서드는 재정의할 수 없습니다.  재정의된 기본 메서드는 `virtual`, `abstract` 또는 `override` 메서드이어야 합니다.  
  
 `override` 선언을 사용하여 `virtual` 메서드의 액세스 가능성을 변경할 수 없습니다.  `override` 메서드와 `virtual` 메서드의 [액세스 수준 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)는 모두 동일해야 합니다.  
  
 `new`, `static` 또는 `virtual` 한정자를 사용하여 `override` 메서드를 한정할 수 없습니다.  
  
 속성 선언을 재정의할 때는 상속된 속성과 동일한 액세스 한정자, 형식 및 이름을 정확히 지정해야 하며 재정의된 속성은 `virtual`, `abstract` 또는 `override`여야 합니다.  
  
 `override` 키워드를 사용하는 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하십시오.  
  
## 예제  
 이 예제에서는 `Employee`라는 기본 클래스와 `SalesEmployee`라는 파생 클래스를 정의합니다.  `SalesEmployee` 클래스는 추가 속성 `salesbonus`를 포함하며 이를 고려하여 `CalculatePay` 메서드를 재정의합니다.  
  
 [!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)