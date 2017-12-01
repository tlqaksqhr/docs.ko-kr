---
title: "C# 7.2의 새로운 기능"
description: "C# 7.2에 대 한 새로운 기능의 개요입니다."
keywords: "C# 언어 디자인, 7.2, Visual Studio 2017 년"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a>C# 7.2의 새로운 기능

C# 7.2는 다양 한 유용한 기능을 추가 하는 다른 지점 릴리스입니다.
이 릴리스에 대 한 하나의 테마는 불필요 한 복사본 또는 할당을 방지 하 여 값 형식으로 보다 효율적으로 작업은 합니다. 

나머지 기능은 작은, 순위가 멋진 기능을 보여 줍니다.

사용 하 여 C# 7.2는 [언어 버전 선택](csharp-7-1.md#language-version-selection) 컴파일러 언어 버전을 선택 하는 구성 요소입니다.

이 릴리스의 새 언어 기능은 다음과 같습니다.

* [값 형식과 참조 의미 체계가](#reference-semantics-with-value-types)
  - 값 형식 참조 의미 체계가 사용 하 여 작업에 사용할 수 있는 구문 기능 향상의 조합입니다.
* [비 후행 명명 된 인수](#non-trailing-named-arguments)
  - 명명 된 인수를 위치 인수 올 수 있습니다.
* [숫자 리터럴에서 선행 밑줄이](#leading-underscores-in-numeric-literals)
  - 숫자 리터럴을 수 있는 인쇄 숫자 하기 전에 선행 밑줄이 생깁니다.
* [`private protected`액세스 한정자](#private-protected)
  - `private protected` 액세스 한정자를 사용 하면 동일한 어셈블리의 파생된 클래스에 대 한 액세스.

## <a name="reference-semantics-with-value-types"></a>값 형식과 참조 의미 체계가

7.2에 도입 된 언어 기능에는 참조 의미 체계가 사용 하는 동안 값 형식과 함께 사용할 수 있습니다. 복사 값 형식은 참조 형식 사용과 관련 된 메모리 할당을 발생 시 키 지 않고 최소화 하 여 성능을 향상 시키기 위해 설계 되었습니다. 기능은 다음과 같습니다.

 - `in` 매개 변수를 인수로 참조로 전달 있지만 호출된 된 메서드에 의해 수정 되지 않음을 지정 하는 한정자입니다.
 - `ref readonly` 한정자 메서드가 반환 되 면 메서드는 참조로 값을 반환한 있지만 해당 개체에 대 한 쓰기를 허용 하지 않습니다.
 - `readonly struct` 구조체는 변경할 수 있으며 변수로 전달 해야 나타내기 위해 선언 된 `in` 매개 변수는 멤버 메서드를 합니다.
 - `ref struct` 선언이 표시 되는 구조체 형식의 관리 되는 메모리에 직접 액세스 항상 스택 할당 해야 합니다.

이러한 모든 요소에 대 한 자세한 정보를 변경 읽을 수 [값 형식을 사용 하 여 참조 의미론을 통해](../reference-semantics-with-value-types.md)합니다.

## <a name="non-trailing-named-arguments"></a>비 후행 명명 된 인수

이제 메서드 호출 명명 된 인수는 올바른 위치에 배치 하는 경우 위치 인수 앞에 있는 명명 된 인수를 사용할 수 있습니다. 자세한 내용은 참조 [명명 된 인수와 선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)합니다.

## <a name="leading-underscores-in-numeric-literals"></a>숫자 리터럴에서 선행 밑줄이

자릿수 구분 기호에 C# 7.0에 대 한 지원 구현을 허용 하지 않습니다는 `_` 리터럴 값의 첫 번째 문자 수입니다. 16 진수 및 숫자 리터럴을 이진 수로 시작 이제는 `_`합니다. 

예:

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

새 복합 액세스 한정자를 마지막으로,: `private protected` 같은 어셈블리에 선언 된 파생된 클래스에서 구성원을 액세스할 수 있음을 의미 합니다. 반면 `protected internal` 동일한 어셈블리에 있는 클래스 또는 파생된 클래스에서 액세스할 수 있도록 `private protected` 동일한 어셈블리에 선언 된 파생된 형식에 대 한 액세스를 제한 합니다.

자세한 내용은 참조 [액세스 한정자](../language-reference/keywords/access-modifiers.md) 언어 참조에서.
