---
title: "++ 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6deb2f772fefc93020e7eaaed6be35e48b11df7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>++ 연산자(C# 참조)
증가 연산자(`++`)는 피연산자를 1씩 증가합니다. 증가 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다( `++variable` 및 `variable++`).  
  
## <a name="remarks"></a>설명  
 첫 번째 형태는 전위 증가 연산입니다. 연산 결과는 증가된 후의 피연산자 값입니다.  
  
 두 번째 형태는 후위 증가 연산입니다. 연산 결과는 증가되기 전의 피연산자 값입니다.  
  
 숫자 및 열거형 형식에는 미리 정의된 증가 연산자가 있습니다. 사용자 정의 형식은 `++` 연산자를 오버로드할 수 있습니다. 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
