---
title: "sealed(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sealed"
  - "sealed_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sealed 키워드[C#]"
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# sealed(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

클래스에 적용될 경우 `sealed` 한정자는 다른 클래스가 해당 클래스에서 상속하지 않도록 합니다.  다음 예제에서 `B` 클래스는 `A` 클래스에서 상속하지만 `B` 클래스에서 상속할 수 있는 클래스는 없습니다.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 기본 클래스의 가상 메서드나 속성을 재정의하는 메서드 또는 속성에 `sealed` 한정자를 사용할 수도 있습니다.  이렇게 하면 클래스에서 클래스를 파생시키고, 해당 클래스에서 특정 가상 메서드나 속성을 재정의하지 못하도록 할 수 있습니다.  
  
## 예제  
 다음 예제에서 `Z`는 `Y`에서 상속하지만 `Z`는 `X`에 선언되고 `Y`에 봉인된 가상 함수 `F`를 재정의할 수 없습니다.  
  
 [!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 클래스의 새 메서드 또는 속성을 정의할 때 [virtual](../../../csharp/language-reference/keywords/virtual.md)로 선언하지 않으면 파생 클래스가 재정의되지 않도록 할 수 있습니다.  
  
 추상 클래스는 추상 메서드 또는 속성의 구현을 제공하는 클래스에서 상속해야 하므로 봉인 클래스와 함께 [abstract](../../../csharp/language-reference/keywords/abstract.md) 한정자를 사용하면 오류가 발생합니다.  
  
 메서드나 속성에 `sealed` 한정자를 적용하는 경우 항상 [override](../../../csharp/language-reference/keywords/override.md)를 함께 사용해야 합니다.  
  
 구조체는 암시적으로 봉인되므로 상속할 수 없습니다.  
  
 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)를 참조하십시오.  
  
 추가 예제는 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하십시오.  
  
## 예제  
 [!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 위 예제에서 다음 문을 사용하여 봉인 클래스에서 상속할 경우  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 다음 오류 메시지가 나타납니다.  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 설명  
 클래스, 메서드 또는 속성을 봉인할지 여부를 결정하려면 일반적으로 다음 두 가지 사항을 고려해야 합니다.  
  
-   파생 클래스에서 클래스 사용자 지정 기능을 통해 얻을 수 있는 이점  
  
-   파생 클래스에서 사용자의 클래스를 수정하여 해당 클래스가 더 이상 올바르게 또는 예상대로 작동하지 않게 될 가능성  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)