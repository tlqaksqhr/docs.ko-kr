---
title: "로컬 함수 및 람다 식"
description: "로컬 함수가 람다 식보다 더 적합한 선택일 수 있는 이유를 알아봅니다."
keywords: "C#, .NET, .NET Core, 최신 기능, 새로운 기능, 로컬 함수, 람다 식"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 20312b58a24dc991791edad4bb92d3a8ca6d501a
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="local-functions-compared-to-lambda-expressions"></a>람다 식에 비해 로컬 함수

얼핏 보기에 [로컬 함수](programming-guide/classes-and-structs/local-functions.md)와 [람다 식](lambda-expressions.md)은 매우 유사합니다. 대부분의 경우 람다 식과 로컬 함수를 사용 하 여 선택 된 스타일 및 개인 기본 설정 하는 것 이지만 그러나 실제에 차이점이 하나 또는 알고 있어야 하 고 다른을 사용할 수 있습니다.

계승 알고리즘의 로컬 함수 및 람다 식 구현 간의 차이점을 살펴보겠습니다. 먼저 로컬 함수를 사용하는 버전은 다음과 같습니다.

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

람다 식을 사용하는 버전과 해당 구현을 비교해 보세요.

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

로컬 함수는 이름을 사용 합니다. 람다 식에 있는 변수를 할당 된 무명 메서드는 `Func` 또는 `Action` 형식입니다. 로컬 함수를 선언 된 인수 형식 및 반환 형식이 함수 선언 포함 됩니다. 람다 본문에 포함 되는 대신 식, 인수 형식 및 반환 형식이 람다 식의 변수 형식 선언의 일부입니다. 이러한 두 가지 차이점이 코드를 더 명확 하 게 될 수 있습니다.

로컬 함수는 람다 식 보다 한 정적 할당에 대 한 다양 한 규칙을 갖고 있습니다. 로컬 함수 선언 된 범위에 모든 코드 위치에서 참조할 수 있습니다. 람다 식은 되거나 되기 전에 수 액세스할 (람다 식을 참조 delgate 통해 호출 합니다..)를 대리자 변수에 할당 합니다. 람다 식을 사용하는 버전은 람다 식 `nthFactorial`을 정의하기 전에 선언하고 초기화해야 합니다. 이렇게 하지 않으면 `nthFactorial`을 할당하기 전에 참조하여 컴파일 시간 오류가 발생합니다.
이러한 차이 재귀 알고리즘은 로컬 함수를 사용 하 여 만드는 쉽게 의미 합니다. 선언 하 고 자신을 호출 하는 로컬 함수를 정의할 수 있습니다. 람다 식은 선언 하 고 동일한 람다 식을 참조 하는 본문에 다시 할당 될 수 전에 기본 값을 할당 해야 합니다.

한 정적 할당 규칙은 로컬 함수 또는 내부 epression에서 캡처되는 변수를도 영향을 줍니다. 로컬 함수와 람다 식 규칙 캡처된 변수 할당 되어 있는지 확실 하 게 지점에는 로컬 함수 또는 람다 식을 대리자 변환 될 때 요구 합니다. 선언 된 경우 람다 식이 대리자도 변환 되는 다릅니다. 대리자는 대리자로 사용할 경우에 로컬 함수 변환 됩니다. 로컬 함수를 선언 하 고만 메서드처럼 호출 하 여 참조 하는 경우 대리자에 변환 되지 됩니다. 해당 규칙을 사용 하는 괄호로 묶인 범위 내의 모든 편리한 위치에서 로컬 함수를 선언할 수 있습니다. 모든 return 문을 뒤는 부모 메서드 끝에 로컬 함수 선언에 공통 되기 합니다.

셋째, 컴파일러는 캡처된 변수는 포함 범위에 정적으로 할당 하려면 로컬 함수를 사용할 수 있는 정적 분석을 수행할 수 있습니다. 다음 예제를 고려해 보세요.

```csharp
bool M()
{
    int y;
    Local();
    return y;

    void Local() => y = 0;
}
```

컴파일러는 했음을 확인할 수 `Local` 확실 하 게 할당 `y` 호출 합니다. 때문에 `Local` 전에 호출 됩니다는 `return` 문, `y` definitiely에서 할당 되며 모델의 `return` 문.

해당 분석을 사용 하는 분석에는 네 번째 차이 수 있습니다.
그 용도 따라 로컬 함수는 람다 식에 필요한 경우가 있는 힙 할당을 피할 수 있습니다. 로컬 함수는, 대리자에 게 변환 되지 않습니다 및 다른 람다 식 또는 대리자로 변환 되는 로컬 함수에 의해 캡처된 로컬 함수에 의해 캡처된 변수의 없음, 컴파일러 힙 할당을 피해갈 수 있습니다. 

다음 비동기 예제를 살펴보세요.

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

이 람다 식의 클로저에는 `address`, `index` 및 `name` 변수가 포함됩니다. 로컬 함수의 경우 클로저를 구현하는 개체는 `struct` 형식일 수 있습니다. 해당 구조체 형식의 로컬 함수에 참조로 전달 될 합니다. 구현에서 이러한 차이 할당에 저장 합니다.

람다 식에 필요한 인스턴스화 시간이 중요 한 코드 경로에 성능에 영향을 일 수 있는 추가 메모리 할당을 의미 합니다.
로컬 함수는 이러한 오버헤드를 유발하지 않습니다. 위의 예제에서 로컬 함수 버전은 람다 식 버전보다 할당 수가 2개 더 적습니다.

> [!NOTE]
> 이 메서드에 해당하는 로컬 함수는 클로저에 클래스도 사용합니다. 로컬 함수의 클로저가 `class` 또는 `struct`로 구현되는지 여부는 구현 세부 정보입니다. 로컬 함수는 `struct`를 사용할 수 있는 반면, 람다는 항상 `class`를 사용합니다.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

이 샘플에서 설명하지 않은 한 가지 최종 장점은 `yield return` 구문을 사용해서 로컬 함수를 반복기로 구현하여 값 시퀀스를 생성할 수 있다는 것입니다. `yield return` 문은 람다 식에 사용할 수 없습니다.

로컬 함수는 람다 식과 중복되는 것처럼 보일 수도 있지만, 실제로 다른 용도로 다르게 사용됩니다.
로컬 함수는 다른 메서드의 컨텍스트에서만 호출되는 함수를 작성하려는 경우에 더 효율적입니다.
