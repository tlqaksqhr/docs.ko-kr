---
title: "&amp;= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6dec8de5077c07150ea37b88979e7b59b231d610
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a>&amp;= 연산자(C# 참조)
AND 대입 연산자.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `&=` 대입 연산자를 사용하는 식의 경우  
  
```  
x &= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x & y  
```  
  
 단, `x`가 한 번만 계산됩니다. [& 연산자](../../../csharp/language-reference/operators/and-operator.md)는 정수 피연산자에 대한 비트 논리적 AND 연산과 `bool` 피연산자에 대한 논리적 AND 연산을 수행합니다.  
  
 `&=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 이항 [& 연산자](../../../csharp/language-reference/operators/and-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

