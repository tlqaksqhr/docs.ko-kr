---
title: "값 형식과 참조 의미 체계가"
description: "안전 하 게 복사 구조를 최소화 하는 언어 기능 이해"
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9eeaf201c1f5a58044db62e356199b609c4c035a
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="reference-semantics-with-value-types"></a>값 형식과 참조 의미 체계가

값 형식을 사용 하 여 힙 할당을 종종 방지 하는 것입니다.
해당 단점은 값으로 복사 됩니다. 이러한 상충 관계를 사용 하면 많은 양의 데이터에서 작동 하는 알고리즘을 최적화 하기 어렵습니다. C# 7.2의 새로운 언어 기능 값 형식과 참조로 전달 의미 체계를 사용할 수 있는 메커니즘을 제공 합니다. 현명 하 게 이러한 기능을 사용 하는 경우에 할당을 모두를 최소화 하 고 복사 작업 수 있습니다. 이 문서는 새로운 기능을 탐색합니다.

이 문서의 예제 코드의 대부분 C# 7.2에 추가 된 기능을 보여 줍니다. 이러한 기능을 사용 하려면 프로젝트에 C# 7.2 또는 그 이후 버전을 사용 하도록 프로젝트를 구성 해야 합니다. Visual Studio를 사용할 수 있습니다. 각 프로젝트에 대 한 선택 **프로젝트** 다음 메뉴에서 **속성**합니다. 선택 된 **빌드** 탭을 클릭 **고급**합니다. 여기에서 언어 버전을 구성할 수 있습니다. "7.2" 또는 "최신" 중 하나를 선택 합니다.  편집할 수도 있습니다는 *csproj* 파일을 다음 노드를 추가 합니다.

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

값에 대 한 "7.2" 또는 "최신" 중 하나를 사용할 수 있습니다.

## <a name="specifying-in-parameters"></a>지정 `in` 매개 변수

추가 하는 C# 7.2는 `in` 기존 보완 하기 위해 키워드 `ref` 및 `out` 키워드 참조로 인수를 전달 하는 메서드를 작성 하는 경우. `in` 키워드 지정 된 매개 변수를 전달 하는 참조에 의해 호출된 된 메서드에 전달 된 값을 수정 하지 않습니다. 

이 추가 디자인 의도 표현 하는 전체 어휘를 제공 합니다. 값 형식에는 다음 한정자 중 하나를 지정 하지 않을 경우 호출 메서드에 전달 될 때 복사 됩니다. 이러한 한정자의 각 값 형식이 전달 되도록 참조에 의해 복사 방지를 지정 합니다. 각 한정자 다른 목적에 따라 표시:

- `out`:이 메서드는이 매개 변수로 사용 되는 인수 값을 설정 합니다.
- `ref`:이 메서드는이 매개 변수로 사용 되는 인수의 값을 설정할 수 있습니다.
- `in`:이 메서드는이 매개 변수로 사용 되는 인수 값을 수정 하지 않습니다.

추가 하는 경우는 `in` 한정자 참조로 인수를 전달 하려면 디자인 의도 불필요 한 복사를 방지 하기 위해 참조로 인수를 전달 하는 것을 선언 합니다. 해당 인수로 사용 되는 개체를 수정 하지 않을 수도 있습니다. 다음 코드에서는 3D 공간에서 두 점 사이의 거리를 계산 하는 방법의 예를 보여 줍니다. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

인수는 각각 세 개의 double 값을 포함 하는 두 개의 구조. Double 8 바이트 이므로 각 인수는 24 바이트. 지정 하 여는 `in` 컴퓨터의 아키텍처에 따라 이러한 인수에 대 한 4 바이트 또는 8 바이트 참조를 전달 한정자입니다. 크기의 차이 크지 있지만 응용 프로그램 여러 다른 값을 사용 하 여 루프에서이 메서드를 호출 하면 신속 하 게 추가할 수 있습니다.
 
`in` 한정자 보완 `out` 및 `ref` 다른 방식에서입니다. 만 시에도 다른 메서드의 오버 로드를 만들 수 없습니다 `in`, `out` 또는 `ref`합니다. 이러한 새 규칙에 대해 정의 된 항상 동일한 동작 확장 `out` 및 `ref` 매개 변수입니다.

`in` 한정자 매개 변수를 사용 하는 멤버에 적용 될 수 있습니다: 메서드, 대리자, 람다 식, 로컬 함수, 인덱서, 연산자입니다.

