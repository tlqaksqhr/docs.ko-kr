---
title: fixed 문(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a>fixed 문(C# 참조)
`fixed` 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다. `fixed` 문은 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트에서만 허용됩니다. `Fixed`를 사용하여 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 만들 수도 있습니다.  
  
 `fixed` 문은 관리되는 변수에 대한 포인터를 설정하고 문을 실행하는 동안 해당 변수를 "고정"합니다. `fixed`를 사용하지 않으면 가비지 수집에서 변수를 예기치 않게 재배치할 수 있으므로 이동 가능한 관리되는 변수에 대한 포인터가 거의 사용되지 않습니다. C# 컴파일러만 `fixed` 문에서 관리되는 변수에 대한 포인터를 할당할 수 있습니다.  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 배열, 문자열, 고정 크기 버퍼 또는 변수의 주소를 사용하여 포인터를 초기화할 수 있습니다. 다음 예제에서는 변수 주소, 배열 및 문자열의 사용을 보여 줍니다. 고정 크기 버퍼에 대한 자세한 내용은 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 참조하세요.  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 모두 동일한 형식인 경우 여러 포인터를 초기화할 수 있습니다.  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 형식이 다른 포인터를 초기화하려면 다음 예제와 같이 `fixed` 문을 중첩하면 됩니다.  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 이 문의 코드를 실행하면 고정된 모든 변수가 고정 해제되고 가비지 수집됩니다. 따라서 `fixed` 문 외부에서 해당 변수를 가리키지 않습니다.  
  
> [!NOTE]
>  fixed 문에서 초기화된 포인터는 수정할 수 없습니다.  
  
 안전하지 않은 모드에서는 가비지 수집되지 않아 고정할 필요가 없는 스택에서 메모리를 할당할 수 있습니다. 자세한 내용은 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
