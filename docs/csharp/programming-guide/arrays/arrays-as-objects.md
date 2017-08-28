---
title: "개체 형식 배열(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 396d0df9196b7331e94127730b83782ffc8ea593
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-as-objects-c-programming-guide"></a>개체 형식 배열(C# 프로그래밍 가이드)
C#의 배열은 C 및 C++와 같이 인접한 메모리의 주소 지정 가능한 영역이 아니라 실제로 개체입니다. <xref:System.Array>는 모든 배열 형식의 추상 기본 형식입니다. <xref:System.Array>에 포함된 속성 및 다른 클래스 멤버를 사용할 수 있습니다. 이러한 예로 <xref:System.Array.Length%2A> 속성을 사용하여 배열의 길이를 가져오는 경우가 있습니다. 다음 코드에서는 `numbers` 배열의 길이(`5`)를 `lengthOfNumbers`라는 변수에 할당합니다.  
  
 [!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 <xref:System.Array> 클래스는 배열의 정렬, 검색 및 복사를 위한 다른 여러 유용한 메서드와 속성을 제공합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 <xref:System.Array.Rank%2A> 속성을 사용하여 배열의 차원 수를 표시합니다.  
  
 [!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [가변 배열](../../../csharp/programming-guide/arrays/jagged-arrays.md)

