---
title: 비트 연산자(F#)
description: 'F # 프로그래밍 언어에서 사용할 수 있는 비트 연산자에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a>비트 연산자

이 항목에서는 F # 언어에서 사용할 수 있는 비트 연산자를 설명 합니다.

## <a name="summary-of-bitwise-operators"></a>비트 연산자 요약
다음 표에서 F # 언어에서 정수 계열 형식과 unboxed에 지원 되는 비트 연산자를 설명 합니다.

|연산자|노트|
|--------|-----|
|`&&&`|비트 AND 연산자입니다. 결과 비트의에서 경우에 두 소스 피연산자의 해당 비트는 1이 고 값 1을 갖습니다.|
|<code>&#124;&#124;&#124;</code>|비트 OR 연산자입니다. 결과 비트는 값 1 경우 원본에 해당 비트의 두 피연산자가 1입니다.|
|`^^^`|비트 배타적 OR 연산자입니다. 결과의 비트 소스 피연산자의 비트 같지 않은 값이 있는 경우에 값 1을 갖습니다.|
|`~~~`|비트 부정 연산자입니다. 단항 연산자 이므로 결과 생성 중인 소스 피연산자의 모든 0 비트는 1 비트 변환할 모든 1 비트를 0 비트로 변환 됩니다.|
|`<<<`|비트 왼쪽 시프트 연산자. 결과 비트를 첫 번째 피연산자는 두 번째 피연산자의 비트 수 만큼 왼쪽 이동 합니다. 가장 중요 한 위치에서 벗어나 이동한 비트 위치로 돌아가지 않습니다. 가장 덜 중요 한 비트는 0으로 채워집니다. 두 번째 인수 형식이 `int32`합니다.|
|`>>>`|비트 오른쪽 시프트 연산자. 결과 두 번째 피연산자의 비트 수 만큼 오른쪽으로 이동 하는 비트를 첫 번째 피연산자입니다. 가장 덜 중요 한 위치에서 벗어나 이동한 비트 위치 돌아가지 않습니다. 부호 없는 형식에 대 한 최상위 비트는 0으로 채워집니다. 부호 있는 형식에 대 한 최상위 비트는 1로 채워집니다. 두 번째 인수 형식이 `int32`합니다.|

비트 연산자와 함께 사용할 수는 다음과 같은: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, 및 `unativeint`합니다.

## <a name="see-also"></a>참고 항목
[기호 및 연산자 참조](index.md)

[산술 연산자](arithmetic-operators.md)

[부울 연산자](boolean-operators.md)

