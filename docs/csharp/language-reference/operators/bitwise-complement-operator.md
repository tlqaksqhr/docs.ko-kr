---
title: "~ 연산자(C# 참조) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
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
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: c7245700f78ff52a98c499d895c7eb2f95efe5b6
ms.contentlocale: ko-kr
ms.lasthandoff: 05/15/2017

---
# <a name="-operator-c-reference"></a>~ 연산자(C# 참조)
`~` 연산자는 피연산자에 대해 비트 보수 연산을 수행하며, 각 비트를 반대로 하는 효과가 있습니다. 비트 보수 연산자는 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 및 [ulong](../../../csharp/language-reference/keywords/ulong.md)에 대해 미리 정의됩니다.  
  
> [!NOTE]
>  또한 `~` 기호는 종료자를 선언하는 데 사용됩니다. 자세한 내용은 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 사용자 정의 형식은 `~` 연산자를 오버로드할 수 있습니다. 자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요. 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)   
 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)
