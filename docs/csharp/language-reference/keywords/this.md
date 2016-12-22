---
title: "this(C# 참조) | Microsoft Docs"
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
  - "this"
  - "this_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "this 키워드[C#]"
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# this(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`this` 키워드는 클래스의 현재 인스턴스를 가리키며 확장 메서드의 첫째 매개 변수에 대한 한정자로도 사용됩니다.  
  
> [!NOTE]
>  이 문서에서는 `this`를 클래스 인스턴스와 함게 사용하는 방법을 설명합니다.  확장 메서드에서 이를 사용하는 방법에 대한 자세한 내용은 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하십시오.  
  
 일반적으로 `this` 키워드는 다음과 같이 사용됩니다.  
  
-   예를 들어, 비슷한 이름으로 숨겨진 멤버를 지정하는 방법은 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   개체를 다른 메서드의 매개 변수로 전달하는 방법은 다음과 같습니다.  
  
    ```  
    CalcTax(this);  
    ```  
  
-   인덱서를 선언하는 방법은 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 클래스 수준에서 작성되고 개체의 일부로 포함되지 않는 정적 멤버 함수에는 `this` 포인터가 없습니다.  정적 메서드에서 `this`를 참조하려고 하면 오류가 발생합니다.  
  
## 예제  
 이 예제에서 `this`는 비슷한 이름으로 숨겨진 `Employee` 클래스 멤버\(`name`, `alias`\)를 한정하는 데 사용됩니다.  또한 다른 클래스에 속한 `CalcTax` 메서드로 개체를 전달하는 데 사용됩니다.  
  
 [!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [메서드](../../../fsharp/language-reference/members/methods.md)