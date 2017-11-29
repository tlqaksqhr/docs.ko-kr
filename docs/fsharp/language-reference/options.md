---
title: "옵션(F#)"
description: "명명 된 값 또는 변수에 대 한 F # 형식 때 실제 값이 존재 하지 않을 옵션을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: 537ba69aecc1ab489de63d67c5f9ff857afb4a28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="options"></a>옵션

F #에서 옵션 종류는 명명 된 값 또는 변수에 대 한 실제 값이 존재 하지 않을 때 사용 됩니다. 옵션은 기본 형식이 고 해당 형식의 값을 보유할 수 또는 값이 될 수 있습니다.

## <a name="remarks"></a>설명
다음 코드에서는 옵션 종류를 생성 하는 함수를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

경우 볼 수 있듯이 입력 `a` 0 보다 크면 `Some(a)` 생성 됩니다.  그렇지 않으면 `None` 생성 됩니다.

값 `None` 옵션 실제 값이 없는 경우에 사용 됩니다. 그렇지 않으면 식 `Some( ... )` 옵션 값이 나와 있습니다. 값 `Some` 및 `None` 다음 함수에서와 같이 패턴 일치에 유용 `exists`를 반환 하 `true` 옵션 값이 있으면 및 `false` 그렇지 않은 경우.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>옵션을 사용 하 여
옵션은 다음 코드와 같이 일반적으로 검색 일치 하는 결과 반환 하지 않는 경우 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

이전 코드에서 목록은 재귀적으로 검색된 합니다. 함수 `tryFindMatch` 는 조건자 함수 `pred` 검색할 목록과 부울 값을 반환 하 합니다. 재귀 종료 되 고 함수가 반환 식에 옵션으로 한 값 조건자를 만족 하는 요소가 없으면 `Some(head)`합니다. 재귀 빈 목록이 일치 하는 경우 종료 됩니다. 값이 해당 시점 `head` 검색 되지 않은 및 `None` 반환 됩니다.

여러 F # 라이브러리 함수 반환이 존재 하지 않거나 않을 수 있는 값에 대 한 컬렉션을 검색 하는 `option` 유형입니다. 규칙에 따라 이러한 기능으로 시작 된 `try` 예를 들어 접두사 [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)합니다.

예를 들어 값을 생성 하려고 할 때 예외가 throw 될 수 있으면 값 존재 하지 않을 때에 옵션 유용할 수 있습니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

`openFile` 함수는 앞의 예에서 형식이 `string -> File option` 반환 하기 때문에 `File` 파일이 성공적으로 열리는 경우 개체 및 `None` 예외가 발생 합니다. 않을 상황에 따라 전파 되도록 허용 하는 대신 예외를 catch 하는 적절 한 디자인을 선택 하지 수 있습니다.


## <a name="option-properties-and-methods"></a>옵션 속성 및 메서드
옵션 종류는 다음과 같은 속성 및 메서드를 지원합니다.



|속성 또는 메서드|형식|설명|
|------------------|----|-----------|
|[없음](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|이 옵션 값을 만들 수 있도록 하는 정적 속성은 `None` 값입니다.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|반환 `true` 경우이 옵션에는 `None` 값입니다.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|반환 `true` 옵션의 값이 아닌 값 `None`합니다.|
|[일부](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|옵션을 만드는 정적 멤버인 하지 않은 값이 `None`합니다.|
|[Value](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|기본 값을 반환 하거나 throw 한 `System.NullReferenceException` 값이 `None`합니다.|

## <a name="option-module"></a>Option 모듈
모듈이 [옵션](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), 옵션에 대 한 작업을 수행 하는 유용한 함수가 포함 됩니다. 일부 함수 속성의 기능을 반복은 함수 필요한 상황에 유용 합니다. [Option.isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) 및 [Option.isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) 는 모두 모듈 함수 옵션 값이 있는지 여부가 테스트입니다. [Option.get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) 있는 경우는 값을 가져옵니다. 값이 없는 경우 throw `System.ArgumentException`합니다.

[Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) 함수는 값이 있는 경우 값의 함수를 실행 합니다. 함수는 정확히 하나의 인수를 사용 해야 하 고 해당 매개 변수 형식을 옵션 유형 이어야 합니다. 함수의 반환 값은 또 다른 옵션 종류입니다.

Option 모듈에는 목록, 배열, 시퀀스 및 기타 컬렉션 형식에 사용할 수 있는 함수에 해당 하는 함수가 포함 되어 있습니다. 이러한 함수에 포함 [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), 및 [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876)합니다. 이러한 함수를 0 개 또는 한 요소의 모음 처럼 사용할 옵션을 사용 합니다. 자세한 내용 및 예제에 대 한 컬렉션 함수에서의 설명을 참조 [나열](lists.md)합니다.


## <a name="converting-to-other-types"></a>다른 형식으로 변환
옵션 목록 또는 배열 변환할 수 있습니다. 옵션은 이러한 데이터 구조를 개별적으로 변환 되 면 결과 데이터 구조에 0 개 이상의 요소가 있습니다. 사용 하 여 배열에 옵션으로 변환 하려면 [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64)합니다. 옵션 목록으로 변환 하려면 사용 하 여 [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1)합니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[F# 형식](fsharp-types.md)
