---
title: "방법: 변수의 주소 가져오기(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>방법: 변수의 주소 가져오기(C# 프로그래밍 가이드)
고정 변수로 계산되는 단항 식의 주소를 가져오려면 address-of 연산자를 사용합니다.  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 address-of 연산자는 변수에만 적용할 수 있습니다. 변수가 이동 가능한 변수인 경우 해당 주소를 가져오기 전에 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)을 사용하여 일시적으로 변수를 고정할 수 있습니다.  
  
 변수가 초기화되었는지 확인해야 합니다. 변수가 초기화되지 않은 경우 컴파일러가 오류 메시지를 실행하지 않습니다.  
  
 상수 또는 값의 주소를 가져올 수 없습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `int`에 대한 포인터인 `p`가 선언되고 정수 변수 `number`의 주소가 할당됩니다. `number` 변수는 *p에 대한 할당 결과로 초기화됩니다. 이 대입문을 주석으로 설정하면 `number` 변수의 초기화가 제거되지만 컴파일 시간 오류가 발생하지 않습니다. [멤버 액세스](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) 연산자 `->`을 사용하여 포인터에 저장된 주소를 가져오고 표시합니다.  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [유형](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
