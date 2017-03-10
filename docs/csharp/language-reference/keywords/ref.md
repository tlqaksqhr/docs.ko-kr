---
title: "ref(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "ref_CSharpKeyword"
  - "ref"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "매개 변수[C#], ref"
  - "ref 키워드[C#]"
ms.assetid: b8a5e59c-907d-4065-b41d-95bf4273c0bd
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# ref(C# 참조)
`ref` 키워드는 인수를 값이 아닌 참조로 전달하도록 합니다.  인수를 참조로 전달하는 경우 호출된 메서드의 매개 변수 변경 내용이 호출 메서드에 반영됩니다.  예를 들어 호출자가 로컬 변수 식 또는 배열 요소 액세스 식을 전달하는 경우 호출된 메서드에서 ref 매개 변수가 참조하는 개체를 바꾸면 호출자의 로컬 변수 또는 배열 요소가 새 개체를 참조합니다.  
  
> [!NOTE]
>  참조로 전달의 개념과 참조 형식의 개념을 혼동해서는 안 됩니다.  이 두 개념은 서로 다릅니다.  메서드 매개 변수는 값 형식이든 참조 형식이든 관계없이 `ref`를 통해 수정할 수 있으며,  참조로 전달되는 경우 값 형식은 boxing되지 않습니다.  
  
 `ref` 매개 변수를 사용하려면 다음 예제에 나와 있는 것처럼 메서드 정의와 호출 메서드가 모두 `ref` 키워드를 명시적으로 사용해야 합니다.  
  
 [!code-cs[csrefKeywordsMethodParams#6](../../../csharp/language-reference/keywords/codesnippet/csharp/ref_1.cs)]  
  
 `ref` 매개 변수로 전달하는 인수는 전달 전에 초기화해야 합니다.  이러한 방식은 인수를 전달하기 전에 명시적으로 초기화할 필요가 없는 `out` 매개 변수와는 다릅니다.  자세한 내용은 [out](../../../csharp/language-reference/keywords/out.md)을 참조하세요.  
  
 클래스의 멤버는 `ref` 및 `out`만 다른 서명을 포함할 수 없습니다.  특정 형식의 두 멤버가 하나는 `ref` 매개 변수를 포함하고 다른 하나는 `out` 매개 변수를 포함한다는 것 외에는 차이가 없으면 컴파일러 오류가 발생합니다.  예를 들어 다음 코드는 컴파일되지 않습니다.  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../csharp/language-reference/keywords/codesnippet/csharp/ref_2.cs)]  
  
 그러나 다음 예제에 나와 있는 것처럼 메서드 하나에는 `ref` 또는 `out` 매개 변수가 포함되어 있고 다른 하나에는 값 매개 변수가 포함되어 있으면 오버로드를 수행할 수 있습니다.  
  
 [!code-cs[csrefKeywordsMethodParams#7](../../../csharp/language-reference/keywords/codesnippet/csharp/ref_3.cs)]  
  
 숨기기나 재정의와 같이 서명이 일치해야 하는 다른 상황에서는 `ref` 및 `out`이 서명의 일부가 되며 서로 일치하지 않습니다.  
  
 속성은 변수가 아니라  메서드이며 `ref` 매개 변수로 전달할 수 없습니다.  
  
 배열을 전달하는 방법에 대한 자세한 내용은 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.  
  
 다음과 같은 종류의 메서드에는 `ref` 및 `out` 키워드를 사용할 수 없습니다.  
  
-   [async](../../../csharp/language-reference/keywords/async.md) 한정자를 사용하여 정의하는 비동기 메서드  
  
-   [yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드  
  
## 예제  
 위의 예제에서는 값 형식을 참조로 전달하는 경우의 결과를 보여 줍니다.  `ref` 키워드를 사용하여 참조 형식을 전달할 수도 있습니다.  참조 형식을 참조로 전달하는 경우 호출된 메서드는 참조 매개 변수가 참조하는 호출 메서드의 개체를 바꿀 수 있습니다.  개체의 저장 위치는 참조 매개 변수의 값으로 메서드에 전달됩니다.  매개 변수의 저장 위치에서 값을 변경하여 새 개체를 가리키도록 하면 호출자가 참조하는 저장 위치도 변경됩니다.  다음 예제에서는 참조 형식 인스턴스를 `ref` 매개 변수로 전달합니다.  참조 형식을 값 및 참조로 전달하는 방법에 대한 자세한 내용은 [참조 형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)을 참조하세요.  
  
 [!code-cs[csrefKeywordsMethodParams#8](../../../csharp/language-reference/keywords/codesnippet/csharp/ref_4.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)