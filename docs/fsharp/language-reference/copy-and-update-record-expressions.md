---
title: "복사 및 업데이트가 레코드 식 (F #)"
description: "작성 한 '복사 및 업데이트 레코드 식' 복사는 기존 레코드를 업데이트 하는 필드를 지정 및 업데이트 된 레코드를 반환 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b5fc4ef0-64eb-4272-96a7-bb4dffbb634a
ms.openlocfilehash: 2eb51842b678780a1d6da96e237ebb92d1ea5cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="copy-and-update-record-expressions"></a>레코드 식 복사 및 업데이트

A *복사 및 업데이트 레코드 식* 기존 레코드를 복사, 지정 된 필드를 업데이트 및 업데이트 된 레코드를 반환 하는 식입니다.


## <a name="syntax"></a>구문

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>설명
레코드를 기존 레코드 업데이트가 가능한 인수가 있도록 기본적으로 변경할 수 없는 합니다. 업데이트 된 레코드는 레코드의 모든 필드를 만들려면 해야 다시 지정 합니다. 이 작업을 간소화 하기 위해는 *복사 및 업데이트 레코드 식* 사용할 수 있습니다. 이 식은 기존 레코드는 사용, 식에서 지정 된 필드와 식으로 지정 된 누락 된 필드를 사용 하 여 동일한 유형의 새 브러시를 만듭니다.
기존 레코드를 복사 하 고 필드 값의 일부를 변경 해야 할 경우에 유용할 수 있습니다.

사용 예를 들어 새로 만든된 레코드.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

사용 하면 해당 레코드의 필드에 대해서만 업데이트 하는 경우는 *복사 및 업데이트 레코드 식* 다음과 같습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>참고 항목
[레코드](records.md)

[F# 언어 참조](index.md)
