---
title: "/ 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>/ 연산자(C# 참조)
나누기 연산자(`/`)는 두 번째 피연산자로 첫 번째 피연산자를 나눕니다. 모든 숫자 형식에는 미리 정의된 나누기 연산자가 있습니다.  
  
## <a name="remarks"></a>주의  
 사용자 정의 형식은 `/` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). `/` 연산자를 오버로드하면 [/= 연산자](division-assignment-operator.md)를 암시적으로 오버로드합니다.  
  
 두 정수를 나누면 결과는 항상 정수입니다. 예를 들어 7 / 3의 결과는 2입니다. 7 / 3의 나머지를 확인하려면 나머지 연산자([%](../../../csharp/language-reference/operators/modulus-operator.md))를 사용합니다. 유리수나 분수로 몫을 가져오려면 피제수나 제수를 `float` 또는 `double` 형식으로 지정합니다. 다음 예제와 같이 소수점 오른쪽에 숫자를 입력하여 피제수나 제수를 10진수로 표현하는 경우 형식을 암시적으로 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
