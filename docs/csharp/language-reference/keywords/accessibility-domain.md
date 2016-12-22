---
title: "액세스 가능 도메인(C# 참조) | Microsoft Docs"
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
  - "액세스 가능 도메인[C#]"
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 액세스 가능 도메인(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

멤버의 액세스 가능 도메인은 프로그램 섹션에서 멤버가 참조될 수 있는 범위를 지정합니다.  멤버가 다른 형식 내에 중첩되어 있을 경우, 이 멤버의 액세스 가능 도메인은 멤버의 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 직접 포함하는 형식의 액세스 가능 도메인에 의해 결정됩니다.  
  
 최상위 수준 형식의 액세스 가능 도메인은 가장 작을 경우 해당 최상위 수준 형식이 선언된 프로젝트의 프로그램 텍스트가 됩니다.  즉, 도메인은 이 프로젝트의 소스 파일을 모두 포함합니다.  중첩 형식의 액세스 가능 도메인은 가장 작을 경우 해당 중첩 형식이 선언된 형식의 프로그램 텍스트가 됩니다.  즉, 이 도메인은 모든 중첩 형식을 포함하는 형식 본문입니다.  중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수 없습니다.  이러한 개념은 다음 예제에 설명되어 있습니다.  
  
## 예제  
 이 예제에는 최상위 형식인 `T1`과 두 개의 중첩 클래스 `M1` 및 `M2`가 있습니다.  각 클래스는 서로 다른 액세스 가능성이 선언된 필드를 포함하고 있습니다.  `Main` 메서드에서 각 문 뒤에 붙은 주석은 각 멤버의 액세스 가능 도메인을 나타냅니다.  액세스할 수 없는 멤버를 참조하려는 문은 주석으로 처리되어 있습니다.  액세스할 수 없는 멤버를 참조하려고 할 때 발생하는 컴파일러 오류를 보려면 주석을 한 번에 하나씩 제거하십시오.  
  
 [!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [액세스 가능성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)