---
title: ++ 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: 0fe1150ca7267d02feeab33168eab7f79734c2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275066"
---
# <a name="-operator-c-reference"></a>++ 연산자(C# 참조)
증가 연산자(`++`)는 피연산자를 1씩 증가합니다. 증가 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다( `++variable` 및 `variable++`).  
  
## <a name="remarks"></a>설명  
 첫 번째 형태는 전위 증가 연산입니다. 연산 결과는 증가된 후의 피연산자 값입니다.  
  
 두 번째 형태는 후위 증가 연산입니다. 연산 결과는 증가되기 전의 피연산자 값입니다.  
  
 숫자 및 열거형 형식에는 미리 정의된 증가 연산자가 있습니다. 사용자 정의 형식은 `++` 연산자를 오버로드할 수 있습니다. 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
