---
title: '리소스 관리: use 키워드(F#)'
description: "F # 키워드 'use'와 '사용' 함수를 초기화 및 리소스의 해제를 제어할 수 있는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: c75783080d1d87c6ee75aede500d3d0b3fdf8355
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-management-the-use-keyword"></a>리소스 관리: use 키워드

키워드에 설명 `use` 및 `using` 초기화 및 리소스의 해제를 제어할 수 있는 함수입니다.

## <a name="resources"></a>자료
용어 *리소스* 에 여러 가지 방법으로 사용 됩니다. 예, 리소스 문자열, 그래픽, like, 같은 있지만이 컨텍스트에서 응용 프로그램을 사용 하는 데이터 수 *리소스* 그래픽 장치 컨텍스트, 파일 핸들, 네트워크 등의 소프트웨어 또는 운영 체제 리소스에 대 한 참조 와 데이터베이스 연결, 대기 핸들 등과 같은 동시성 개체. 응용 프로그램에서 이러한 리소스의 사용에 운영 체제 또는 다른 응용 프로그램에 제공 될 수 있도록 풀에 리소스의 이후 릴리스 후 다른 리소스 공급자에서 리소스를 확보를 해야 합니다. 문제는 응용 프로그램 일반적인 풀으로 리소스를 해제 하지 않는 경우에 발생 합니다.

## <a name="managing-resources"></a>리소스 관리
책임 지 고 효율적으로 응용 프로그램의 리소스를 관리 하려면 신속 하 게 하 고 예측 가능한 방식으로 리소스를 해제 해야 합니다. .NET Framework를 사용 하면 제공 하 여이 작업을 수행 된 `System.IDisposable` 인터페이스입니다. 구현 하는 형식은 `System.IDisposable` 에 `System.IDisposable.Dispose` 메서드를 올바르게 리소스를 해제 합니다. 잘 작성 된 응용 프로그램을 `System.IDisposable.Dispose` 제한 된 리소스를 보유 하는 모든 개체는 더 이상 필요 없는 신속 하 게 호출 됩니다. 다행히 대부분.NET 언어를 더 쉽게 확인을 지원 하 고 F #도 예외가 합니다. dispose 패턴을 지 원하는 두 개의 유용한 언어 구문이 있습니다:는 `use` 바인딩 및 `using` 함수입니다.

## <a name="use-binding"></a>바인딩을 사용 하 여
`use` 키워드의 구문과 유사 합니다 하는 폼에는 `let` 바인딩:

사용 하 여 *값* = *식*

와 동일한 기능을 제공는 `let` 바인딩 있지만 경우에 대 한 호출 추가 `Dispose` 값 범위를 벗어날 때 값에 있습니다. 컴파일러는 값에 대해 null 확인을 삽입 되는 경우 값은 참고 `null`에 대 한 호출 `Dispose` 시도 됩니다.

다음 예제를 사용 하 여 파일을 자동으로 종결 하는 방법을 보여 줍니다는 `use` 키워드입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
사용할 수 있습니다 `use` 계산 식에는 사용자 지정 된 버전의 경우는 `use` 식이 사용 됩니다. 자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.


## <a name="using-function"></a>함수를 사용 하 여
`using` 함수 형식은 다음과 같습니다.

`using` (*expression1*) *람다 또는 함수*

에 `using` 식 *expression1* 삭제 해야 하는 개체를 만듭니다. 결과 *expression1* (삭제 해야 하는 개체)가 인수, *값*을 *람다 또는 함수*, 단일 필요한 함수 중 하나는 생성 되는 값과 일치 하는 형식의 인수를 남은 *expression1*, 또는 해당 형식의 인수를 예상 하는 람다 식입니다. 함수 실행 끝날 때 런타임에서 호출 `Dispose` 리소스를 해제 하 고 (값이 `null`, Dispose에 대 한 호출 시도 하지는 경우).

다음 예제는 `using` 람다 식 사용 하 여 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

에서는 다음 예제는 `using` 함수로 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

다른 인수가 이미 적용 하는 함수 일 수 있는지 확인 합니다. 다음 코드 예제에서는 이 작업을 보여줍니다. 문자열이 포함 된 파일을 만듭니다 `XYZ`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

`using` 함수 및 `use` 바인딩은 거의 같은 방식으로 동일한 작업을 수행 합니다. `using` 키워드 좀 더 잘 제어할 때 `Dispose` 라고 합니다. 사용 하는 경우 `using`, `Dispose` 사용 하는 경우, 함수 또는 람다 식의 끝에서 호출 되는 `use` 키워드를 `Dispose` 포함 하는 코드 블록의 끝에 호출 됩니다. 일반적으로 사용 하려면 해야 `use` 대신는 `using` 함수입니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
