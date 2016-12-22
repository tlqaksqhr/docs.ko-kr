---
title: "같음 비교(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "개체 같음[C#]"
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 같음 비교(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 값이 같은지 비교해야 하는 경우가 종종 있습니다.  예를 들어, 두 변수에 포함된 값이 같음을 의미하는 *값 일치* 또는 *동등성*을 테스트하거나  두 변수가 메모리에 있는 동일한 내부 개체를 참조하는지 확인해야 하는 경우가 있습니다.  이 중 두 번째 유형의 일치는 *참조 일치* 또는 *같음*이라고 합니다.  이 항목에서는 두 유형의 일치에 대해 설명하고 자세한 내용을 포함하는 다른 항목에 대한 링크도 제공합니다.  
  
## 참조 일치  
 참조 일치는 두 개체 참조가 동일한 내부 개체를 참조함을 의미합니다.  이러한 일치는 다음 예제에서와 같이 간단한 할당을 통해 발생할 수 있습니다.  
  
 [!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]  
  
 이 코드에서는 두 개체가 만들어지고 대입문 이후 두 참조에서 동일한 개체를 참조합니다.  따라서 두 참조는 참조 일치를 갖습니다.  두 참조가 동일한 개체를 참조하는지 여부를 확인하려면 <xref:System.Object.ReferenceEquals%2A> 메서드를 사용합니다.  
  
 참조 일치라는 개념은 참조 형식에만 적용됩니다.  값 형식 개체의 경우 값 형식 인스턴스가 변수에 할당될 때 값의 복사본이 만들어지기 때문에 참조 일치를 가질 수 없습니다.  따라서 두 unboxed 구조체가 메모리의 동일한 위치를 참조할 수는 없습니다.  또한 <xref:System.Object.ReferenceEquals%2A>를 사용하여 두 값 형식을 비교할 경우 개체에 포함된 값이 모두 동일해도 반환되는 결과는 항상 `false`입니다.  이는 각 변수가 별도의 개체 인스턴스로 boxing되기 때문입니다.  자세한 내용은 [방법: 참조 일치\(같음\) 테스트](../Topic/How%20to:%20Test%20for%20Reference%20Equality%20\(Identity\)%20\(C%23%20Programming%20Guide\).md)를 참조하십시오.  
  
## 값 일치  
 값 일치란 두 개체에 포함된 하나 이상의 값이 동일함을 의미합니다.  [int](../../../csharp/language-reference/keywords/int.md) 또는 [bool](../../../csharp/language-reference/keywords/bool.md) 같은 기본 값 형식의 경우 값이 일치하는지 여부는 간단히 테스트할 수 있습니다.  다음 예제와 같이 [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) 연산자를 사용하면 됩니다.  
  
```c#  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 대부분의 다른 형식에 대해 값 일치를 테스트하려면 해당 형식에서 값 일치가 어떻게 정의되는지 이해해야 하므로 약간 복잡합니다.  여러 필드 또는 속성이 있는 클래스 및 구조체의 경우 일반적으로 값 일치는 모든 필드 또는 속성의 값이 동일함을 의미합니다.  예를 들어 pointA.X가 pointB.X와 일치하고 pointA.Y가 pointB.Y와 일치할 경우 두 `Point` 개체는 동등한 것으로 정의될 수 있습니다.  
  
 그러나 동등성이 형식에 있는 모든 필드의 일치로 정의되어야 하는 것은 아닙니다.  필드의 하위 집합이 동등성의 기준이 될 수도 있습니다.  현재 소유하고 있지 않은 형식을 비교할 경우에는 해당 형식에 대해 동등성이 어떻게 정의되어 있는지 구체적으로 이해해야 합니다.  사용자 지정 클래스 및 구조체의 값 일치를 정의하는 방법에 대한 자세한 내용은 [방법: 형식의 값 일치 정의](../Topic/How%20to:%20Define%20Value%20Equality%20for%20a%20Type%20\(C%23%20Programming%20Guide\).md)를 참조하십시오.  
  
### 부동 소수점 형식의 값 일치  
 이진 컴퓨터에서는 부동 소수점 연산이 정밀하지 않기 때문에 부동 소수점 형식\([double](../../../csharp/language-reference/keywords/double.md) 및 [float](../../../csharp/language-reference/keywords/float.md)\)에 대한 일치 비교에서 문제가 발생할 수 있습니다.  자세한 내용은 <xref:System.Double?displayProperty=fullName> 항목의 설명 단원을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: 참조 일치\(같음\) 테스트](../Topic/How%20to:%20Test%20for%20Reference%20Equality%20\(Identity\)%20\(C%23%20Programming%20Guide\).md)|두 변수가 참조 일치를 갖는지 여부를 확인하는 방법을 설명합니다.|  
|[방법: 형식의 값 일치 정의](../Topic/How%20to:%20Define%20Value%20Equality%20for%20a%20Type%20\(C%23%20Programming%20Guide\).md)|형식의 값 일치에 대한 사용자 지정 정의를 제공하는 방법에 대해 설명합니다.|  
|[C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)|C\# 언어의 중요한 기능 및 C\#에서 .NET Framework를 통해 사용할 수 있는 기능에 대한 자세한 정보의 링크를 제공합니다.|  
|[형식](../../../visual-basic/reference/command-line-compiler/index.md)|C\# 형식 시스템에 대한 정보 및 추가적인 정보에 대한 링크를 제공합니다.|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)