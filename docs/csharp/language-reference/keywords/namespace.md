---
title: "namespace(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "namespace_CSharpKeyword"
  - "namespace"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "namespace 키워드[C#]"
  - "범위[C#]"
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# namespace(C# 참조)
`namespace` 키워드를 사용 하 여 관련된 개체 집합이 포함 된 범위를 선언 합니다.  네임 스페이스 코드 요소를 구성 하 고 전역적으로 고유한 형식을 만들 수 있습니다.  
  
 [!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/csharp/namespace_1.cs)]  
  
## 설명  
 네임스페이스 내에서 아래와 같은 형식을 하나 이상 선언할 수 있습니다.  
  
-   기타 네임스페이스  
  
-   [클래스](../../../csharp/language-reference/keywords/class.md)  
  
-   [인터페이스](../../../csharp/language-reference/keywords/interface.md)  
  
-   [struct](../../../csharp/language-reference/keywords/struct.md)  
  
-   [enum](../../../csharp/language-reference/keywords/enum.md)  
  
-   [대리자\(delegate\)](../../../csharp/language-reference/keywords/delegate.md)  
  
 C\# 소스 파일에 네임스페이스를 명시적으로 선언하든 그렇지 않든 관계없이 컴파일러에서는 기본 네임스페이스를 추가합니다.  명명되지 않은 이 네임스페이스는 전역 네임스페이스이라고도 하며 모든 파일에 존재합니다.  전역 네임스페이스의 모든 식별자는 명명된 네임스페이스에서 사용할 수 있습니다.  
  
 네임스페이스는 암시적으로 공용 액세스이며 수정할 수는 없습니다.  네임스페이스의 요소에 할당할 수 있는 액세스 한정자에 대한 자세한 내용은 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)를 참조하십시오.  
  
 두 개 이상의 선언에서 네임스페이스를 정의할 수 있습니다.  예를 들어, 다음 예제에서는 두 클래스를 모두 `MyCompany` 네임스페이스의 일부로 정의합니다.  
  
 [!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/csharp/namespace_2.cs)]  
  
## 예제  
 아래 예제에서는 중첩된 네임스페이스에서 정적 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/csharp/namespace_3.cs)]  
  
## 자세한 내용  
 네임스페이스 사용에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [방법: 전역 네임스페이스 별칭 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using](../../../csharp/language-reference/keywords/using.md)