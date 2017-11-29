---
title: "가져오기 선언: open 키워드(F#)"
description: "해당 요소를 정규화 된 이름을 사용 하지 않고 참조할 수 F # 가져오기 선언 및 모듈 또는 네임 스페이스 지정 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a>가져오기 선언:는 `open` 키워드

> [!NOTE]
이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

*가져오기 선언* 모듈이 나 네임 스페이스 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 지정 합니다.


## <a name="syntax"></a>구문

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>설명
정규화 된 네임 스페이스 또는 모듈 경로 사용 하 여 코드를 참조 될 때마다 작성 읽고 유지 관리 하는 코드를 만들 수 있습니다. 대신 사용할 수는 `open` 키워드에 대 한 자주 네임 스페이스 및 모듈을 사용 하 여 해당 모듈 또는 네임 스페이스의 멤버를 참조할 때 정규화 된 이름 대신 이름의 약식 형태를 사용할 수 있습니다. 이 키워드는 비슷합니다는 `using` C# 키워드 `using namespace` Visual c + +에서 및 `Imports` Visual Basic의 합니다.

동일한 프로젝트에서 또는 참조 되는 프로젝트 또는 어셈블리에서 모듈 또는 제공 된 네임 스페이스 여야 합니다. 없는 경우에 프로젝트에 대 한 참조를 추가 하거나 사용할 수 있습니다는 `-reference` 명령`-`명령줄 옵션 (또는 그 축약형 `-r`). 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.

가져오기 선언을 사용 하면 이름을 바깥쪽 네임 스페이스, 모듈 또는 파일의 끝까지 선언 뒤에 오는 코드에서 사용할 수 있습니다.

가져오기 선언이 여러 개를 사용 하면 별도 줄에 나타납니다.

다음 코드의 사용을 보여 줍니다.는 `open` 코드를 단순화 하는 키워드입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F # 컴파일러 같은 이름을 여러 개 열려 모듈 또는 네임 스페이스에서 발생 하는 경우 모호성으로 인해 발생 하는 경우에 오류 또는 경고 생성 하지 합니다. 모호성이 발생 하면 F #에서는 더 최근에 열었던 모듈 또는 네임 스페이스를 기본 설정 합니다. 예를 들어, 다음 코드에서에서 `empty` 의미 `Seq.empty`경우라도, `empty` 둘 다에 `List` 및 `Seq` 모듈입니다.

```fsharp
open List
open Seq
printfn "%A" empty
```

따라서 때는 주의 해야 모듈 또는 네임 스페이스와 같은 열 `List` 또는 `Seq` 동일한 이름을 가진; 대신 정규화 된 이름 사용을 고려 하는 멤버를 포함 하는 합니다. 코드는 가져오기 선언의 순서에 종속 된 경우를 피해 야 합니다.


## <a name="namespaces-that-are-open-by-default"></a>기본적으로 열려 있는 네임 스페이스
일부 네임 스페이스를 열 때 암시적으로 명시적 가져오기 선언이 필요 없이 F # 코드에서 매우 자주 사용 됩니다. 다음 표에서 기본적으로 열려 있는 네임 스페이스를 보여 줍니다.

|네임스페이스|설명|
|---------|-----------|
|`Microsoft.FSharp.Core`|와 같은 기본 제공 형식에 대 한 F # 형식 정의 기본 들어 `int` 및 `float`합니다.|
|`Microsoft.FSharp.Core.Operators`|와 같은 기본 산술 연산을 포함 `+` 및 `*`합니다.|
|`Microsoft.FSharp.Collections`|변경 불가능 컬렉션 클래스와 같은 포함 `List` 및 `Array`합니다.|
|`Microsoft.FSharp.Control`|지연 계산 등 비동기 워크플로 제어 구문에 대 한 형식을 포함합니다.|
|`Microsoft.FSharp.Text`|서식이 지정 된 io와 같은 함수를 포함 된 `printf` 함수입니다.|

## <a name="autoopen-attribute"></a>AutoOpen 특성
적용할 수는 `AutoOpen` 어셈블리를 참조할 때 네임 스페이스 또는 모듈을 자동으로 열리게 하려면 특성을 어셈블리에 있습니다. 적용할 수 있습니다는 `AutoOpen` 부모 모듈 또는 네임 스페이스를 열 때 해당 모듈을 자동으로 열도록 모듈에 특성입니다. 자세한 내용은 참조 [Core.AutoOpenAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)합니다.


## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess 특성
일부 모듈, 레코드 또는 공용 구조체 형식을 지정할 수는 `RequireQualifiedAccess` 특성입니다. 이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조 하는 경우 가져오기 선언 포함 하는지 여부에 관계 없이 정규화 된 이름을 사용 해야 합니다. 에 전략적으로이 특성을 사용 하는 경우 일반적으로 정의 하는 형식 이름이 사용 되는, 이름이 충돌 하지 않도록 하 고 있으므로 코드 복원 성도 뛰어납니다. 라이브러리의 변화에 따라 도움말입니다. 자세한 내용은 참조 [Core.RequireQualifiedAccessAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)합니다.


## <a name="see-also"></a>참고 항목
[# 언어 참조](index.md)

[네임스페이스](namespaces.md)

[모듈](modules.md)

