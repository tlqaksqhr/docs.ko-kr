---
title: "/ 연산자(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 387be8c240001557722b4a30b785637c72c9be37
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>/ 연산자(C# 참조)
나누기 연산자(`/`)는 두 번째 피연산자로 첫 번째 피연산자를 나눕니다. 모든 숫자 형식에는 미리 정의된 나누기 연산자가 있습니다.  
  
## <a name="remarks"></a>주의  
 사용자 정의 형식은 `/` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). `/` 연산자를 오버로드하면 [/= 연산자](division-assignment-operator.md)를 암시적으로 오버로드합니다.  
  
 두 정수를 나누면 결과는 항상 정수입니다. 예를 들어 7 / 3의 결과는 2입니다. 7 / 3의 나머지를 확인하려면 나머지 연산자([%](../../../csharp/language-reference/operators/modulus-operator.md))를 사용합니다. 유리수나 분수로 몫을 가져오려면 피제수나 제수를 `float` 또는 `double` 형식으로 지정합니다. 다음 예제와 같이 소수점 오른쪽에 숫자를 입력하여 피제수나 제수를 10진수로 표현하는 경우 형식을 암시적으로 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

