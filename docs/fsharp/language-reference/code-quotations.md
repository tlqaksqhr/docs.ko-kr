---
title: 코드 인용(F#)
description: '생성 하 고 프로그래밍 방식으로 F # 코드 식을 사용할 수 있는 언어 기능 F # 코드 인용에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: a6fab0364cadef1f45276267a59c694140b24a9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564536"
---
# <a name="code-quotations"></a>코드 인용

> [!NOTE]
API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

이 항목에서는 설명 *코드 인용*를 생성 하 고 프로그래밍 방식으로 F # 코드 식을 사용할 수 있는 언어 기능. 이 기능을 사용 하는 추상 구문 트리 F # 코드를 생성할 수 있습니다. 추상 구문 트리 트래버스 고 그런 다음 응용 프로그램의 필요에 따라 처리할 수 있습니다. 예를 들어 F # 코드를 생성 하거나 다른 언어의 코드를 생성 하 여 트리를 사용할 수 있습니다.


## <a name="quoted-expressions"></a>따옴표 붙은 식
A *인용 된 식* 식인지 F # 코드 프로그램의 일부분으로 컴파일되지 않은 방식으로 구분 되지만 대신 컴파일 결과 F # 식을 나타내는 개체입니다. 두 가지 방법 중 하나에 따옴표 붙은 식에 표시할 수 있습니다: 형식 정보를 사용 하거나 형식 정보 없이 합니다. 기호를 사용 하는 형식 정보를 포함 하려는 경우 `<@` 및 `@>` 에 인용된 된 식을 구분 합니다. 기호를 사용 하는 형식 정보를 필요 하지 않은 경우 `<@@` 및 `@@>`합니다. 다음 코드는 형식화 및 형식화 되지 않은 인용구를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

식 트리를 트래버스하는 형식 정보를 포함 하지 않는 경우 합니다. 형식화 된 기호가 포함 된 따옴표 붙은 식의 결과 형식이 `Expr<'T>`, 여기서 형식 매개 변수는 F # 컴파일러는 형식 유추 알고리즘을 기준으로 식의 형식입니다. 따옴표 붙은 식의 형식이 제네릭이 아닌 형식 형식 정보 없이 코드 인용을 사용 하면 [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)합니다. 호출할 수 있습니다는 [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) 속성에는 형식화 된 `Expr` 클래스는 형식화 되지 않은 얻으려고 `Expr` 개체입니다.

다양 한 개체를 생성 하 F # 식을 프로그래밍 방식으로 사용할 수 있는 정적 메서드는 `Expr` 클래스를 사용 하지 않고 따옴표 붙은 식입니다.

참고 코드 인용에는 전체 식이 포함 되어야 합니다. 에 대 한는 `let` 바인딩, 예를 들어 필요한 바인딩된 이름 및 바인딩을 사용 하는 추가 식을 정의 합니다. 자세한 구문에서이 다음에 나오는 식의 `in` 키워드입니다. 모듈의 최상위 수준에서이 모듈에서 다음 식을 방금 이지만 인용에 명시적으로 포함 되어야 합니다.

따라서 다음 식은 올바르지 않습니다.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

하지만 다음 식은 올바릅니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

코드 인용을 사용 하려면 가져오기 선언 추가 해야 합니다 (사용 하 여는 `open` 키워드)가 열립니다는 [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) 네임 스페이스입니다.

F # PowerPack 평가 하 고 실행 하는 F # 식을 개체에 대 한 지원을 제공 합니다.


## <a name="expr-type"></a>Expr 형식
인스턴스는 `Expr` 유형은 F # 식을 나타냅니다. 제네릭과 제네릭이 아닌 `Expr` 유형은 F # 라이브러리 설명서에 설명 되어 있습니다. 자세한 내용은 참조 [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) 및 [Quotations.Expr 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)합니다.


## <a name="splicing-operators"></a>결합 연산자
스플라이스 리터럴 코드 인용을 프로그래밍 방식으로 또는 다른 코드 인용에서 만든 식과 결합할 수 있습니다. `%` 및 `%%` 연산자를 사용 하는 코드 인용에 F # 식을 개체를 추가할 수 있습니다. 사용 된 `%` 형식화 된 인용에 식을 형식화 된 개체를 삽입 하는 연산자를 사용 하 여는 `%%` 연산자를 형식화 되지 않은 인용에 식을 형식화 되지 않은 개체를 삽입 합니다. 두 연산자는 단항 전위 연산자입니다. 따라서 경우 `expr` 형식의 식이 형식화 되지 않은 `Expr`, 다음 코드는 유효 합니다.

```fsharp
<@@ 1 + %%expr @@>
```

쓰고 `expr` 형식의 형식화 된 견적 `Expr<int>`, 다음 코드는 유효 합니다.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>예제

### <a name="description"></a>설명
다음 예제에서는 식 개체에 F # 코드를 저장 한 다음 식의 F # 코드를 인쇄 코드 인용의 사용을 보여 줍니다. 함수 `println` 정의 된 재귀 함수를 포함 하 `print` F # 식을 개체를 표시 하는 (형식의 `Expr`)는 친숙 한 형태로 표시 합니다. 여러 활성 패턴은는 [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) 및 [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) 식 개체를 분석에 사용할 수 있는 모듈입니다. 이 예에서는 F # 식을에 표시 될 수 있는 모든 패턴을 포함 되지 않습니다. 패턴에 와일드 카드 패턴에 일치 하는 트리거 인식 되지 않은 (`_`) 하 고 사용 하 여 렌더링 되는 `ToString` 메서드 이며에 `Expr` 입력에 일치 하는 식에 추가할 활성 패턴을 확인할 수 있습니다.


### <a name="code"></a>코드
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]
    
