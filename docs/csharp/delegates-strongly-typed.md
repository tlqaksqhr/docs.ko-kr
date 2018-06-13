---
title: 강력한 형식의 대리자
description: 대리자가 필요한 기능을 만들 때 제네릭 대리자 형식을 사용하여 사용자 지정 형식을 선언하는 방법을 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: 2e4cc1c7bfa0aaa90f3aaefa0da64c5486a9d10f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215166"
---
# <a name="strongly-typed-delegates"></a>강력한 형식의 대리자

[이전](delegate-class.md)

이전 문서에서는 `delegate` 키워드를 사용하여 특정 대리자 형식을 만드는 것을 확인했습니다. 

추상 대리자 클래스는 느슨한 결합 및 호출을 위한 인프라를 제공합니다. 대리자 개체에 대한 호출 목록에 추가되는 메서드에 대해 형식 안정성을 도입하고 적용하면 구체적인 대리자 형식이 훨씬 더 유용해집니다. `delegate` 키워드를 사용하고 구체적인 대리자 형식을 정의하면 컴파일러에서 해당 메서드를 생성합니다.

실제로 이렇게 하면 다른 메서드 시그니처가 필요할 때마다 새로운 대리자 형식이 생성됩니다. 일정 시간이 지나면 이 작업은 지루해질 수 있습니다. 모든 새 기능에는 새 대리자 형식이 필요합니다.

다행히도 반드시 필요하지는 않습니다. .NET Core 프레임워크에는 대리자 형식이 필요할 때마다 재사용할 수 있는 여러 가지 형식이 포함되어 있습니다. 이러한 형식은 [제네릭](programming-guide/generics/index.md) 정의이므로 새 메서드 선언이 필요할 때 사용자 지정을 선언할 수 있습니다. 

이러한 형식 중 첫 번째는 <xref:System.Action> 형식이며 여러 가지 변형이 있습니다.

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

제네릭 형식 인수에 대한 `in` 한정자는 공변성(Covariance)에 대한 문서에서 설명합니다.

<xref:System.Action%6016> 같이 최대 16개의 인수가 포함된 `Action` 대리자의 변형이 있습니다.
이러한 정의에서는 각 대리자 인수에 대해 서로 다른 제네릭 인수를 사용하여 최대한의 유연성을 제공합니다. 메서드 인수는 같은 형식일 필요가 없지만 같은 형식일 수 있습니다.

void 반환 형식을 갖는 대리자 형식에 대해 `Action` 형식 중 하나를 사용합니다.

또한 프레임워크에는 값을 반환하는 대리자 형식에 사용할 수 있는 여러 가지 제네릭 대리자 형식이 포함됩니다.

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

결과 제네릭 형식 인수에 대한 `out` 한정자는 공변성(Covariance)에 대한 문서에서 설명합니다.

<xref:System.Func%6017> 같이 최대 16개의 입력 인수가 포함된 `Func` 대리자의 변형이 있습니다.
규칙에 따라 결과의 형식은 모든 `Func` 선언에서 항상 마지막 형식 매개 변수입니다.

값을 반환하는 모든 대리자 형식에 대해 `Func` 형식 중 하나를 사용합니다.

또한 단일 값에 대한 테스트를 반환하는 대리자에 대해 특수화된 <xref:System.Predicate%601> 형식이 있습니다.

```csharp
public delegate bool Predicate<in T>(T obj);
```

모든 `Predicate` 형식에 대해 구조적으로 동일한 `Func` 형식이 있다는 것을 알 수 있습니다. 예를 들면 다음과 같습니다.

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

이러한 두 형식이 동일하다고 생각할 수 있습니다. 그러나 동일하지 않습니다.
이러한 두 변수는 서로 교환해서 사용할 수 없습니다. 한 형식의 변수에 다른 형식을 할당할 수 없습니다. C# 형식 시스템에서는 구조체가 아니라 정의된 형식의 이름을 사용합니다.

.NET Core 라이브러리의 이러한 모든 대리자 형식 정의는 대리자가 필요한 새 기능에 대해 새 대리자 형식을 정의할 필요가 없음을 의미해야 합니다. 이러한 제네릭 정의는 대부분의 상황에서 필요한 모든 대리자 형식을 제공해야 합니다. 필수 형식 매개 변수를 사용하여 이러한 형식 중 하나를 인스턴스화할 수 있습니다. 제네릭으로 만들 수 있는 알고리즘의 경우 이러한 대리자를 제네릭 형식으로 사용할 수 있습니다. 

그러면 시간이 절약되고 대리자로 작업하기 위해 만들어야 하는 새로운 형식 수가 최소화됩니다.

다음 문서에서는 실제로 대리자로 작업하기 위한 몇 가지 일반적인 패턴이 표시됩니다.

[다음](delegates-patterns.md)