와 달리 `ref` 및 `out` 인수에 리터럴 값 또는 상수에 대해 사용할 수에 대 한 인수는 `in` 매개 변수입니다. 또한 달리는 `ref` 또는 `out` 매개 변수를 적용할 필요 하지 않습니다는 `in` 호출 사이트에서 한정자입니다. 다음 코드에서는 호출의 두 가지 예는 `CalculateDistance` 메서드. 첫 번째 참조로 전달 하는 두 개의 지역 변수를 사용 합니다. 두 번째 메서드 호출의 일부로 만들어진 임시 변수를 포함 합니다. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

여러 가지 방법으로는 컴파일러 되도록의 읽기 전용 특성은 `in` 인수에 적용 됩니다.  호출된 된 메서드가에 직접 할당할 수 없습니다는 우선,는 `in` 매개 변수입니다. 모든 필드에 직접 할당할 수 없습니다는 `in` 매개 변수입니다. 또한 전달할 수 없습니다는 `in` 요구 되는 모든 메서드 매개 변수는 `ref` 또는 `out` 한정자입니다.
있는 경우 컴파일러는는 `in` 인수는 읽기 전용 변수입니다. 통과-값 의미 체계를 사용 하는 인스턴스 메서드를 호출할 수 있습니다. 이러한 경우,의 복사본은 `in` 매개 변수가 생성 됩니다. 컴파일러에 대 한 임시 변수를 만들 수 있으므로 `in` 매개 변수를 하나에 대 한 기본값을 지정할 수도 있습니다 `in` 매개 변수입니다. 다음 코드는이 사용 하 여 두 번째 요소에 대 한 값을 기본값으로 원점 (0, 0 지점)를 지정 하려면:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

`in` 매개 변수 지정 또한 참조 형식에 사용 하거나 숫자 값에서 빌드된 수 있습니다. 그러나 두 경우 모두 이점은 있는 경우에 최소 있습니다.

## <a name="ref-readonly-returns"></a>`ref readonly`반환

값 형식을 참조로 반환 하지만 해당 값을 수정할 수 없도록 호출자를 허용 하지 않습니다 수도 있습니다. 사용 된 `ref readonly` 디자인 의도 표현 하는 한정자입니다. 기존 데이터에 대 한 참조를 반환 하지만 수정을 허용 하지 않습니다는 판독기를 알립니다. 

경우 컴파일러는 호출자가 참조를 수정할 수 없습니다. 값에 직접 지정 하 려 컴파일 타임 오류를 생성 합니다. 그러나 컴파일러는 멤버 메서드 구조체의 상태를 수정 하는 경우 알 수 없습니다.
개체가 수정 되지 않습니다을 보장 하려면 컴파일러 복사본을 만들고 해당 복사본을 사용 하 여 참조 멤버를 호출 합니다. 모든 수정 내용은 해당 방어 복사본에 됩니다. 

가능성이 사용 하 여 라이브러리 `Point3D` 원본 코드를 통해 자주 사용 합니다. 모든 인스턴스에 스택에 새 개체를 만듭니다. 상수를 만들고 참조로 반환 하는 것이 도움이 수도 있습니다. 그러나 내부 저장소에 대 한 참조를 반환 하는 경우 수 적용 하려는 호출자에 게 참조 된 저장소를 수정할 수 없습니다. 다음 코드를 반환 하는 읽기 전용 속성 정의 `readonly ref` 에 `Point3D` 출처를 지정 하는 합니다.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

반환 ref 읽기 전용 복사본을 만드는 것은 쉽습니다: 방금로 선언 되지 변수에 할당할는 `ref readonly` 한정자입니다. 컴파일러는 할당의 일부로 개체를 복사 하는 코드를 생성 합니다. 

변수를 할당 하면는 `ref readonly return`를 하나만 지정할 수 있습니다는 `ref readonly` 변수 또는 읽기 전용 참조의 값으로 복사:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

위의 코드에서 첫 번째 할당의 복사본을 만듭니다는 `Origin` 상수와 복사 할당 합니다. 두 번째에 대 한 참조를 할당합니다. 에 `readonly` 한정자에는 변수 선언의의 일부 여야 합니다. 참조 하는 참조를 수정할 수 없습니다. 이렇게 하면 컴파일 타임 오류가 발생 합니다.

## <a name="readonly-struct-type"></a>`readonly struct` 형식

적용 `ref readonly` 를 한 구조체의 트래픽이 높은 사용 충분할 수 있습니다.
그 결과 변경할 수 없는 구조체를 만들어야 할 수 있습니다. 항상 읽기 전용 참조로 전달할 수 있습니다 그런 다음. 로 사용 되는 구조체의 메서드를 액세스 하는 경우 발생 하는 복사 연습 방어를 제거 하는 `in` 매개 변수입니다.

