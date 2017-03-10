---
title: "제네릭 및 특성(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "특성[C#], 제네릭"
  - "제네릭[C#], 특성"
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# 제네릭 및 특성(C# 프로그래밍 가이드)
제네릭 형식에 특성을 적용하는 방법은 제네릭이 아닌 형식의 경우와 동일합니다.  특성 적용에 대한 자세한 내용은 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 사용자 지정 특성은 형식 인수가 제공되지 않는 제네릭 형식인 개방형 제네릭 형식과 모든 형식 매개 변수에 대해 인수를 제공하는 생성된 폐쇄형 제네릭 형식을 참조하기 위해서만 허용됩니다.  
  
 다음 예제에서는 이 사용자 지정 특성을 사용합니다.  
  
 [!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_1.cs)]  
  
 특성은 열려 있는 제네릭 형식을 참조할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_2.cs)]  
  
 적절한 수의 쉼표를 사용하여 여러 형식 매개 변수를 지정합니다.  이 예제에서 `GenericClass2`에는 두 개의 형식 매개 변수가 있습니다.  
  
 [!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_3.cs)]  
  
 특성은 생성된 닫혀 있는 제네릭 형식을 참조할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_4.cs)]  
  
 특성에서 제네릭 형식 매개 변수를 참조하면 컴파일 타임 오류가 발생합니다.  
  
 [!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_5.cs)]  
  
 제네릭 형식은 <xref:System.Attribute>에서 상속할 수 없습니다.  
  
 [!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_6.cs)]  
  
 <xref:System.Reflection> 메서드를 사용하면 런타임에 제네릭 형식이나 형식 매개 변수에 대한 정보를 얻을 수 있습니다.  자세한 내용은 [제네릭 및 리플렉션](../../../csharp/programming-guide/generics/generics-and-reflection.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../csharp/programming-guide/generics/index.md)   
 [특성](../Topic/Extending%20Metadata%20Using%20Attributes.md)