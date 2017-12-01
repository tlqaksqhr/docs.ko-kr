---
title: "방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8065c10bec737789f13dcbafe147b50eedb9da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)
포인터 간접 참조 연산자를 사용하여 포인터가 가리키는 위치에 있는 변수를 가져올 수 있습니다. 식의 형식은 다음과 같습니다. 여기서 `p`는 포인터 형식입니다.  
  
```  
*p;  
```  
  
 포인터 형식이 아닌 식에서는 단항 간접 참조 연산자를 사용할 수 없습니다. 또한 [void](../../../csharp/language-reference/keywords/void.md) 포인터에는 적용할 수 없습니다.  
  
 [null](../../../csharp/language-reference/keywords/null.md) 포인터에 간접 참조 연산자를 적용할 때의 결과는 구현에 따라 달라집니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 다양한 형식의 포인터를 사용하여 `char` 형식의 변수에 액세스합니다. 변수에 할당되는 물리적 주소가 변경될 수 있으므로 `theChar`의 주소는 실행할 때마다 달라집니다.  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 **TheChar 값 Z =**  
**Address of theChar = 12F718**  
**Value of pChar = Z**   
**Value of pInt = 90**    
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [유형](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
