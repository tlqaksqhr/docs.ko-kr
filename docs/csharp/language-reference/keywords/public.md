---
title: "public(C# 참조) | Microsoft Docs"
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
  - "public"
  - "public_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "public 키워드[C#]"
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# public(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`public` 키워드는 형식 및 형식 멤버에 대한 액세스 한정자입니다.  공용 액세스는 허용도가 가장 높은 액세스 수준입니다.  다음 예제처럼 public 멤버는 액세스에 제한이 없습니다.  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) 및 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하십시오.  
  
## 예제  
 다음 예제에는 두 개의 클래스 `PointTest` 및 `MainClass`가 선언되어 있습니다.  `PointTest`의 public 멤버인 `x` 및 `y`에는 `MainClass`에서 직접 액세스할 수 있습니다.  
  
 [!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 `public` 액세스 수준을 [private](../../../csharp/language-reference/keywords/private.md) 또는 [protected](../../../csharp/language-reference/keywords/protected.md)로 변경하면 다음과 같은 오류 메시지가 나타납니다.  
  
 보호 수준 때문에 'PointTest.y'에 액세스할 수 없습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)