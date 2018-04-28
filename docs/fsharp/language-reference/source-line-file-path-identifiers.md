---
title: 소스 줄, 파일 및 경로 식별자(F#)
description: '기본 제공 F # 식별자 값을 사용 하면 소스 줄 번호, 디렉터리 및 파일 이름을 코드에서 액세스할 수를 사용 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 18a26f0aa0a0c1f9c0b448ec46eaebd540391324
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="source-line-file-and-path-identifiers"></a>소스 줄, 파일 및 경로 식별자

식별자 `__LINE__`, `__SOURCE_DIRECTORY__` 및 `__SOURCE_FILE__` 코드의 소스 줄 번호, 디렉터리 및 파일 이름에 액세스할 수 있도록 하는 기본 제공 값입니다.


## <a name="syntax"></a>구문

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>설명
이러한 각 값의 형식이 `string`합니다.

다음 표에서 소스 줄, 파일 및 경로 식별자 F #에서 사용할 수 있는 요약 되어 있습니다. 이러한 식별자는 전처리기 매크로; 하지 컴파일러에서 인식 되는 기본 제공 값 않은 것입니다.

|미리 정의 된 식별자|설명|
|---------------------|-----------|
|`__LINE__`|현재 줄 번호를 고려 `#line` 지시문입니다.|
|`__SOURCE_DIRECTORY__`|현재 원본 디렉터리의 전체 경로를 계산 고려 `#line` 지시문입니다.|
|`__SOURCE_FILE__`|현재 소스 파일 이름과 경로 계산 고려 `#line` 지시문입니다.|
에 대 한 자세한 내용은 `#line` 지시문 참조 [컴파일러 지시문](compiler-directives.md)합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 이러한 값을 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

출력:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>참고 항목
[컴파일러 지시문](compiler-directives.md)

[F# 언어 참조](index.md)
