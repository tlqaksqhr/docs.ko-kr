---
title: '*= 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 465cf37d38a989d5c1bf6f0d0242c295e55684f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>*= 연산자(C# 참조)
이항 곱하기 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `*=` 대입 연산자를 사용하는 식의 경우  
  
```  
x *= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x * y  
```  
  
 단, `x`가 한 번만 계산됩니다. [* 연산자](../../../csharp/language-reference/operators/multiplication-operator.md)는 곱하기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.  
  
 `*=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [* 연산자](../../../csharp/language-reference/operators/multiplication-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