### <a name="output"></a>출력

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>예제

### <a name="description"></a>설명
세 가지 활성 패턴을 사용할 수도 있습니다는 [ExprShape 모듈](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) 적은 활성 패턴으로 식 트리를 합니다. 이러한 활성 패턴 트리 이동 하지만 대부분의 노드에서 있는 모든 정보를 불필요 하는 경우 유용할 수 있습니다. F # 식이 다음 세 가지 패턴 중 하 나와 일치 하는 이러한 패턴을 사용 하는 경우: `ShapeVar` 식이 변수에 `ShapeLambda` 식 람다 식의 값 또는 `ShapeCombination` 식이 80 이외 인 경우. 이전 코드 예제와 같이 활성 패턴을 사용 하 여 식 트리를 이동 하는 경우 모든 가능한 F # 식은 형식에 처리 하기 위해 더 많은 패턴을 사용 해야 하 고 코드를 더 복잡 해질 합니다. 자세한 내용은 참조 [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination 활성 패턴](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)합니다.

다음 코드 예제에서는 보다 복잡 한 순회에 대 한 기준으로 사용할 수 있습니다. 이 코드에서는 함수 호출을 포함 하는 식에 대 한 식 트리 만들어집니다 `add`합니다. [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) 활성 패턴은 한 모든 호출을 검색 하는 데 사용 `add` 식 트리에서 합니다. 이 활성 패턴 할당에 대 한 호출의 인수는 `exprList` 값입니다. 이 경우 많습니다 두 개만 개뿐이므로 이들 및 함수는 인수에 재귀적으로 호출 됩니다. 결과에 대 한 호출을 나타내는 코드 인용에 삽입 됩니다 `mul` 스플라이스 연산자를 사용 하 여 (`%%`). `println` 이전 예제에서 함수는 결과 표시 하는 데 사용 됩니다.

다른 활성 패턴 분기의 코드를 다시 생성 하기만 동일한 식 트리를 되므로 결과 식은 작업만에서 변경 `add` 를 `mul`합니다.


### <a name="code"></a>코드
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a>출력

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

