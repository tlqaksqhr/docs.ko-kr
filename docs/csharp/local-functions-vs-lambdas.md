---
title: "로컬 함수 및 람다 식"
description: "로컬 함수가 람다 식보다 더 적합한 선택일 수 있는 이유"
keywords: "C#, .NET, .NET Core, 최신 기능, 새로운 기능, 로컬 함수, 람다 식"
author: BillWagner
ms.author: wiwagn
ms.date: 10/27/2016
ms.topic: article
ms.prod: visual-studio-dev-15
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bba2a8d183f928e298c452f6ec132f3eb9dffbd3
ms.lasthandoff: 03/13/2017

---

### <a name="local-functions-compared-to-lambda-expressions"></a>로컬 함수 및 람다 식 비교

일부 사용 사례에서는 로컬 함수를 만들 필요 없이 람다 식을 만들어 사용할 수 있습니다. 해당 작업을 수행하는 예제 비동기 메서드는 다음과 같습니다.

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "람다 식을 사용하여 메서드를 반환하는 작업")]

그러나 람다 식을 정의 및 호출하는 것보다 로컬 함수를 사용하는 것이 더 나은 여러 가지 이유가 있습니다.

첫째, 람다 식의 경우 컴파일러가 클로저에 의해 캡처된 변수를 저장하기 위해 무명 클래스 및 해당 클래스의 인스턴스를 만들어야 합니다. 이 람다 식의 클로저에는 `address`, `index` 및 `name` 변수가 포함됩니다. 

둘째, 람다 식은 대리자를 인스턴스화하고 해당 대리자를 호출하여 구현됩니다. 로컬 함수는 메서드 호출로 구현됩니다.
람다 식에 필요한 인스턴스화는 추가 메모리 할당을 의미하며, 시간이 중요한 코드 경로에서 성능에 영향을 줄 수 있습니다.
로컬 함수는 이러한 오버헤드를 유발하지 않습니다.

셋째, 로컬 함수는 정의하기 전에 호출할 수 있습니다. 람다 식은 정의하기 전에 선언해야 합니다. 즉, 로컬 함수는 재귀 알고리즘에서 사용하기 쉽습니다.

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "로컬 함수를 사용하는 재귀 계승")]

람다 식을 사용하는 버전과 해당 구현을 비교해 보세요.

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "람다 식을 사용하는 재귀 계승")]

람다 식을 사용하는 버전은 람다 식 `nthFactorial`을 정의하기 전에 선언하고 초기화해야 합니다. 이렇게 하지 않으면 `nthFactorial`을 할당하기 전에 참조하여 컴파일 시간 오류가 발생합니다.
로컬 함수를 사용하면 재귀 알고리즘을 쉽게 만들 수 있습니다. 

로컬 함수는 람다 식과 중복되는 것처럼 보일 수도 있지만, 실제로 다른 용도로 다르게 사용됩니다.
로컬 함수는 다른 메서드의 컨텍스트에서만 호출되는 함수를 작성하려는 경우에 더 효율적입니다.


