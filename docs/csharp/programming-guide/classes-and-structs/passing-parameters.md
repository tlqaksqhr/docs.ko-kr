---
title: "매개 변수 전달(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인수[C#]"
  - "C# 언어, 메서드 매개 변수"
  - "메서드[C#], 매개 변수 전달"
  - "매개 변수[C#], 전달"
  - "매개 변수 전달[C#]"
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 매개 변수 전달(C# 프로그래밍 가이드)
C\#에서는 인수를 값이나 참조로 매개 변수에 전달할 수 있습니다.  참조로 전달하면 함수 멤버, 메서드, 속성, 인덱서, 연산자 및 생성자에서 매개 변수 값을 변경하고 그 변경 내용을 호출 환경에서 유지할 수 있습니다.  참조로 매개 변수를 전달하려면 `ref` 또는 `out` 키워드를 사용하는데,  편의상 이 항목의 예제에서는 `ref` 키워드만 사용합니다.  `ref` 및 `out`의 차이점에 대한 자세한 내용은 [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) 및 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하십시오.  
  
 다음 예제에서는 값과 참조 매개 변수 간의 차이점을 보여 줍니다.  
  
 [!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [값 형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [참조 형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)