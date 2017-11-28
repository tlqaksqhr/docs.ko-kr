---
title: "|= 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aac4fd6016b65daa15da4bd3a414f385edce7c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>|= 연산자(C# 참조)
OR 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `|=` 대입 연산자를 사용하는 식의 경우  
  
```  
x |= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x | y  
```  
  
 단, `x`가 한 번만 계산됩니다. [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)는 정수 피연산자에 대한 비트 논리적 OR 연산과 부울 피연산자에 대한 논리적 OR 연산을 수행합니다.  
  
 `|=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
## <a name="example"></a>예제  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
