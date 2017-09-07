---
title: "!= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
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
ms.openlocfilehash: 49c5c9668c6b1169220ee4fa0babf167292a9813
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>!= 연산자(C# 참조)
같지 않음 연산자(`!=`)는 피연산자가 같으면 false, 다르면 true를 반환합니다. 문자열과 개체를 포함하여 모든 형식에 대해 같지 않음 연산자가 미리 정의되어 있습니다. 사용자 정의 형식은 `!=` 연산자를 오버로드할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 미리 정의된 값 형식의 경우 같지 않음 연산자(`!=`)는 피연산자의 값이 다르면 true, 같으면 false를 반환합니다. `string`를 제외한 참조 형식의 경우 `!=`은 두 피연산자가 서로 다른 개체를 참조하면 true를 반환합니다. `string` 형식의 경우 `!=`은 문자열의 값을 비교합니다.  
  
 사용자 정의 값 형식은 `!=` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 사용자 정의 참조 형식의 경우도 마찬가지입니다. 하지만 기본적으로 `!=`은 미리 정의된 참조 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 대로 동작합니다. `!=` 연산자가 오버로드되면 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 또한 오버로드되어야 합니다. 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

