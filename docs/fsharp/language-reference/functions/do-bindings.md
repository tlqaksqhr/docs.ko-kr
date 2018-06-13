---
title: do 바인딩(F#)
description: "F # 'do' 바인딩을 하는 방법을 함수나 값을 정의 하지 않고 코드 실행에 대해 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 6fd084090a204beab0da1c2deb5b5ae2a86281c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562338"
---
# <a name="do-bindings"></a>do 바인딩

A `do` 코드를 실행 하는 함수 또는 값을 정의 하지 않고 바인딩이 사용 됩니다. 수행 바인딩 수도 있습니다 참조 클래스에 사용 [ `do` 클래스에서](../members/do-bindings-in-classes.md)합니다.


## <a name="syntax"></a>구문

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>설명
사용 하 여 한 `do` 바인딩 함수 또는 값의 정의 의존 하지 않고 코드를 실행 하려는 경우. 식에는 `do` 바인딩 반환 해야 `unit`합니다. 최상위 수준에서 코드 `do` 바인딩 모듈 초기화 될 때 실행 됩니다. 키워드 `do` 선택 사항입니다.

최상위 수준에 특성을 적용할 수 있습니다 `do` 바인딩. 예를 들어 프로그램에서 COM interop를 사용 하는 경우 적용할는 `STAThread` 를 프로그램 특성입니다. 에 특성을 사용 하 여이 작업을 수행할 수는 `do` 바인딩, 다음 코드에 나와 있는 것 처럼 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](../index.md)

[함수](index.md)

