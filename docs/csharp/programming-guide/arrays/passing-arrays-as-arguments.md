---
title: 배열을 인수로 전달(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315518"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>배열을 인수로 전달(C# 프로그래밍 가이드)
배열을 메서드 매개 변수에 인수로 전달할 수 있습니다. 배열은 참조 형식이므로 메서드를 통해 요소 값을 변경할 수 있습니다.  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a>1차원 배열을 인수로 전달  
 초기화된 1차원 배열을 메서드에 전달할 수 있습니다. 예를 들어 다음 문은 인쇄 메서드에 배열을 보냅니다.  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 다음 코드는 인쇄 메서드의 부분 구현을 보여 줍니다.  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 다음 예제와 같이 한 단계로 새 배열을 초기화하고 전달할 수 있습니다.  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예제에서는 문자열 배열이 초기화되고 문자열에 대한 `PrintArray` 메서드에 인수로 전달됩니다. 메서드가 배열 요소를 표시합니다. 그런 다음, `ChangeArray` 및 `ChangeArrayElement` 메서드가 호출되어 배열 인수를 값으로 전송할 경우 배열 요소의 변경이 허용됨을 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a>다차원 배열을 인수로 전달  
 초기화된 다차원 배열을 1차원 배열 전달과 동일한 방식으로 메서드에 전달합니다.  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 다음 코드는 2차원 배열을 해당 인수로 허용하는 인쇄 메서드의 부분 선언을 보여 줍니다.  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 다음 예제와 같이 한 단계로 새 배열을 초기화하고 전달할 수 있습니다.  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예제에서는 정수의 2차원 배열이 초기화되고 `Print2DArray` 메서드에 전달됩니다. 메서드가 배열 요소를 표시합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [배열](../../../csharp/programming-guide/arrays/index.md)  
 [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [가변 배열](../../../csharp/programming-guide/arrays/jagged-arrays.md)
