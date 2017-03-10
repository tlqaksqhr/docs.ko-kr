---
title: "struct(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "struct_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "struct 키워드[C#]"
  - "구조체[C#], struct 키워드"
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# struct(C# 참조)
`struct` 형식은 인벤토리의 항목 특성이나 사각형의 좌표와 같은 관련 변수의 소규모 그룹을 캡슐화하는 데 일반적으로 사용되는 값 형식입니다.  다음 예제에서는 간단한 구조체 선언을 보여줍니다.  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## 설명  
 구조체는 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md), [상수](../../../csharp/programming-guide/classes-and-structs/constants.md), [필드](../../../csharp/programming-guide/classes-and-structs/fields.md), [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md), [속성](../../../csharp/programming-guide/classes-and-structs/properties.md), [인덱서](../../../csharp/programming-guide/indexers/index.md), [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [이벤트](../../../csharp/programming-guide/events/index.md) 및 [중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)도 포함할 수 있습니다. 그러나 이러한 멤버가 여러 개 필요한 경우에는 구조체 대신 클래스 형식을 지정하는 것이 좋습니다.  
  
 예제를 보려면 [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)을 참조하십시오.  
  
 구조체는 인터페이스를 구현할 수는 있지만 다른 구조체를 상속할 수는 없습니다.  그러므로 구조체 멤버를 `protected`로 선언할 수는 없습니다.  
  
 자세한 내용은 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)을 참조하십시오.  
  
## 예제  
 예제와 자세한 내용은 [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)을 참조하세요.  
  
## C\# 언어 사양  
 예제를 보려면 [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)   
 [클래스](../../../csharp/language-reference/keywords/class.md)   
 [interface](../../../csharp/language-reference/keywords/interface.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)