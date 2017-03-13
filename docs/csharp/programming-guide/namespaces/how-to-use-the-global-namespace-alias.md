---
title: "방법: 전역 네임스페이스 별칭 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "별칭[C#]"
  - "전역 네임스페이스[C#]"
  - "네임스페이스[C#], 전역 네임스페이스 한정자"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# 방법: 전역 네임스페이스 별칭 사용(C# 프로그래밍 가이드)
전역 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md)의 멤버에 액세스할 수 있다는 점은 멤버가 이름이 동일한 다른 엔터티에 의해 숨겨질 수 있는 경우에 유용합니다.  
  
 예를 들어, 다음 코드에서 `Console`은 <xref:System> 네임스페이스의 `Console` 형식 대신 `TestApp.Console`로 해석됩니다.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 `System` 네임스페이스가 `TestApp.System` 클래스에 의해 숨겨져 있으므로 `System.Console`을 사용해도 여전히 오류가 발생합니다.  
  
 [!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 그러나 다음과 같이 `global::System.Console`을 사용하여 이 오류를 해결할 수 있습니다.  
  
 [!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 왼쪽 식별자가 `global`이면 오른쪽 식별자에 대한 검색이 전역 네임스페이스에서 시작됩니다.  예를 들어, 다음 선언에서는 `TestApp`를 전역 공간의 멤버로 참조합니다.  
  
 [!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 `System`이라는 자체 네임스페이스는 만들지 않는 것이 좋으며, 이러한 네임스페이스를 만드는 코드는 거의 찾아볼 수 없습니다.  그러나 보다 큰 프로젝트에서는 여러 가지 형태의 네임스페이스 중복이 발생할 수 있습니다.  이러한 경우 전역 네임스페이스 한정자를 사용하면 확실하게 루트 네임스페이스를 지정할 수 있습니다.  
  
## 예제  
 이 예제에서는 `TestClass` 클래스가 `System` 네임스페이스에 포함되므로 `System` 네임스페이스에 의해 숨겨져 있는 `System.Console` 클래스를 참조하려면 `global::System.Console`을 사용해야 합니다.  또한 `System.Collections` 네임스페이스를 참조하기 위해 별칭 `colAlias`가 사용되고 있으므로 <xref:System.Collections.Hashtable?displayProperty=fullName>의 인스턴스는 네임스페이스 대신 이 별칭을 사용하여 생성됩니다.  
  
 [!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
  **A 1**  
**B 2**  
**C 3**   
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)   
 [. 연산자](../../../csharp/language-reference/operators/member-access-operator.md)   
 [:: 연산자](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)