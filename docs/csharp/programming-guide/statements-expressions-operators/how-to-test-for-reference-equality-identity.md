---
title: "방법: 참조 일치(같음) 테스트(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "개체 ID[C#]"
  - "참조 같음[C#]"
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# 방법: 참조 일치(같음) 테스트(C# 프로그래밍 가이드)
형식의 참조 일치 비교를 지원하기 위해 사용자 지정 논리를 구현할 필요는 없습니다.  이 비교 기능은 정적 메서드인 <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName>에서 모든 형식에 대해 제공합니다.  
  
 다음 예제에서는 두 변수가 *참조 일치* 관계에 있는지, 즉 두 변수가 메모리에 있는 동일한 개체를 참조하는지 여부를 확인하는 방법을 보여 줍니다.  
  
 또한 이 예제에서는 <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> 가 값 형식에 대해 항상 `false` 를 반환하는 이유와 문자열 일치를 확인하는 데  <xref:System.Object.ReferenceEquals%2A> 를 사용하면 안 되는 이유를 보여 줍니다.  
  
## 예제  
 [!code-cs[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-test-for-referenc_1.cs)]  
  
 공통적인 기본 클래스인 <xref:System.Object?displayProperty=fullName>의 `Equals` 구현에서도 참조 일치 검사를 수행하지만 클래스에서 이 메서드를 재정의할 경우 예기치 않은 결과가 발생할 수도 있으므로 이 메서드는 사용하지 않는 것이 가장 좋은 방법입니다.  같은 기준이 `==` 및 `!=` 연산자에도 적용됩니다.  \=\= 및 `!=` 연산자가 참조 형식에 대해 작동할 경우 기본적으로 참조 일치 검사를 수행하게 됩니다.  그러나 파생 클래스에서 이러한 연산자를 오버로드하여 값 일치 검사를 수행할 수 있습니다.  오류 발생 가능성을 최소화하려면 두 개체가 참조 일치 관계에 있는지 여부를 확인해야 하는 경우에 항상 <xref:System.Object.ReferenceEquals%2A>를 사용하는 것이 가장 좋은 방법입니다.  
  
 동일한 어셈블리 내의 상수 문자열은 항상 런타임에 내부 풀에 추가됩니다.  즉, 각각의 고유한 리터럴 문자열에 대해 인스턴스가 하나만 유지 관리됩니다.  하지만 런타임에서는 런타임에 만들어진 문자열이 내부 풀에 추가되는 것을 보장하거나 서로 다른 어셈블리에 있는 동일한 두 상수 문자열이 내부 풀에 추가되는 것을 보장하지 않습니다.  
  
## 참고 항목  
 [같음 비교](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)