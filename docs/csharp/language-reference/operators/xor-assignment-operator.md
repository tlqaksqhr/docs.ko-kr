---
title: ^= 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: b868f2cdbfa8a80f89a12e6194a30154481f0b07
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172375"
---
# <a name="-operator-c-reference"></a>^= 연산자(C# 참조)
배타적 OR 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음 형태의 식이 있다고 가정합니다.  
  
```csharp  
x ^= y  
```  
  
 이 식은 다음과 같이 계산됩니다.  
  
```csharp  
x = x ^ y  
```  
  
 단, `x`가 한 번만 계산됩니다. [^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)는 정수 피연산자에 대한 배타적 비트 OR 연산과 [bool](../../../csharp/language-reference/keywords/bool.md) 피연산자에 대한 배타적 논리 OR 연산을 수행합니다.  
  
 ^= 연산자는 직접 오버로드할 수 없지만 사용자 정의 형식은 [^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)를 오버로드할 수 있습니다([연산자](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
