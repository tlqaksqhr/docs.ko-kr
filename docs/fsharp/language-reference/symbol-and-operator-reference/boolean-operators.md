---
title: "부울 연산자(F#)"
description: "F # 프로그래밍 언어에서 사용할 수 있는 부울 연산자에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a>부울 연산자

이 항목에는 F # 언어의 부울 연산자에 대 한 지원을 설명합니다.


## <a name="summary-of-boolean-operators"></a>부울 연산자 요약
다음 표에 F # 언어에서 사용할 수 있는 부울 연산자 요약 되어 있습니다. 이러한 연산자에서 지원 되는 유일한 유형은 `bool` 유형입니다.

|연산자|설명|
|--------|-----------|
|`not`|부울 부정|
|<code>&#124;&#124;</code>|부울 OR|
|`&&`|부울 AND|

AND와 OR 부울 연산자 수행 *(short-circuit)*, 식의 전체 결과 확인 하는 데 필요한 경우에 연산자의 오른쪽에 있는 식 평가, 즉 합니다. 두 번째 식의 `&&` 연산자는 첫 번째 식으로 계산 하는 경우에 계산 됩니다 `true`;의 두 번째 식의 `||` 연산자는 첫 번째 식으로 계산 하는 경우에 계산 됩니다 `false`합니다.

## <a name="see-also"></a>참고 항목
[비트 연산자](bitwise-operators.md)

[산술 연산자](arithmetic-operators.md)

[기호 및 연산자 참조](index.md)
