---
title: 어설션(F#)
description: "F # 프로그래밍 언어에서 식 테스트에 대 한 디버깅 기능으로 'assert' 식을 사용 하는 방법에 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 83e6cd77bbbb2c32e9b778e5bf6dd9d2e9c8fe32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="assertions"></a>어설션

`assert` 식은 식을 테스트 하는 데 사용할 수 있는 디버깅 기능이 있습니다. 디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.

## <a name="syntax"></a>구문

```fsharp
assert condition
```

## <a name="remarks"></a>설명

`assert` 식에는 형식이 `bool -> unit`합니다.

위 구문에서 *조건* 테스트할 하는 부울 식을 나타냅니다. 식이 계산 되는 경우 `true`, 실행이 계속 영향을 주지 않습니다. 로 평가 되 면 `false`, 시스템 오류 대화 상자가 열립니다. 오류 대화 상자에 문자열을 포함 하는 캡션을 **어설션 오류**합니다. 대화 상자에 어설션 오류가 발생 한을 나타내는 스택 추적을 포함 합니다.

디버그 모드에서 컴파일할 때에 사용할 수는 어설션 검사 즉, 경우 상수 `DEBUG` 정의 됩니다. 기본적으로 프로젝트 시스템에서의 `DEBUG` 상수 릴리스 구성에 없습니다. 디버그 구성에서 정의 됩니다.

F # 예외 처리를 사용 하 여 어설션 실패 오류를 낼 수 없습니다.

>[!NOTE]
`assert` 함수는 <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 `assert` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>참고 항목

[F# 언어 참조](index.md)
