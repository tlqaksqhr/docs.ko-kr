---
title: C# 7.1의 새로운 기능
description: C# 7.1의 새로운 기능에 대한 개요입니다.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a>C# 7.1의 새로운 기능

C# 7.1은 C# 언어에 대한 첫 번째 포인트 릴리스입니다. 언어에 대한 증가된 릴리스 일정을 표시합니다. 새로운 각 기능이 준비될 때 이상적으로 새 기능을 빨리 사용할 수 있습니다. C# 7.1은 지정된 버전의 언어와 일치하도록 컴파일러를 구성하는 기능을 추가합니다. 이를 통해 도구를 업그레이드하는 결정을 언어 버전을 업그레이드하는 결정에서 구분할 수 있습니다.

C# 7.1은 [언어 버전 선택](#language-version-selection) 구성 요소, 세 개의 새로운 언어 기능 및 새로운 컴파일러 동작을 추가합니다.

이 릴리스의 새로운 언어 기능은 다음과 같습니다.

* [`async` `Main`메서드](#async-main)
  - 응용 프로그램에 대한 진입점은 `async` 한정자를 가질 수 있습니다.
* [`default` 리터럴 식](#default-literal-expressions)
  - 대상 형식을 유추할 수 있는 경우 기본 값 식에서 기본 리터럴 식을 사용할 수 있습니다.
* [유추된 튜플 요소 이름](#inferred-tuple-element-names)
  - 튜플 요소의 이름은 대부분의 경우에 튜플 초기화에서 유추할 수 있습니다.

마지막으로 컴파일러에는 [참조 어셈블리 생성](#reference-assembly-generation)을 제어하는 두 가지 옵션 `/refout` 및 `/refonly`가 있습니다.

## <a name="language-version-selection"></a>언어 버전 선택

C# 컴파일러는 Visual Studio 2017 버전 15.3 또는 .NET Core SDK 2.0부터 C# 7.1을 지원합니다. 그러나 7.1 기능은 기본적으로 꺼져 있습니다. 7.1 기능을 활성화하려면 프로젝트에 대한 언어 버전 설정을 변경해야 합니다.

Visual Studio의 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **빌드** 탭을 선택하고 **고급** 단추를 선택합니다. 드롭다운 목록에서 **C# 최신 부 버전(최신 버전)** 또는 다음 그림과 같이 특정 버전 **C# 7.1**을 선택합니다. `latest` 값은 현재 컴퓨터에 최신 부 버전을 사용하려는 것을 의미합니다. `C# 7.1`은 최신 부 버전이 출시된 후에도 C# 7.1을 사용하려는 것을 의미합니다.

![언어 버전 설정](./media/csharp-7-1/advanced-build-settings.png)

또는 "csproj" 파일을 편집하고 다음 줄을 추가하거나 수정할 수 있습니다.

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Visual Studio IDE를 사용하여 csproj 파일을 업데이트하는 경우 IDE는 각 빌드 구성에 대한 별도 노드를 만듭니다. 일반적으로 모든 빌드 구성에서 값을 동일하게 설정하지만 각 빌드 구성에 대해 명시적으로 설정하거나 이 설정을 수정하는 경우 "모든 구성"을 선택해야 합니다. csproj 파일에 다음이 표시됩니다.

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

`LangVersion` 요소에 대한 올바른 설정은 다음과 같습니다.

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

특수한 문자열 `default` 및 `latest`는 각각 빌드 컴퓨터에 설치된 최신 주 및 부 언어 버전을 확인합니다.

이 설정은 개발 환경에서 SDK 및 도구의 새 버전 설치를 프로젝트의 새 언어 기능을 통합하는 선택에서 분리합니다. 빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다. 각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.

## <a name="async-main"></a>비동기 기본

*비동기 기본* 메서드를 통해 `Main` 메서드에서 `await`를 사용할 수 있습니다.
이전에 다음을 작성해야 했습니다.

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

프로그램이 종료 코드를 반환하지 않는 경우 <xref:System.Threading.Tasks.Task>를 반환하는 `Main` 메서드를 선언할 수 있습니다.

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

프로그래밍 가이드의 [비동기 기본](../programming-guide/main-and-command-args/index.md) 항목에서 세부 정보에 대해 자세히 읽어볼 수 있습니다.

## <a name="default-literal-expressions"></a>기본 리터럴 식

기본 리터럴 식은 기본값 식에 대한 향상된 기능입니다.
이러한 식은 변수를 기본 값으로 초기화합니다. 여기서 이전에 다음을 작성했습니다.

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

이제 초기화의 오른쪽에서 형식을 생략할 수 있습니다.

```csharp
Func<string, bool> whereClause = default;
```

[기본값 식](../programming-guide/statements-expressions-operators/default-value-expressions.md)의 C# 프로그래밍 가이드 항목에서 이 향상된 기능에 대해 자세히 알아볼 수 있습니다.

또한 이 향상된 기능은 [기본값 키워드](../language-reference/keywords/default.md)에 대한 일부 구문 분석 규칙을 변경합니다.

## <a name="inferred-tuple-element-names"></a>유추된 튜플 요소 이름

이 기능은 C# 7.0에 도입된 튜플 기능에 대한 작은 향상된 기능입니다. 여러 번 튜플을 초기화할 때 할당의 오른쪽에 사용되는 변수는 튜플 요소에 대해 원하는 이름과 동일합니다.

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

튜플 요소의 이름은 C# 7.1에서 튜플을 초기화하는 데 사용되는 변수에서 유추할 수 있습니다.

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

[튜플](../tuples.md) 항목에서 이 기능에 대해 자세히 알아볼 수 있습니다.

## <a name="reference-assembly-generation"></a>참조 어셈블리 생성

*참조 전용 어셈블리*인 [/refout](../language-reference/compiler-options/refout-compiler-option.md) 및 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)를 생성하는 두 개의 새로운 컴파일러 옵션이 있습니다.
링크된 항목에서는 이러한 옵션과 참조 어셈블리를 보다 자세히 설명합니다.
