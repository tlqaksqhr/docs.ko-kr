---
title: 기본값 식(C# 프로그래밍 가이드)
description: 기본값 식은 참조 형식 또는 값 형식에 대해 기본값을 생성합니다.
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: be51ad253a2939f538144caf4500f39e144c1664
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336803"
---
# <a name="default-value-expressions-c-programming-guide"></a>기본값 식(C# 프로그래밍 가이드)

기본값 식 `default(T)`은 형식 `T`의 기본값을 생성합니다. 다음 표에서는 다양한 형식에 대해 생성되는 값을 보여줍니다.

|형식|기본값|
|---------|---------|
|임의 참조 형식|`null`|
|숫자 값 형식|0|
|[bool](../../language-reference/keywords/bool.md)|`false`|
|[char](../../language-reference/keywords/char.md)|`'\0'`|
|[enum](../../language-reference/keywords/enum.md)|식 `(E)0`로 생성한 값이며 여기서 `E`는 열거형 식별자입니다.|
|[struct](../../language-reference/keywords/struct.md)|모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.|
|nullable 형식|<xref:System.Nullable%601.HasValue%2A> 속성은 `false`이고 <xref:System.Nullable%601.Value%2A> 속성은 정의되지 않은 인스턴스입니다.|

기본값 식은 특히 제네릭 클래스와 메서드에서 유용합니다. 제네릭 사용으로 발생하는 한 가지 문제는 다음과 같은 내용을 미리 알지 못하는 경우 매개 변수가 있는 형식 `T`에 기본값을 할당하는 방법입니다.

- `T`가 참조 형식인지 값 형식인지 여부
- `T`이 값 형식인 경우 숫자 값인지 구조체인지 여부를 표시합니다.

 매개 변수가 있는 형식 `T`의 변수 `t`가 제공되었을 때 `t = null` 문은 `T`가 참조 형식인 경우에만 유효합니다. 할당 `t = 0`은 숫자 값 형식에만 작동하고 구조체에는 작동하지 않습니다. 이를 해결하려면 기본값 식을 사용합니다.

```csharp
T t = default(T);
```

`default(T)` 식은 제네릭 클래스와 메서드로 제한되지 않습니다. 기본값 식은 모든 관리되는 형식과 사용할 수 있습니다. 이러한 식은 유효합니다.

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 `GenericList<T>` 클래스에 있는 다음 예제에서는 제네릭 클래스에서 `default(T)` 연산자를 사용하는 방법을 보여 줍니다. 자세한 내용은 [제네릭 소개](../generics/introduction-to-generics.md)를 참조하세요.

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>기본 리터럴 및 형식 유추

C# 7.1부터 컴파일러에서 식의 형식을 유추할 수 있을 때 기본값 식에 대해 `default` 리터럴을 사용할 수 있습니다. `default` 리터럴은 `T`가 유추된 형식인 경우 해당 `default(T)`와 동일한 값을 생성합니다. 그러면 형식 선언의 중복성을 두 번 이상 줄여 코드가 더 간결해집니다. `default` 리터럴은 다음 위치에서 사용할 수 있습니다.

- 변수 이니셜라이저
- 변수 대입
- 선택적 매개 변수의 기본값 선언
- 메서드 호출 인수에 대한 값 제공
- 문(또는 식 본문 멤버의 식) 반환

다음 예제에서는 기본값 식에서 많은 `default` 리터럴 사용을 보여 줍니다.

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>참고 항목

 <xref:System.Collections.Generic>  
 [C# 프로그래밍 가이드](../index.md)  
 [제네릭(C# 프로그래밍 가이드)](../generics/index.md)  
 [제네릭 메서드](../generics/generic-methods.md)  
 [.NET의 제네릭](~/docs/standard/generics/index.md)  
 [기본값 표](../../language-reference/keywords/default-values-table.md)
