---
title: unchecked(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: d7a48950b7158be3cd589c20fbfe0661f3c9c5af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="unchecked-c-reference"></a>unchecked(C# 참조)
`unchecked` 키워드는 정수 형식 산술 연산 및 변환에 대한 오버플로 검사를 비활성화하는 데 사용됩니다.  
  
 unchecked 컨텍스트에서 식이 대상 형식의 범위를 벗어난 값을 생성하는 경우 오버플로에 플래그가 지정되지 않습니다. 예를 들어 다음 예제의 계산은 `unchecked` 블록 또는 식에서 수행되므로 결과가 정수에 비해 너무 크다는 사실이 무시되며 `int1`에 -2,147,483,639 값이 할당됩니다.  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 `unchecked` 환경을 제거하면 컴파일 오류가 발생합니다. 식의 모든 항이 상수이기 때문에 컴파일 시간에 오버플로가 검색될 수 있습니다.  
  
 상수가 아닌 항을 포함하는 식은 컴파일 시간 및 런타임에 기본적으로 확인되지 않습니다. checked 환경을 사용하도록 설정하는 방법에 대한 자세한 내용은 [checked](../../../csharp/language-reference/keywords/checked.md)를 참조하세요.  
  
 오버플로를 확인하는 데 시간이 걸리기 때문에 오버플로 위험이 없는 상황에서는 unchecked 코드를 사용하여 성능을 향상할 수 있습니다. 그러나 오버플로가 발생할 가능성이 있는 경우 checked 환경을 사용해야 합니다.  
  
## <a name="example"></a>예  
 이 샘플에서는 `unchecked` 키워드를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [checked](../../../csharp/language-reference/keywords/checked.md)
