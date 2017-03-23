---
title: "가변 배열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], 가변"
  - "가변 배열[C#]"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# 가변 배열(C# 프로그래밍 가이드)
가변 배열의 요소에는 배열이 사용됩니다.  따라서 가변 배열의 요소는 다양한 차원과 크기를 가질 수 있습니다.  가변 배열을 "배열의 배열"이라고도 합니다. 다음 예제에서는 가변 배열을 선언 및 초기화하고 가변 배열에 액세스하는 방법을 보여 줍니다.  
  
 다음은 3개의 요소를 가진 1차원 배열의 선언입니다. 이 배열의 각 요소는 1차원 정수 배열입니다.  
  
 [!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 `jaggedArray`를 사용하려면 먼저 요소를 초기화해야 합니다.  다음과 같이 요소를 초기화할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 각 요소는 1차원 정수 배열입니다.  첫째 요소는 5개의 정수, 둘째 요소는 4개의 정수, 셋째 요소는 2개의 정수를 갖는 배열입니다.  
  
 초기 값을 사용하여 배열 요소를 값으로 채울 수도 있습니다. 이 경우 배열 크기를 지정할 필요가 없습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 또한 다음 예제처럼 선언 시에 배열을 초기화할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 다음과 같은 약식 표기를 사용할 수 있습니다.  요소에 대한 기본 초기화가 없으므로 요소 초기화에서 `new` 연산자를 생략할 수 없다는 사실에 주의해야 합니다.  
  
 [!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 가변 배열은 배열의 배열이므로, 각 요소는 참조 형식이고 `null`로 초기화됩니다.  
  
 다음 예제처럼 개별 배열 요소에 액세스할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 가변 배열과 다차원 배열을 함께 사용할 수 있습니다.  다음은 서로 다른 크기의 세 개의 2차원 배열 요소를 갖는 1차원 가변 배열의 선언 및 초기화입니다.  2차원 배열에 대한 자세한 내용은 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)을 참조하십시오.  
  
 [!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 첫째 배열의 `[1,0]` 요소 값\(값 `5`\)을 표시하는 다음 예제처럼 개별 요소에 액세스할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 `Length` 메서드는 가변 배열에 포함된 배열의 수를 반환합니다.  예를 들어, 앞의 예제에서와 같은 배열을 선언한 경우를 가정해 볼 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 값 3을 반환합니다.  
  
## 예제  
 이 예제에서는 배열을 요소로 사용하는 배열을 만듭니다.  배열 요소 각각은 다른 크기입니다.  
  
 [!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## 참고 항목  
 <xref:System.Array>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)