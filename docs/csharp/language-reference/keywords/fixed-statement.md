---
title: fixed 문(C# 참조)
ms.date: 04/20/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e1664f508cb861ffa73b800eeb0da3a1f1cdc432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fixed-statement-c-reference"></a>fixed 문(C# 참조)

`fixed` 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다. `fixed` 문은 [unsafe](unsafe.md) 컨텍스트에서만 허용됩니다. `Fixed`를 사용하여 [고정 크기 버퍼](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 만들 수도 있습니다.

`fixed` 문은 관리되는 변수에 대한 포인터를 설정하고 문을 실행하는 동안 해당 변수를 "고정"합니다. 이동 가능한 관리되는 변수에 대한 포인터는 `fixed` 컨텍스트에만 유용합니다. `fixed` 컨텍스트 없는 가비지 수집은 예기치 않게 변수를 재배치할 수 있습니다. C# 컴파일러만 `fixed` 문에서 관리되는 변수에 대한 포인터를 할당할 수 있습니다.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

배열, 문자열, 고정 크기 버퍼 또는 변수의 주소를 사용하여 포인터를 초기화할 수 있습니다. 다음 예제에서는 변수 주소, 배열 및 문자열의 사용을 보여 줍니다. 고정 크기 버퍼에 대한 자세한 내용은 [고정 크기 버퍼](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 참조하세요.

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

여러 개의 포인터가 모두 동일한 형식인 경우 하나의 명령문에서 초기화할 수 있습니다.

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

형식이 다른 포인터를 초기화하려면 다음 예제와 같이 `fixed` 문을 중첩하면 됩니다.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

이 문의 코드를 실행하면 고정된 모든 변수가 고정 해제되고 가비지 수집됩니다. 따라서 `fixed` 문 외부에서 해당 변수를 가리키지 않습니다. `fixed` 명령문 내에서 선언된 변수는 해당 명령문에 범위가 지정되어 다음을 더 쉽게 만듭니다.

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

`fixed` 명령문에서 초기화된 포인터는 읽기 전용 변수입니다. 포인터 값을 수정하려는 경우 두 번째 포인터 변수를 선언하고 수정 해야 합니다. `fixed` 명령문에서 선언된 변수는 을 수정될 수 없습니다.

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


안전하지 않은 모드에서는 가비지 수집되지 않아 고정할 필요가 없는 스택에서 메모리를 할당할 수 있습니다. 자세한 내용은 [stackalloc](stackalloc.md)를 참조하세요.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a>C# 언어 사양

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

 [C# 참조](../index.md)  
 [C# 프로그래밍 가이드](../../programming-guide/index.md)  
 [C# 키워드](index.md)  
 [unsafe](unsafe.md)  
 [고정 크기 버퍼](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
