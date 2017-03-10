---
title: "개체 형식 배열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], 개체"
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 개체 형식 배열(C# 프로그래밍 가이드)
C 및 C\+\+의 경우와 마찬가지로 C\#에서 배열은 실제로는 개체이며, 주소를 지정할 수 있는 인접 메모리 영역이 아닙니다.  <xref:System.Array>는 모든 배열 형식의 추상 기본 형식입니다.  <xref:System.Array>에 있는 속성 및 기타 클래스 멤버를 사용할 수 있습니다.  예를 들어, <xref:System.Array.Length%2A> 속성을 사용하여 배열의 길이를 구할 수 있습니다.  다음 코드에서는 `numbers` 배열의 길이인 `5`를 `lengthOfNumbers`라는 변수에 할당합니다.  
  
 [!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/csharp/arrays-as-objects_1.cs)]  
  
 <xref:System.Array> 클래스에서는 배열의 정렬, 검색 및 복사 등을 위한 여러 가지 유용한 메서드와 속성을 제공합니다.  
  
## 예제  
 이 예제에서는 <xref:System.Array.Rank%2A> 속성을 사용하여 배열의 차수를 표시합니다.  
  
 [!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/csharp/arrays-as-objects_2.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [가변 배열](../../../csharp/programming-guide/arrays/jagged-arrays.md)