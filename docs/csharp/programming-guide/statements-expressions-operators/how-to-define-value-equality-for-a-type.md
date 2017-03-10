---
title: "방법: 형식의 값 일치 정의(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Equals 메서드[C#], 재정의"
  - "동등성[C#]"
  - "개체 동등성[C#]"
  - "Equals 메서드 재정의[C#]"
  - "값 같음[C#]"
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# 방법: 형식의 값 일치 정의(C# 프로그래밍 가이드)
클래스 또는 구조체를 정의할 경우 해당 형식의 값 일치 또는 동등성에 대한 사용자 지정 정의를 만드는 것이 의미 있는지 여부를 결정하게 됩니다.  일반적으로는 해당 형식의 개체가 특정 유형의 컬렉션에 추가될 것으로 예상되거나 해당 형식의 주 용도가 필드 또는 속성 집합을 저장하는 데 있으면 값 일치를 구현합니다.  값 일치의 정의는 해당 형식의 모든 필드 및 속성에 대한 비교를 기준으로 하거나 하위 집합에 대한 정의를 기반으로 할 수 있습니다.  그러나 어느 경우이든 클래스 및 구조체에 대한 동등성을 구현하려면 다음 5가지 사항이 준수되어야 합니다.  
  
1.  x.`Equals`\(x\)는 `true`를 반환합니다. 이를 반사 속성이라고 합니다.  
  
2.  x.`Equals`\(y\)와 y.`Equals`\(x\)의 반환 값은 같습니다.  이를 대칭 속성이라고 합니다.  
  
3.  \(x.`Equals`\(y\) && y.`Equals`\(z\)\)가 `true`를 반환하는 경우 x.`Equals`\(z\)도 `true`를 반환합니다.  이를 전이 속성이라고 합니다.  
  
4.  x 및 y가 참조하는 개체가 수정되지 않는 한 x.`Equals`\(y\)를 계속 호출해도 같은 값이 반환됩니다.  
  
5.  x.`Equals`\(null\)에서 `false`를 반환합니다.  그러나 null.Equals\(null\)의 경우는 위의 2번째 규칙에 위배되므로 예외가 throw됩니다.  
  
 사용자가 정의한 모든 구조체에는 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 메서드의 <xref:System.ValueType?displayProperty=fullName> 재정의에서 상속한 값 일치의 기본 구현이 있습니다.  이 구현에서는 리플렉션을 사용하여 해당 형식의 모든 public 필드와 속성 및 public이 아닌 필드와 속성을 검사합니다.  이 구현을 통해 올바른 결과를 얻을 수 있기는 하지만 해당 형식에 맞게 직접 작성한 사용자 지정 구현에 비해 느리다는 단점이 있습니다.  
  
 값 일치에 대한 기본적 구현은 클래스와 구조체에서 서로 다릅니다.  그러나 값 일치를 구현하기 위한 기본적 단계는 클래스와 구조체에서 동일합니다.  
  
1.  [가상](../../../csharp/language-reference/keywords/virtual.md) 메서드 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>를 재정합니다.  대부분의 경우 `bool Equals( object obj )` 구현에서는 각 형식에 맞게 <xref:System.IEquatable%601?displayProperty=fullName> 인터페이스를 구현한 `Equals` 메서드를 호출하게 됩니다.  2단계를 참조하십시오.  
  
2.  형식에 맞는 `Equals` 메서드를 제공하여 <xref:System.IEquatable%601?displayProperty=fullName> 인터페이스를 구현합니다.  실질적인 동등성 비교는 이 메서드에서 수행됩니다.  예를 들어, 형식의 필드를 한 개만 비교하거나 두 개 비교하여 일치 여부를 결정하도록 정의할 수 있습니다.  `Equals`에서 예외를 throw하지 마십시오.  클래스의 경우에는 해당 클래스에 선언되어 있는 필드만 이 메서드에서 검사해야 합니다.  기본 클래스에 있는 필드를 검사하려면 `base.Equals`를 호출해야 합니다.  형식이 <xref:System.Object>에서 직접 상속되는 경우에는 이렇게 호출하지 마십시오. <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>의 <xref:System.Object> 구현에서는 참조 일치 검사를 수행합니다.  
  
3.  [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) 및 [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) 연산자를 오버로드합니다. 이 단계는 선택적이지만 권장 사항입니다.  
  
4.  값이 일치하는 두 개체에서 동일한 해시 코드를 생성하도록 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>를 재정의합니다.  
  
5.  "보다 큼" 또는 "보다 작음"의 정의를 지원하려면 형식에 맞게 <xref:System.IComparable%601> 인터페이스를 구현하고 [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 및 [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) 연산자를 오버로드합니다. 이 단계는 선택적입니다.  
  
 다음의 첫 번째 예제에서는 클래스 구현을 보여 주고,  두 번째 예제에서는 구조체 구현을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 클래스\(참조 형식\)의 값 일치를 구현하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-value-equa_1.cs)]  
  
 클래스\(참조 형식\)의 경우 두 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 메서드의 기본 구현에서 값 일치 검사가 아니라 참조 일치 비교를 수행합니다.  구현자가 가상 메서드를 재정의하는 목적은 해당 메서드에 값 일치 구문을 지정하는 데 있습니다.  
  
 `==` 및 `!=` 연산자는 클래스에서 재정의하지 않은 경우에도 해당 클래스와 함께 사용될 수 있습니다.  그러나 기본 동작은 참조 일치 검사를 수행하는 것입니다.  클래스에서 `Equals` 메서드를 재정의한 경우 `==` 및 `!=` 연산자를 오버로드하는 것이 좋지만 오버로드가 반드시 필요한 것은 아닙니다.  
  
## 예제  
 다음 예제에서는 구조체\(값 형식\)의 값 일치를 구현하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-value-equa_2.cs)]  
  
 구조체의 경우 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>의 기본 구현\(<xref:System.ValueType?displayProperty=fullName>에서 재정의한 버전\)에서는 해당 형식의 모든 필드 값을 비교하는 데 리플렉션을 사용하여 값 일치 검사를 수행합니다.  구현자가 구조체에서 가상 메서드 `Equals`를 재정의하는 목적은 값 일치 검사를 수행할 수 있는 보다 효율적인 수단을 제공하고 추가적으로 비교의 기준을 구조체의 필드 또는 속성 하위 집합에 두려는 데 있습니다.  
  
 [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) 및 [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) 연산자는 구조체에서 명시적으로 오버로드하지 않는 한 구조체에 대해 연산을 수행할 수 없습니다.  
  
## 참고 항목  
 [같음 비교](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)