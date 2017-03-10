---
title: "배열을 인수로 전달(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], 인수로 전달"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 배열을 인수로 전달(C# 프로그래밍 가이드)
배열은 메서드 매개 변수의 인수로 전달될 수 있습니다.  배열은 참조 형식이므로 메서드에서 요소의 값을 변경할 수 있습니다.  
  
## 1차원 배열을 인수로 전달  
 초기화된 1차원 배열을 메서드에 전달할 수 있습니다.  예를 들어, 다음 문에서는 인쇄 메서드에 배열을 전달합니다.  
  
 [!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_1.cs)]  
  
 다음 코드 예제에서는 인쇄 메서드의 부분적 구현을 보여 줍니다.  
  
 [!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_2.cs)]  
  
 다음 예제와 같이 새 배열을 초기화하고 전달하는 작업을 한 단계로 처리할 수 있습니다.  
  
 [!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_3.cs)]  
  
## 예제  
  
### 설명  
 다음 예제에서는 문자열 배열이 초기화되어 `PrintArray` 메서드에 문자열 인수로 전달됩니다.  이 메서드는 배열의 요소를 표시합니다.  그런 다음 `ChangeArray` 및 `ChangeArrayElement` 메서드를 호출하여 값으로 배열 인수를 전송해도 배열 요소가 변경되는 것을 방지하지 않음을 보여 줍니다.  
  
### 코드  
 [!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_4.cs)]  
  
## 다차원 배열을 인수로 전달  
 초기화된 다차원 배열을 메서드에 전달하는 방법은 1차원 배열을 전달하는 방법과 동일합니다.  
  
 [!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_5.cs)]  
  
 다음 코드에서는 2차원 배열을 인수로 사용하는 인쇄 메서드의 부분적 선언을 보여 줍니다.  
  
 [!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_6.cs)]  
  
 다음 예제와 같이 새 배열을 초기화하고 전달하는 작업을 한 단계로 처리할 수 있습니다.  
  
 [!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_7.cs)]  
  
## 예제  
  
### 설명  
 다음 예제에서는 2차원 정수 배열이 초기화되어 `Print2DArray` 메서드에 전달됩니다.  이 메서드는 배열의 요소를 표시합니다.  
  
### 코드  
 [!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_8.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [가변 배열](../../../csharp/programming-guide/arrays/jagged-arrays.md)