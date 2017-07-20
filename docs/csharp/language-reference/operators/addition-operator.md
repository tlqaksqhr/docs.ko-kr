---
title: "+ 연산자(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3c6ef1acc69fed1c43f0a249287ca8819c8f091c
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>+ 연산자(C# 참조)
`+` 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.  
  
## <a name="remarks"></a>주의  
 단항 `+` 연산자는 모든 숫자 형식에 대해 미리 정의됩니다. 숫자 형식에 대한 단항 `+` 연산의 결과는 피연산자의 값입니다.  
  
 이항 `+` 연산자는 숫자 및 문자열 형식에 대해 미리 정의됩니다. 숫자 형식의 경우 +는 두 피연산자의 합계를 계산합니다. 피연산자 중 하나 또는 둘 다가 문자열 형식이면 +는 피연산자의 문자열 표현을 연결합니다.  
  
 대리자 형식도 대리자 연결을 수행하는 이항 `+` 연산자를 제공합니다.  
  
 사용자 정의 형식은 단항 `+` 및 이항 `+` 연산자를 오버로드할 수 있습니다. 정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다. 자세한 내용은 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)   
 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)
