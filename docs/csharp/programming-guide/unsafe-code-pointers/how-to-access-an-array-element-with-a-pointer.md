---
title: "방법: 포인터로 배열 요소 액세스(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
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
ms.openlocfilehash: 73f14aba63b7f7677a889f18cc1b410e3ecf1438
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a>방법: 포인터로 배열 요소 액세스(C# 프로그래밍 가이드)
안전하지 않은 컨텍스트에서는 다음 예제와 같이 포인터 요소 액세스를 사용하여 메모리의 요소에 액세스할 수 있습니다.  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 대괄호 안의 식은 암시적으로 `int`, `uint`, `long` 또는 `ulong`으로 변환할 수 있어야 합니다. p[e] 연산은 *(p+e)와 동일합니다. C 및 C++와 마찬가지로 포인터 요소 액세스에서는 범위 이탈 오류를 검사하지 않습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 123개의 메모리 위치가 문자 배열 `charPointer`에 할당됩니다. 이 배열은 두 개의 [for](../../../csharp/language-reference/keywords/for.md) 루프에서 소문자와 대문자를 표시하는 데 사용됩니다.  
  
 `charPointer[i]` 식은 `*(charPointer + i)` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.  
  
 [!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 **대문자:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**소문자:**  
**abcdefghijklmnopqrstuvwxyz**   
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

