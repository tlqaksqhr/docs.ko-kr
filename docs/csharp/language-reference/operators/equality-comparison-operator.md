---
title: == 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: f8356320817771cb559192c1ce720a80bf33bbf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>== 연산자(C# 참조)
미리 정의된 값 형식의 경우 같음 연산자(`==`)는 피연산자의 값이 같으면 true, 같지 않으면 `false`를 반환합니다. [string](../../../csharp/language-reference/keywords/string.md)을 제외한 참조 형식의 경우 `==`은 두 피연산자가 동일한 개체를 참조하면 `true`를 반환합니다. `string` 형식의 경우 `==`은 문자열의 값을 비교합니다.  
  
## <a name="remarks"></a>설명  
 사용자 정의 값 형식은 `==` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 사용자 정의 참조 형식의 경우도 마찬가지입니다. 하지만 기본적으로 `==`은 미리 정의된 참조 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 대로 동작합니다. `==` 연산자가 오버로드되면 [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 또한 오버로드되어야 합니다. 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
