---
title: "1차원 배열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], 1차원"
  - "1차원 배열[C#]"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# 1차원 배열(C# 프로그래밍 가이드)
다음 예제처럼 5개의 정수를 포함하는 1차원 배열을 선언할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 이 배열에는 `array[0]`에서 `array[4]`까지의 요소가 있습니다.  배열을 생성하고 배열 요소를 기본값으로 초기화하려면 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용합니다.  이 예제에서는 모든 배열 요소를 0으로 초기화합니다.  
  
 같은 방법으로 문자열 요소를 저장하는 배열을 선언할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## 배열 초기화  
 선언 시 배열을 초기화할 수 있으며, 이런 경우 차수는 초기화 목록의 요소 수로 지정되므로 별도로 지정할 필요가 없습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 같은 방법으로 문자열 배열을 초기화할 수 있습니다.  다음은 각 배열 요소를 요일 이름으로 초기화한 문자열 배열 선언의 예입니다.  
  
 [!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 선언 시 배열을 초기화할 경우 다음과 같은 바로 가기를 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 배열 변수를 초기화하지 않고 선언할 수 있지만 이러한 변수에 배열을 할당하려면 `new` 연산자를 사용해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 C\# 3.0에는 암시적으로 형식화된 배열이 도입되었습니다.  자세한 내용은 [암시적으로 형식화된 배열](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)를 참조하십시오.  
  
## 값 형식 및 참조 형식 배열  
 다음 배열 선언을 참조하십시오.  
  
 [!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 이 선언의 결과는 `SomeType`이 값 형식인지 또는 참조 형식인지에 따라 달라집니다.  값 형식인 경우 문에는 요소의 배열 10개가 생성되는데, 각 배열에는 `SomeType` 형식이 있습니다.  `SomeType`이 참조 형식인 경우 선언의 결과로 10개의 요소로 구성된 배열이 생성되며 각 요소는 null 참조로 초기화됩니다.  
  
 값 형식 및 참조 형식에 대한 자세한 내용은 [형식](../../../csharp/language-reference/keywords/types.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Array>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [가변 배열](../../../csharp/programming-guide/arrays/jagged-arrays.md)