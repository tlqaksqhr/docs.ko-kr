---
title: "제네릭 대리자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "대리자[C#], 제네릭"
  - "제네릭[C#], 대리자"
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 제네릭 대리자(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[대리자](../../../csharp/language-reference/keywords/delegate.md)는 자체 형식 매개 변수를 정의할 수 있습니다.  제네릭 대리자를 참조하는 코드에서는 제네릭 클래스를 인스턴스화하거나 제네릭 메서드를 호출할 때와 마찬가지로 다음 예제와 같이 형식 매개 변수를 지정하여 폐쇄형 구성 형식을 만들 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 C\# 버전 2.0에는 메서드 그룹 변환이라는 새로운 기능이 있습니다. 이 기능은 제네릭 대리자뿐만 아니라 구체적인 대리자에도 적용되며, 이를 통해 위 코드를 다음과 같이 단순화된 구문으로 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 제네릭 클래스 내에 정의된 대리자에서는 클래스 메서드와 마찬가지로 제네릭 클래스 형식 매개 변수를 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 대리자를 참조하는 코드에서는 다음과 같이 포함하는 클래스의 형식 매개 변수를 지정해야 합니다.  
  
 [!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 sender 인수에 강력한 형식을 사용할 수 있고 <xref:System.Object> 사이에서 캐스팅할 필요가 없으므로 제네릭 대리자는 특히 일반적인 디자인 패턴을 기반으로 이벤트를 정의할 때 유용합니다.  
  
 [!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)   
 [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)   
 [제네릭 인터페이스](../../../csharp/programming-guide/generics/generic-interfaces.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [제네릭](../Topic/Generics%20in%20the%20.NET%20Framework.md)