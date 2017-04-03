---
title: "식 트리 작성"
description: "식 트리 작성"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 542754a9-7f40-4293-b299-b9f80241902c
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4673690c95d1a1fcea950db272cf0685a9d4c888
ms.lasthandoff: 03/13/2017

---

# <a name="building-expression-trees"></a>식 트리 작성

[이전 - 식 해석](expression-trees-interpreting.md)

지금까지 살펴본 모든 식 트리는 C# 컴파일러에서 만들어졌습니다. `Expression<Func<T>>` 또는 유사한 형식의 변수 형식에 할당된 람다 식을 만들기만 하면 됐습니다. 그러나 식 트리를 만드는 유일한 방법은 아닙니다. 대부분의 시나리오에서는 런타임에 메모리에서 식을 작성해야 함을 알 수 있습니다. 

식 트리는 변경할 수 없다는 사실로 인해 식 트리 작성은 복잡합니다. 변경할 수 없다는 것은 리프에서 루트까지 위로 트리를 작성해야 한다는 의미입니다. 식 트리를 작성하는 데 사용할 API에 이 사실이 반영됩니다. 즉, 노드를 작성하는 데 사용되는 메서드는 모든 자식을 인수로 사용합니다. 이 기술을 보여 주는 몇 가지 예제를 살펴보겠습니다.

## <a name="creating-nodes"></a>노드 만들기

비교적 간단하게 다시 시작해 보겠습니다. 이러한 섹션 전체에서 사용한 더하기 식을 사용하겠습니다.

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

해당 식 트리를 생성하려면 리프 노드를 생성해야 합니다.
리프 노드는 상수이므로 `Expression.Constant` 메서드를 사용하여 노드를 만들 수 있습니다.

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

다음으로 더하기 식을 작성해 보겠습니다.

```csharp
var addition = Expression.Add(one, two);
```

더하기 식을 작성했으면 람다 식을 만들 수 있습니다.

```csharp
var lamdba = Expression.Lambda(addition);
```

이 식은 인수가 없기 때문에 매우 간단한 LambdaExpression입니다.
이 섹션의 뒷부분에서는 인수를 매개 변수에 매핑하고 더 복잡한 식을 작성하는 방법을 살펴봅니다.

이 식처럼 간단한 식의 경우 모든 호출을 단일 문으로 결합할 수 있습니다.

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a>트리 작성

메모리에서 식 트리를 작성할 때의 기본 사항입니다. 좀 더 복잡한 트리는 일반적으로 노드 유형과 트리의 노드가 더 많음을 의미합니다. 예제를 하나 더 실행하고 식 트리를 만들 때 일반적으로 작성하는 인수 노드와 메서드 호출 노드라는 노드 유형을 두 개 더 살펴보겠습니다.

식 트리를 작성하여 다음 식을 만들어 보겠습니다.

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```
 
`x` 및 `y`에 대한 매개 변수 식부터 만듭니다.

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

곱하기와 더하기 식을 만들 때 이미 살펴본 패턴을 따릅니다.

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

다음으로 `Math.Sqrt`를 호출하기 위한 메서드 호출 식을 만들어야 합니다.

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

그런 다음 마지막으로 메서드 호출을 람다 식에 넣고 람다 식에 대한 인수를 정의해야 합니다.

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

더 복잡한 이 예제에서는 식 트리를 만드는 데 자주 필요한 기술을 몇 가지 더 확인할 수 있습니다.

먼저 매개 변수 또는 지역 변수를 나타내는 개체를 만든 후에 사용해야 합니다. 이러한 개체를 만들었으면 필요할 때마다 식 트리에서 사용할 수 있습니다.

두 번째로 해당 메서드에 액세스하는 식 트리를 만들 수 있도록 리플렉션 API의 하위 집합을 사용하여 `MethodInfo` 개체를 만들어야 합니다. .NET Core 플랫폼에서 사용할 수 있는 리플렉션 API의 하위 집합으로 제한해야 합니다. 이제 이러한 기술은 다른 식 트리로 확장됩니다.

## <a name="building-code-in-depth"></a>코드 빌드에 대한 자세한 설명

이러한 API를 사용하여 빌드할 수 있는 항목으로 제한되지 않습니다. 그러나 작성하려는 식 트리가 복잡할수록 코드를 관리하고 읽기가 더 어려워집니다. 

다음 코드에 해당하는 식 트리를 작성해 보겠습니다.

```csharp
Func<int, int> factorialFunc = (n) =>
{
    var res = 1;
    while (n > 1)
    {
        res = res * n;
        n--;
    }
    return res;
};
```

위의 예제에서는 식 트리를 작성하지 않고 대리자만 작성했습니다. `Expression` 클래스를 사용하여 문 람다를 빌드할 수 없습니다. 다음은 동일한 기능을 빌드하는 데 필요한 코드입니다. `while` 루프를 빌드하는 API가 없기 때문에 복잡합니다. 대신 루프를 중단하려면 조건부 테스트를 포함하는 루프와 레이블 대상을 빌드해야 합니다. 

```csharp
var nArgument = Expression.Parameter(typeof(int), "n");
var result = Expression.Variable(typeof(int), "result");

// Creating a label that represents the return value
LabelTarget label = Expression.Label(typeof(int));

var initializeResult = Expression.Assign(result, Expression.Constant(1));

// This is the inner block that performs the multiplication,
// and decrements the value of 'n'
var block = Expression.Block(
    Expression.Assign(result,
        Expression.Multiply(result, nArgument)),
    Expression.PostDecrementAssign(nArgument)
);

// Creating a method body.
BlockExpression body = Expression.Block(
    new[] { result },
    initializeResult,
    Expression.Loop(
        Expression.IfThenElse(
            Expression.GreaterThan(nArgument, Expression.Constant(1)),
            block,
            Expression.Break(label, result)
        ),
        label
    )
);
```

계승 함수에 대한 식 트리를 작성하는 코드는 훨씬 더 길고 더 복잡하며, 레이블과 break 문 및 일상적인 코딩 작업에서 방지하려는 기타 요소로 인해 복잡해집니다. 

이 섹션에서는 이 식 트리의 모든 노드를 방문하는 방문자 코드도 업데이트하고 이 샘플에서 만들어진 노드에 대한 정보를 기록했습니다. 코드는 [샘플 섹션](https://github.com/dotnet/docs/tree/master/samples/csharp/expression-trees)에서 확인할 수 있습니다.
코드를 빌드하고 샘플을 실행하여 직접 실험할 수 있습니다.

## <a name="examining-the-apis"></a>API 검사

식 트리 API는 .NET Core에서 탐색하기가 더 어렵지만 괜찮습니다. 용도는 런타임에 코드를 생성하는 코드를 작성하는 경우처럼 다소 복잡합니다. C# 언어에서 사용할 수 있는 모든 제어 구조를 지원하고 API의 노출 영역을 적절히 작게 유지하는 작업 간에 균형을 맞추려면 복잡할 수 밖에 없습니다. 이러한 균형은 많은 제어 구조가 C# 구문이 아니라 컴파일러가 더 높은 수준의 구조체에서 생성하는 기본 논리를 나타내는 구조체에 의해 표시됨을 의미합니다. 

또한 `Expression` 클래스 메서드를 사용하여 직접 작성할 수 없는 C# 식도 있습니다. 일반적으로 C# 5 및 C# 6에서 추가된 최신 연산자 및 식이 있습니다. 예를 들어 `async` 식을 작성할 수 없으며 새로운 `?.` 연산자를 직접 만들 수 없습니다.

[다음 -- 식 변환](expression-trees-translating.md)

