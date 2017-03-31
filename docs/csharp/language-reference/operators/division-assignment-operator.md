---
title: "/= 연산자(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: bd9cb025153897c2c9b47a606f0d78d8ea4ad488
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>/= 연산자(C# 참조)
나누기 대입 연산자입니다.  
  
## <a name="remarks"></a>주의  
 다음과 같은 `/=` 대입 연산자를 사용하는 식의 경우  
  
```  
x /= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x / y  
```  
  
 단, `x`가 한 번만 계산됩니다. [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)는 나누기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.  
  
 `/=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 모든 복합 대입 연산자에서 이진 연산자를 암시적으로 오버로드하면 해당하는 복합 대입 연산자가 오버로드됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

