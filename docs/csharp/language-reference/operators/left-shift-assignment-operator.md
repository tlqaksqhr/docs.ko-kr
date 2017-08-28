---
title: "&lt;&lt;= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
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
ms.openlocfilehash: fd562a538891a5592cc724e74cffb3d086248898
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;= 연산자(C# 참조)
왼쪽 시프트 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음 형태의 식이 있다고 가정합니다.  
  
```  
x <<= y  
```  
  
 이 식은 다음과 같이 계산됩니다.  
  
```  
x = x << y  
```  
  
 단, `x`가 한 번만 계산됩니다. [<< 연산자](../../../csharp/language-reference/operators/left-shift-operator.md)는 `y`로 지정된 비트 수만큼 `x`를 왼쪽으로 이동합니다.  
  
 `<<=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [<< 연산자](../../../csharp/language-reference/operators/left-shift-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

