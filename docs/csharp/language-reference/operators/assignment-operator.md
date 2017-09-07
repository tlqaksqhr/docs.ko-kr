---
title: "= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
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
ms.openlocfilehash: e40b2f221717461443a5d0247b3401eb527a7b5a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>= 연산자(C# 참조)
대입 연산자(`=`)는 왼쪽 피연산자가 나타내는 저장소 위치, 속성 또는 인덱서에 오른쪽 피연산자의 값을 저장하고 그 값을 해당 결과로 반환합니다. 피연산자는 동일한 형식이어야 합니다(또는 오른쪽 피연산자를 왼쪽 피연산자의 형식으로 암시적으로 변환할 수 있어야 함).  
  
## <a name="remarks"></a>설명  
 대입 연산자는 오버로드할 수 없습니다. 그러나 형식에 대한 암시적 변환 연산자를 정의할 수 있으며, 이 연산자를 통해 해당 형식에 대입 연산자를 사용할 수 있습니다. 자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

