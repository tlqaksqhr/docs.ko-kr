---
title: "&gt; 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc7c173ecc97bd3ca3b76a92ccbabc0f40062ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a>&gt; 연산자(C# 참조)
모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 크면 `true`를 반환하고 그렇지 않으면 `false`를 반환하는 “보다 큼” 관계 연산자(`>`)를 정의합니다.  
  
## <a name="remarks"></a>설명  
 사용자 정의 형식은 `>` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). `>` 연산자가 오버로드되면 [<](../../../csharp/language-reference/operators/less-than-operator.md) 또한 오버로드되어야 합니다. 이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)
