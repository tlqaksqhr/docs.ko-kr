---
title: "제네릭(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 제네릭(generics)"
  - "제네릭[C#]"
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# 제네릭(C# 프로그래밍 가이드)
제네릭이 2.0 버전의 C\# 언어와 CLR\(공용 언어 런타임\)에 추가되었습니다.  제네릭을 통해 .NET Framework에 형식 매개 변수라는 개념이 처음 소개되었습니다. 형식 매개 변수를 사용하면 클라이언트 코드에서 클래스나 메서드를 선언하고 인스턴스화할 때까지 하나 이상의 형식 지정을 연기하는 클래스와 메서드를 디자인할 수 있습니다.  예를 들어, 다음과 같이 제네릭 형식 매개 변수 T를 사용하면 런타임 캐스트나 boxing 작업에 따른 비용이나 위험을 초래하지 않은 채 다른 클라이언트 코드에서 사용 가능한 단일 클래스를 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## 제네릭 개요  
  
-   제네릭 형식을 사용하면 코드 재사용, 형식 안전성 및 성능을 최대화할 수 있습니다.  
  
-   제네릭의 가장 일반적인 용도는 컬렉션 클래스를 만드는 것입니다.  
  
-   .NET Framework 클래스 라이브러리에는 <xref:System.Collections.Generic> 네임스페이스의 여러 가지 새로운 제네릭 컬렉션 클래스가 포함되어 있습니다.  이러한 클래스는 가능한 경우 항상 <xref:System.Collections> 네임스페이스의 <xref:System.Collections.ArrayList> 같은 클래스 대신 사용해야 합니다.  
  
-   고유한 제네릭 인터페이스, 클래스, 메서드, 이벤트 및 대리자를 만들 수 있습니다.  
  
-   특정 데이터 형식의 메서드에만 액세스하도록 제네릭 클래스를 제한할 수 있습니다.  
  
-   리플렉션을 사용하면 런타임에 제네릭 데이터 형식에 사용되는 형식과 관련된 정보를 얻을 수 있습니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [제네릭의 장점](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [제네릭 형식 매개 변수](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [제네릭 인터페이스](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [default 키워드](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md)  
  
-   [C\+\+ 템플릿과 C\# 제네릭의 차이점](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [제네릭 및 리플렉션](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [.NET Framework 클래스 라이브러리의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## C\# 언어 사양  
 자세한 내용은 [C\# 언어 사양](../../../csharp/language-reference/language-specification.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [형식](../../../csharp/programming-guide/types/index.md)   
 [\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)   
 [\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)