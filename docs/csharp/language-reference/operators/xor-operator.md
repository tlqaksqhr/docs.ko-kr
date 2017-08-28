---
title: "^ 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f081dd2979930404639638179444adc05dd462e1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>^ 연산자(C# 참조)
이항 `^` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다. 정수 형식의 경우 `^` 연산자는 해당 피연산자의 배타적 비트 OR 연산자를 계산합니다. `bool` 피연산자의 경우 `^` 연산자는 피연산자의 배타적 논리 OR 연산을 계산합니다. 즉 피연산자 중 정확히 하나가 `true`일 경우에만 결과가 `true`입니다.  
  
## <a name="remarks"></a>설명  
 사용자 정의 형식은 `^` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 이전 예제에서의 `0xf8 ^ 0x3f` 계산은 16진수 값 F8 및 3F에 해당하는 다음 두 이진 값에 대하여 배타적 비트 OR 연산을 처리합니다.  
  
 `1111 1000`  
  
 `0011 1111`  
  
 배타적 OR 연산 결과는 `1100 0111`이며 16진수로 나타내면 C7입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

