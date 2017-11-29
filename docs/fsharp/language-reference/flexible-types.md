---
title: "유연한 형식(F#)"
description: "F # 유연한 형식의 주석을 매개 변수, 변수 또는 값에는 지정 된 형식과 호환 되는 형식을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a>유연한 형식

A *유연한 형식 주석* 매개 변수, 변수 또는 값 클래스 또는 인터페이스의 개체 지향 계층에서 위치에 따라 호환성 결정 되는 지정 된 형식과 호환 되는 형식에 있음을 나타냅니다. 유연한 형식을 사용 특히 형식 계층에서 더 높은 형식으로 자동 변환이 발생 하지 않습니다는 계층 구조의 형식으로 또는 인터페이스를 구현 하는 모든 형식을 사용 하 여 기능을 사용 하도록 설정 하려면.

## <a name="syntax"></a>구문

```fsharp
#type
```

## <a name="remarks"></a>설명

위 구문에서 *형식* 기본 형식 또는 인터페이스를 나타냅니다.

유연한 형식에 허용 되는 형식과 기본 또는 인터페이스 형식과 호환 되는 형식으로 제한 하는 제약 조건이 있는 제네릭 형식을 하는 것과 같습니다. 즉, 다음 두 줄의 코드는 동일 합니다.

```fsharp
#SomeType

'T when 'T :> SomeType
```

유연한 형식은 여러 가지 상황에서에서 유용 합니다. 예를 들어, 고차 함수 (함수를 인수로 사용 하는 함수)을 사용 하는 경우 유용 종종 유연한 형식을 반환 하는 함수입니다. 다음 예제에 시퀀스 인수가 있는 유연한 형식을 사용 하 여 `iterate2` 시퀀스, 배열, 목록 및 기타 열거 가능한 형식을 생성 하는 함수를 사용 하 여 고차 함수를 사용 하도록 설정 합니다.

유연한 형식은 다른 반환 순서는 반환, 하나는 다음 두 가지 기능을 고려 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

또 다른 예로 [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) 라이브러리 함수:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

이 함수에 있는 다음 열거 가능한 시퀀스를 전달할 수 있습니다.

- 목록의 목록
- 배열 목록
- 목록의 배열
- 시퀀스의 배열
- 열거 가능한 시퀀스의 다른 조합

다음 코드에서는 `Seq.concat` 유연한 형식을 사용 하 여 지원할 수 있는 시나리오를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

출력은 다음과 같습니다.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

F #에서 다른 개체 지향 언어와 마찬가지로 없는 컨텍스트는 파생된 형식 또는 인터페이스를 구현 하는 형식을 자동으로 변환 된 기본 형식 또는 인터페이스 형식입니다. 이러한 자동 변환의 형식은 형식 인수 또는 반환 형식이 함수 형식인 같은 보다 복잡 한 형식의 일부로 종속 된 위치에 때가 아니라 하지만 직접 인수를 발생 합니다. 따라서 되 게 적용 하는 형식을 더 복잡 한 유형의 일부인 경우 유연한 형식 표기법은 주로 유용 합니다.

## <a name="see-also"></a>참고 항목

[F# 언어 참조](index.md)

[제네릭](generics/index.md)
