---
title: 배열(C# 프로그래밍 가이드)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8d395bcb179650fe29ab0918e7f91f3c8b6197b5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="arrays-c-programming-guide"></a>배열(C# 프로그래밍 가이드)
배열 데이터 구조에 형식이 동일한 변수를 여러 개 저장할 수 있습니다. 요소의 형식을 지정하여 배열을 선언합니다.  
  
 `type[] arrayName;`  
  
 다음 예제에서는 단일 차원, 다차원 및 가변 배열을 만듭니다.  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a>배열 개요  
 배열에는 다음과 같은 속성이 있습니다.  
  
-   배열은 [단일 차원](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [다차원](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) 또는 [가변](../../../csharp/programming-guide/arrays/jagged-arrays.md)일 수 있습니다.  
  
-   차원 수와 각 차원의 길이는 배열 인스턴스를 만들 때 설정됩니다. 이러한 값은 인스턴스의 수명 동안 변경할 수 없습니다.  
  
-   숫자 배열 요소의 기본값은 0으로 설정되고, 참조 요소는 null로 설정됩니다.  
  
-   가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.  
  
-   배열은 0으로 인덱싱됩니다. `n` 요소는 `0`부터 `n-1`로 인덱싱됩니다.  
  
-   배열 요소 형식은 배열 형식을 비롯한 어떤 형식도 될 수 있습니다.  
  
-   배열 형식은 <xref:System.Array> 추상 기본 형식에서 파생된 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)입니다. 이 형식은 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.Generic.IEnumerable%601>을 구현하므로 C#의 모든 배열에서 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 반복을 사용할 수 있습니다.  
  
## <a name="related-sections"></a>관련 단원  
  
-   [개체로 사용되는 배열](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [배열에 foreach 사용](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [인수로 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 [배열 컬렉션 유형](http://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8)
