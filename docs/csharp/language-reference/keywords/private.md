---
title: "private(C# 참조) | Microsoft Docs"
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
  - "private_CSharpKeyword"
  - "private"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "private 키워드[C#]"
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# private(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`private` 키워드는 멤버 액세스 한정자입니다.  전용 액세스는 허용도가 가장 낮은 액세스 수준입니다.  전용 멤버는 다음 예제처럼 해당 멤버가 선언되어 있는 클래스 또는 구조체의 본문 내에서만 액세스할 수 있습니다.  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 동일한 본문에서 중첩된 형식도 이 전용 멤버에 액세스할 수 있습니다.  
  
 전용 멤버가 선언되어 있는 클래스 또는 구조체 외부에서 이 멤버를 참조하면 컴파일 타임 오류가 발생합니다.  
  
 `private`을 다른 액세스 한정자와 비교하려면 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
## 예제  
 이 예제에서 `Employee` 클래스에는 `name`과 `salary`라는 두 개의 전용 데이터 멤버가 포함되어 있습니다.  이들은 private 멤버이므로 멤버 메서드를 사용해야만 액세스할 수 있습니다.  private 멤버에 대한 액세스를 제어할 수 있도록 `GetName` 및 `Salary`라는 public 메서드가 추가됩니다.  `name` 멤버에는 public 메서드를 사용하여 액세스하고, `salary` 멤버에는 public 읽기 전용 속성을 통해 액세스합니다.  자세한 내용은 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)를 참조하십시오.  
  
 [!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
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
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)