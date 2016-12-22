---
title: "protected(C# 참조) | Microsoft Docs"
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
  - "protected"
  - "protected_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "protected 키워드[C#]"
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# protected(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`protected` 키워드는 멤버 액세스 한정자입니다.  보호된 멤버는 해당 클래스 내에서와 파생 클래스 인스턴스에서 액세스할 수 있습니다.  다른 액세스 한정자와 `protected`를 비교하려면 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하십시오.  
  
## 예제  
 기본 클래스의 보호된 멤버를 파생 클래스에서 액세스할 수 있는 경우는 해당 파생 클래스 형식을 통해 액세스하는 경우뿐입니다.  예를 들어, 다음의 코드 세그먼트를 참조하십시오.  
  
 [!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 `a.x = 10` 문은 클래스 B의 인스턴스가 아니라 정적 메서드인 Main 내에서 만들어지므로 오류를 생성합니다.  
  
 구조체는 상속되지 않으므로 구조체 멤버는 보호될 수 없습니다.  
  
## 예제  
 이 예제의 경우 `DerivedPoint` 클래스는 `Point`에서 파생됩니다.  따라서 파생된 클래스에서 기본 클래스의 보호된 멤버에 직접 액세스할 수 있습니다.  
  
 [!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 `x` 및 `y`의 액세스 수준을 [private](../../../csharp/language-reference/keywords/private.md)으로 변경하면 컴파일러가 오류 메시지를 생성합니다.  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)