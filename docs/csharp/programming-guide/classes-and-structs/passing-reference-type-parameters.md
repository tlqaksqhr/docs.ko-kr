---
title: "참조 형식 매개 변수 전달(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "메서드 매개 변수[C#], 참조 형식"
  - "매개 변수[C#], 참조"
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# 참조 형식 매개 변수 전달(C# 프로그래밍 가이드)
[참조 형식](../../../csharp/language-reference/keywords/reference-types.md) 변수는 데이터를 직접 포함하지 않고 데이터에 대한 참조를 포함합니다.  값으로 참조\-형식 매개 변수를 전달할 경우 클래스 멤버 값과 같은 참조에서 가리키는 데이터를 변경할 수 있으나  참조 값 자체를 변경할 수는 없습니다. 즉, 같은 참조를 사용하여 새 클래스에 메모리를 할당하고 이를 블록 밖에서 지속하도록 할 수 없습니다.  그렇게 하려면 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out.md) 키워드를 사용하여 매개 변수를 전달해야 합니다.  편의상 다음 예제에서는 `ref`를 사용합니다.  
  
## 값으로 참조 형식 전달  
 다음 예제에서는 참조\-형식 매개 변수 `arr`를 값으로 `Change` 메서드에 전달하는 것에 대해 설명합니다.  매개 변수가 `arr`에 대한 참조이므로 배열 요소 값을 변경할 수 있습니다.  그러나 다른 메모리 위치에 매개 변수를 다시 할당하는 것은 메서드 안에서만 가능하며 원래 변수 `arr`에 영향을 주지는 않습니다.  
  
 [!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]  
  
 이전 예제에서 참조 형식인 `arr` 배열은 `ref` 매개 변수 없이 메서드에 전달됩니다.  이러한 경우 `arr`를 가리키는 참조의 복사본이 메서드로 전달됩니다.  출력은 메서드로 배열 요소 내용\(이 경우 `1`부터 `888`까지\)을 변경할 수 있음을 보여 줍니다.  그러나, `Change` 메서드 안에서 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 메모리 일부를 새로 할당하면 변수 `pArray`은 새 배열을 참조하게 됩니다.  따라서 이후의 모든 변경 사항은 `Main`에서 만들어진 원본 배열 `arr`에 영향을 주지 않습니다.  실제로 이 예제에서 두 개의 배열이 만들어지는데, 하나는 `Main` 안에서 다른 하나는 `Change` 메서드 안에서 만들어집니다.  
  
## 참조로 참조 형식 전달  
 다음 예제에서는 제외 하 고 이전 예제와 동일은 `ref` 키워드는 메서드 헤더와 호출에 추가 됩니다.  메서드에서 변수 변경 호출 프로그램에서 원래 변수에 영향을 줍니다.  
  
 [!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]  
  
 메서드에서의 모든 변경 사항은 `Main`의 원본 배열에 영향을 줍니다.  실제로 `new` 연산자를 사용하여 원본 배열을 다시 할당합니다.  따라서, `Change` 메서드를 호출한 후 `arr`에 대한 모든 참조는 `Change` 메서드에서 만들어진 다섯 요소 배열을 가리킵니다.  
  
## 두 문자열 맞바꾸기  
 문자열 맞바꾸기는 참조로 참조\-형식 매개 변수를 전달하는 좋은 예입니다.  예제에서 두 문자열 `str1`과 `str2`는 `Main`에서 초기화되고 `ref` 키워드에 의해 한정된 매개 변수로 `SwapStrings` 메서드에 전달됩니다.  두 문자열은 메서드와 `Main`에서 맞바뀝니다.  
  
 [!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]  
  
 이 예제에서 호출 프로그램의 변수에 영향을 주려면 참조로 매개 변수를 전달해야 합니다.  메서드 헤더와 메서드 호출 모두에서 `ref` 키워드를 제거하면 호출 프로그램에서 아무것도 변경되지 않습니다.  
  
 문자열에 대한 자세한 내용은 [문자열](../../../csharp/language-reference/keywords/string.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)