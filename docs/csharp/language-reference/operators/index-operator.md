---
title: '[] 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 65908bb3bcd8912ef81fc094e5958ae8dc4ae1f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>[] 연산자(C# 참조)
대괄호(`[]`)는 배열, 인덱서 및 특성에 사용됩니다. 포인터에 사용할 수도 있습니다.  
  
## <a name="remarks"></a>설명  
 배열 형식은 뒤에 `[]`가 오는 형식입니다.  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 배열의 요소에 액세스하려면 원하는 요소의 인덱스를 대괄호로 묶습니다.  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 배열 인덱스가 범위를 벗어나면 예외가 throw됩니다.  
  
 배열 인덱싱 연산자를 오버로드할 수는 없습니다. 그러나 형식에서 하나 이상의 매개 변수를 사용하는 속성 및 인덱서를 정의할 수 있습니다. 인덱서 매개 변수는 배열 인덱스와 마찬가지로 대괄호에 묶여 있지만 인덱서 매개 변수는 정수여야 하는 배열 인덱스와 달리 임의 형식으로 선언할 수 있습니다.  
  
 예를 들어 .NET Framework에서는 임의 형식의 키와 값을 연결하는 `Hashtable` 형식을 정의합니다.  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 대괄호는 [특성](../../../csharp/programming-guide/concepts/attributes/index.md)을 지정하는 데에도 사용됩니다.  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 대괄호를 사용하여 포인터를 인덱싱할 수 있습니다.  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 범위 검사는 수행되지 않습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)  
 [배열](../../../csharp/programming-guide/arrays/index.md)  
 [인덱서](../../../csharp/programming-guide/indexers/index.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)
