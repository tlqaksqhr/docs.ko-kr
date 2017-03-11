---
title: "배열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#]"
  - "C# 언어, 배열"
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 33
---
# 배열(C# 프로그래밍 가이드)
배열 데이터 구조에 동일한 형식의 변수를 여러 개 저장할 수 있습니다.  요소의 형식을 지정하여 배열을 선언합니다.  
  
 `type[] arrayName;`  
  
 다음 예제에서는 1차원, 다차원 및 가변 배열을 만듭니다.  
  
 [!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/csharp/index_1.cs)]  
  
## 배열 개요  
 배열에는 다음과 같은 속성이 있습니다.  
  
-   배열은 [1차원](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [다차원](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) 또는 [가변](../../../csharp/programming-guide/arrays/jagged-arrays.md) 배열일 수 있습니다.  
  
-   차원 수와 각 차원의 길이는 배열 인스턴스가 생성될 때 만들어집니다.  이러한 값은 인스턴스의 수명 동안 변경할 수 없습니다.  
  
-   숫자 배열 요소에는 0이, 참조 요소에는 null이 기본값으로 설정됩니다.  
  
-   가변 배열은 배열의 배열이므로, 각 요소는 참조 형식이고 `null`로 초기화됩니다.  
  
-   배열의 인덱스는 0부터 시작합니다. `n`개의 요소가 있는 배열의 인덱스는 `0`부터 `n-1`까지입니다.  
  
-   배열 요소는 배열 형식을 포함하여 모든 형식이 될 수 있습니다.  
  
-   배열 형식은 <xref:System.Array> 추상 기본 형식에서 파생된 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)입니다.  이 형식은 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.Generic.IEnumerable%601>을 구현하므로 C\#의 모든 배열에 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 반복을 사용할 수 있습니다.  
  
## 관련 단원  
  
-   [개체 형식 배열](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [배열에 foreach 사용](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [인수로 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)  
  
-   [Visual C\# 2010 시작](http://go.microsoft.com/fwlink/?LinkId=221214)의 [변수 상세 정보](http://go.microsoft.com/fwlink/?LinkId=221230)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Array Collection Type](http://msdn.microsoft.com/ko-kr/8a9964de-8941-47b1-a3cf-a01bc88db9e8)