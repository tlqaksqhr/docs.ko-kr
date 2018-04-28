---
title: 진입점(F#)
description: 'F # 프로그램 실행 정식으로 시작, 실행 파일로 컴파일로 진입점을 설정 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 42e5fe7f85285f990ef92e9791ed5bdfacb85059
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="entry-point"></a>진입점

이 항목에서는 F # 프로그램에 진입점을 설정 하려면 사용 하는 방법을 설명 합니다.


## <a name="syntax"></a>구문

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>설명
위 구문에서 *let 함수 바인딩에* 는 함수에 대 한 정의 `let` 바인딩.

실행 파일로 실행 정식으로 시작은 컴파일된 프로그램 진입점입니다. 적용 하 여 F # 응용 프로그램에 대 한 진입점을 지정 된 `EntryPoint` 프로그램의 특성 `main` 함수입니다. 이 함수 (사용 하 여 만든는 `let` 바인딩) 마지막으로 컴파일된 파일에 마지막 함수 여야 합니다. 마지막 컴파일된 파일은 프로젝트의 마지막 파일 또는 명령줄에 전달 되는 마지막 파일.

진입점 함수 형식이 `string array -> int`합니다. 명령줄에 제공 된 인수에 전달 되는 `main` 함수에 문자열의 배열입니다. 배열의 첫 번째 요소는 첫 번째 인수입니다. 실행 파일의 이름 일부 다른 언어에서는 있는 그대로 배열에 포함 되지 않습니다. 반환 값은 프로세스에 대 한 종료 코드로 사용 됩니다. 0에는 일반적으로 성공을 나타냅니다. 0이 아닌 값에 오류가 발생 합니다. 규칙은 없습니다 반환 코드 0이 아닌;의 특정 의미에 대 한 반환 코드의 의미는 응용 프로그램 마다 다릅니다.

다음 예제에서는 간단한 `main` 함수입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

이 코드 명령줄으로 실행 되 면 `EntryPoint.exe 1 2 3`, 출력은 다음과 같습니다.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>암시적 진입점
프로그램에 아니요 **EntryPoint** 진입점으로 컴파일할 마지막 파일의 최상위 수준 바인딩이 명시적으로 나타내는 특성의 진입점으로 사용 됩니다.


## <a name="see-also"></a>참고 항목
[함수](index.md)

[let 바인딩](let-bindings.md)
