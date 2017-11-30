---
title: "C# 7.1의 새로운 기능"
description: "C# 7.1에 새로운 기능의 개요입니다."
keywords: "C# 언어 디자인, 7.1, Visual Studio 2017 년"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a>C# 7.1의 새로운 기능

C# 7.1은 첫 번째 포인트 릴리스는 C# 언어입니다. 언어는 증가 된 릴리스 일정을 표시합니다. 사용할 수 있습니다의 새로운 기능 일찍 이상적으로 각 새로운 기능으로 준비 하는 경우. C# 7.1 지정 된 버전의 언어와 일치 하도록 컴파일러를 구성 하는 기능을 추가 합니다. 언어 버전을 업그레이드 하에서 도구를 업그레이드 하는 결정을 구분할 수 있도록 하는 합니다.

C# 7.1 추가 [언어 버전 선택](#language-version-selection) 구성 요소, 세 개의 새로운 언어 기능 및 새 컴파일러 동작입니다.

이 릴리스의 새 언어 기능은 다음과 같습니다.

* [`async``Main` 메서드](#async-main)
  - 응용 프로그램에 대 한 진입점을 가질 수 있습니다는 `async` 한정자입니다.
* [`default`리터럴 식](#default-literal-expressions)
  - 대상 형식을 유추할 수 하는 경우 기본 값 식에 기본 리터럴 식을 사용할 수 있습니다.
* [유추 된 튜플 요소 이름](#inferred-tuple-element-names)
  - 튜플 요소의 이름은 대부분의 경우에서 튜플 초기화에서 유추할 수 있습니다.

마지막으로, 컴파일러에 두 가지 옵션이 `/refout` 및 `/refonly` 제어 하는 [참조 어셈블리를 생성](#reference-assembly-generation)합니다.

## <a name="language-version-selection"></a>언어 버전 선택

C# 컴파일러는 Visual Studio 2017 15.3, 버전 또는.NET Core SDK 2.0부터 C# 7.1을 지원 합니다. 그러나 7.1 기능은 기본적으로 되어 있습니다. 7.1 기능을 사용 하려면 프로젝트에 대 한 언어 버전 설정을 변경 해야 합니다.

Visual Studio에서 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 선택 된 **빌드** 탭을 선택한는 **고급** 단추입니다. 드롭다운 목록에서 선택 **C# 최신 부 버전 (최신)**, 또는 특정 버전 **C# 7.1** 이미지 다음과 같이 합니다. `latest` 값 현재 컴퓨터에 최신 부 버전을 사용 하려는 것을 의미 합니다. `C# 7.1` 최신 부 버전은 출시 후에 C# 7.1, 사용 하려는 있다는 것을 의미 합니다.

![언어 버전을 설정합니다.](./media/csharp-7-1/advanced-build-settings.png)

또는 "csproj" 파일을 편집 하 고 추가 하거나 다음 줄을 수정할 수 있습니다.

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Csproj 파일을 업데이트 하려면 Visual Studio IDE를 사용 하는 경우 IDE는 각 빌드 구성에 대 한 별도 노드를 만듭니다. 일반적으로 설정 값 같은 모든 빌드 구성에 있지만이 설정을 수정 하는 경우 "모든 구성"을 선택 하거나 각 빌드 구성에 대 한 명시적으로 설정 해야 합니다. 다음 csproj 파일에 표시 됩니다.

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

에 대 한 올바른 설정을 `LangVersion` 요소는:

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

특수 한 문자열 `default` 및 `latest` 각각 빌드 컴퓨터에 설치 된 최신 주 및 부 언어 버전을 확인 합니다.

이 설정은 분리는 프로젝트에 새 언어 기능을 통합 하 여 개발 환경에서 새 버전의 SDK 및 도구를 설치 합니다. 빌드 컴퓨터에서 최신 SDK 및 도구를 설치할 수 있습니다. 각 프로젝트의 빌드에 대 한 특정 버전의 언어를 사용 하도록 구성할 수 있습니다.

## <a name="async-main"></a>비동기 주

*비동기 주* 메서드를 사용 하면 `await` 에 프로그램 `Main` 메서드.
이전에 작성 해야 합니다.

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

이제 다음을 작성할 수 있습니다.

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

경우 프로그램이 종료 코드는 반환 하지 않는 선언할 수 있습니다는 `Main` 반환 하는 메서드는 <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

읽어볼 수 있는에서 세부 정보에 대 한는 [비동기 주](../programming-guide/main-and-command-args/index.md) 프로그래밍 설명서의에서 항목입니다.

## <a name="default-literal-expressions"></a>기본 리터럴 식

기본 리터럴 식이 모두 기본값 식의 향상 된 기능입니다.
이러한 식은 기본 값으로 변수를 초기화합니다. 여기서 이전에 씁니다.

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

이제 초기화는 오른쪽에서 유형의 생략할 수 있습니다.

```csharp
Func<string, bool> whereClause = default;
```

이 기능은 C# 프로그래밍 가이드 항목에 대해 자세히 알아볼 수 있습니다 [값 식 기본](../programming-guide/statements-expressions-operators/default-value-expressions.md)합니다.

이 향상 된이 기능 변경에 대 한 구문 분석 규칙 중 일부는 [default 키워드](../language-reference/keywords/default.md)합니다.

## <a name="inferred-tuple-element-names"></a>유추 된 튜플 요소 이름

이 기능은 C# 7.0에 도입 된 튜플 기능에는 작은 향상 기능에 설명 합니다. 여러 번 튜플을 초기화할 때 할당의 오른쪽에 사용 되는 변수 동일 튜플 요소에 대 한 원하는 이름으로 합니다.

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

튜플 요소의 이름은 C# 7.1 튜플에서 초기화 하는 데 변수에서 유추할 수 있습니다.

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

이 기능에 대해 자세히 알아볼 수 있습니다는 [튜플](../tuples.md) 항목입니다.

## <a name="reference-assembly-generation"></a>참조 어셈블리를 생성

생성 하는 두 개의 새 컴파일러 옵션 가지가 *참조 전용 어셈블리*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) 및 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)합니다.
링크 된 항목에는 이러한 옵션과 참조 어셈블리 보다 자세히 설명합니다.
