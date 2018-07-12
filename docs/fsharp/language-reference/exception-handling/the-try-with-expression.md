---
title: '예외: try...with 식(F#)'
description: "예외 처리에 대 한 F # 'try...with' 식을 사용 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 5e6e16d5fba88841d567512ba7e08a2e8d17bdba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565290"
---
# <a name="exceptions-the-trywith-expression"></a>예외: try...with 식

이 항목에서는 설명는 `try...with` 식, F # 언어의 예외 처리에 사용 되는 식입니다.


## <a name="syntax"></a>구문

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>설명
`try...with` 식은 F #에서 예외를 처리 하는 데 사용 됩니다. 비슷합니다는 `try...catch` C# 문. 위 구문에 코드에서 *expression1* 예외가 발생할 수 있습니다. `try...with` 식이 값을 반환 합니다. 예외가 throw 되 면 전체 식의 값을 반환 *expression1*합니다. 예외가 throw 되 면 각 *패턴* 는 경우를 제외 하 고 해당 첫 번째 일치 하는 패턴에 대 한 다시 비교 *식*으로 알려진는 *예외처리기*해당 분기 실행 되 고 해당 예외 처리기에서 식의 값을 반환 하는 전체 식에 대 한 합니다. 패턴 일치 하는 경우 일치 하는 처리기를 찾을 때까지 호출 스택으로 예외 전파 합니다. 예외 처리기에 각 식에서 반환 된 값의 형식이 일치 해야 하는 식에서 반환 되는 형식에서 `try` 블록입니다.

대부분의 경우 또한 오류가 발생 했다는 사실을 각 예외 핸들러에서의 식에서 반환 될 수 있는 유효한 값 임을 의미 합니다. 자주 패턴은 옵션 형식 이어야 하는 식의 형식입니다. 다음 코드 예제에서는이 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

예외는.NET 예외 수 또는 F # 예외 될 수 있습니다. 사용 하 여 F # 예외를 정의할 수는 `exception` 키워드입니다.

예외 유형 및 기타 조건;에 대해 필터링 하는 다양 한 패턴을 사용할 수 있습니다. 옵션은 다음 표에 요약 되어 있습니다.


|무늬|설명|
|-------|-----------|
|:? *예외 형식*|지정된 된.NET 예외 형식과 일치 합니다.|
|:? *예외 형식* 으로 *식별자*|지정된 된.NET 예외 형식과 일치 하지만 예외 명명된 된 값을 제공 합니다.|
|*예외 이름을*(*인수*)|F # 예외 형식과 일치 하 고 인수를 바인딩합니다.|
|*identifier*|모든 예외에 일치 하 고 예외 개체에 이름을 바인딩합니다. 에 해당 하는 **:? System.Exception으로 * * * 식별자*|
|*식별자* 때 *조건*|조건이 true 인 경우 모든 예외를 일치 시킵니다.|

## <a name="examples"></a>예제
다음 코드 예제에서는 다양 한 예외 처리기 패턴 사용법을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
`try...with` 구문은에서 별도 식을 고 `try...finally` 식입니다. 따라서 코드 둘 다 요구 하는 경우는 `with` 블록 및 `finally` 블록 두 식을 중첩 해야 합니다.

>[!NOTE] 
사용할 수 있습니다 `try...with` 비동기 워크플로 및 기타 계산 식, 있는 경우 사용자 지정 된 버전의는 `try...with` 식이 사용 됩니다. 자세한 내용은 참조 [비동기 워크플로](../asynchronous-workflows.md), 및 [계산 식](../computation-expressions.md)합니다.


## <a name="see-also"></a>참고 항목
[예외 처리](index.md)

[예외 형식](exception-types.md)

[예외: `try...finally` 식](the-try-finally-expression.md)