만들면 할 수는 `readonly struct` 유형입니다. 추가할 수는 `readonly` 구조체 선언에는 한정자입니다. 구조체의 모든 멤버가 되는 경우 컴파일러는 `readonly`; `struct` 변경 하지 않아야 합니다.

에 대 한 다른 최적화는는 `readonly struct`합니다. 사용할 수는 `in` 한정자를 모든 위치에서 있는 `readonly struct` 인수입니다. 또한 반환할 수 있습니다는 `readonly struct` 로 `ref return` 수명이 개체를 반환 하는 메서드 범위에 해당 하는 개체 반환 합니다.

멤버를 호출 하는 경우 컴파일러에서 보다 효율적인 코드를 생성 하는 마지막으로, 한 `readonly struct`:는 `this` 수신기의 복사본 대신 참조는 항상는 `in` 매개 변수는 멤버 메서드를 참조로 전달 합니다. 이 최적화를 사용 하는 경우 더 많은 복사 저장는 `readonly struct`합니다. `Point3D` 이 변경에 대 한 훌륭한 후보입니다. 다음 코드에서는 업데이트 된 `ReadonlyPoint3D` 구조:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>`ref struct` 형식

다른 관련 된 언어 기능 스택에 할당 해야 하는 값 형식을 선언할 수 있다는 점입니다. 즉, 이러한 형식은 되지 만들 수 있습니다 힙에 다른 클래스의 구성원으로. 이 기능에 대 한 기본 동기를 <xref:System.Span%601> 및 관련 구조입니다. <xref:System.Span%601>포함할 수 있습니다 관리 되는 포인터 해당 멤버 중 하나로 다른 되는 범위의 길이입니다. C# 안전 하지 않은 컨텍스트 외부에서 관리 되는 메모리에 대 한 포인터를 지원 하지 않으므로 약간 다르게 구현 실제로 됩니다. 포인터와 길이 변경 하는 모든 쓰기 원자성있지 않습니다. 즉, 한 <xref:System.Span%601> 부족 범위 오류를 일으키는 것 또는 다른 형식 안전성을 위반 하는 단일 스택 프레임으로 제한 되지 않습니다. 또한 JIT 시 충돌 GC 힙에 일반적으로 관리 되는 포인터를 배치 합니다.

이와 비슷한 요구 사항을 사용 하 여 만든 메모리 작업을 할 수 있습니다 [ `stackalloc` ](language-reference/keywords/stackalloc.md) 메모리 interop Api에서 사용 하는 경우. 직접 정의할 수 `ref struct` 이러한 요구 사항에 대 한 형식입니다. 이 문서에 사용 하는 예제 표시 `Span<T>` 을 간소화 합니다.

`ref struct` 선언은 스택에이 형식의 구조체를 이어야 함을 선언 합니다. 언어 규칙에는 이러한 형식의 안전 하 게 보장합니다. 다른 형식으로 선언 `ref struct` 포함 <xref:System.ReadOnlySpan%601>합니다. 

보관의 목표는 `ref struct` 스택 할당 변수의 경우 컴파일러는 모두에 대 한 여러 가지 규칙을 소개 하는 대로 입력 `ref struct` 형식입니다.

- 상자 없습니다는 `ref struct`합니다. 할당할 수 없습니다는 `ref struct` 형식의 변수에 형식을 `object`, `dynamic`, 또는 임의의 인터페이스 형식입니다.
- 선언할 수 없습니다는 `ref struct` 클래스 또는 일반 구조체의 멤버로 합니다.
- 지역 변수를 선언할 수 없습니다 `ref struct` 비동기 메서드의 유형입니다. 반환 하는 동기 메서드를 선언할 수 있습니다 `Task`, `Task<T>` 또는 작업와 비슷한 형식입니다.
- 선언할 수 없습니다 `ref struct` 반복기에서 지역 변수입니다.
- 캡처할 수 없습니다 `ref struct` 람다 식 또는 로컬 함수에는 변수입니다.

이러한 제한 사항을 확인을 사용 하지 않는 실수로 `ref struct` 한 방식으로 관리 되는 힙에 승격할 수 없습니다.

## <a name="conclusions"></a>결론

이러한 향상 된 C# 언어에는 메모리 할당을 필요한 성능을 달성 하는 데 중요 한 될 수 있는 중요 한 알고리즘의 성능 설계 되었습니다. 작성 하는 코드에서 이러한 기능을 자주 사용 하지 않는 알 수 있습니다. 그러나 이러한 향상 된.NET Framework의 여러 위치에서 채택 된 합니다. 점점 더 많은 Api로 이러한 기능을 사용 하 여, 응용 프로그램의 성능을 향상 시킬 표시 됩니다.
