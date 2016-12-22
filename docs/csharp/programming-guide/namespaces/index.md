---
title: "네임스페이스(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "C# 언어, 네임스페이스"
  - "네임스페이스[C#]"
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 네임스페이스(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

네임스페이스는 C\# 프로그래밍에서 다음과 같은 두 가지 방식으로 중요하게 사용됩니다.  첫 번째로, .NET Framework에서는 네임스페이스를 사용하여 많은 클래스를 다음과 같이 조직화합니다.  
  
 [!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System`은 네임스페이스이고 `Console`은 이 네임스페이스에 있는 클래스입니다.  전체 이름을 사용할 필요가 없도록 다음 예제와 같이 `using` 키워드를 사용할 수 있습니다.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 자세한 내용은 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)를 참조하십시오.  
  
 두 번째로, 사용자 자신의 네임스페이스를 선언하면 큰 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 쉽게 제어할 수 있습니다.  네임스페이스를 정의하려면 다음 예제와 같이 [namespace](../../../csharp/language-reference/keywords/namespace.md) 키워드를 사용합니다.  
  
 [!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## 네임스페이스 개요  
 네임스페이스에는 다음과 같은 속성이 있습니다.  
  
-   큰 코드 프로젝트를 조직화합니다.  
  
-   `.` 연산자로 구분됩니다.  
  
-   `using directive`를 사용하면 모든 클래스에 대해 네임스페이스의 이름을 지정할 필요가 없습니다.  
  
-   `global` 네임스페이스는 "루트" 네임스페이스입니다. `global::System`은 항상 .NET Framework 네임스페이스인 `System`을 참조합니다.  
  
## 관련 단원  
 네임스페이스에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [방법: 전역 네임스페이스 별칭 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [방법: My 네임스페이스 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)   
 [:: 연산자](../Topic/::%20Operator%20\(C%23%20Reference\).md)   
 [. 연산자](../../../csharp/language-reference/operators/member-access-operator.md)