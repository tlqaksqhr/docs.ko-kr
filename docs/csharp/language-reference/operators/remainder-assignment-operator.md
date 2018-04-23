---
title: '%= 연산자(C# 참조)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 864b96dcf16e4756cd0e74a6e02297660e72357e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>%= 연산자(C# 참조)
나머지 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `%=` 대입 연산자를 사용하는 식의 경우  
  
```  
x %= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x % y  
```  
  
 단, `x`가 한 번만 계산됩니다. [% 연산자](../../../csharp/language-reference/operators/remainder-operator.md)는 나누기 후 나머지를 계산하기 위해 숫자 형식에 대해 미리 정의되어 있습니다.  
  
 `%=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [% 연산자](../../../csharp/language-reference/operators/remainder-operator.md)를 오버로드할 수 있습니다([연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
