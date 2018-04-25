---
title: '* 연산자(C# 참조)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 07d06d668ba43ebc3f4fae394d7b6641b122f4a6
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>* 연산자(C# 참조)
곱하기 연산자(`*`)는 피연산자의 곱을 계산합니다. 모든 숫자 형식에는 곱하기 연산자가 미리 정의되어 있습니다.  

`*`는 역참조 연산자로 사용되어 포인터를 읽고 쓸 수도 있습니다.
  
## <a name="remarks"></a>설명  
 `*` 연산자는 포인터 형식의 선언과 포인터의 역참조에도 사용됩니다. 이 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드로 표시되었으며 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션이 필요한 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.  역참조 연산자를 간접 참조 연산자라고도 합니다.  
  
 사용자 정의 형식으로 이항 `*` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
