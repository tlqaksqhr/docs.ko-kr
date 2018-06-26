---
title: C# 언어 버전 선택 - C# 가이드
description: 특정 컴파일러 버전을 사용하여 구문 유효성 검사를 수행하도록 컴파일러 구성
ms.date: 05/24/2018
ms.openlocfilehash: 2056a99544d0cac94bc7cc79e8cd8793b1bcff78
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566369"
---
# <a name="select-the-c-language-version"></a>C# 언어 버전 선택

C# 컴파일러는 기본적으로 릴리스된 언어의 최신 주 버전을 사용합니다. 언어의 새 포인트 릴리스를 사용하여 모든 프로젝트를 컴파일하도록 선택할 수 있습니다. 최신 버전의 언어를 선택하면 프로젝트에서 최신 언어 기능을 사용할 수 있습니다. 다른 시나리오에서는 이전 버전의 언어를 사용할 때 프로젝트가 깨끗하게 컴파일되는지 확인해야 할 수 있습니다.

이 기능은 개발 환경에서 SDK 및 도구의 새 버전을 설치하는 결정과 프로젝트의 새 언어 기능을 통합하는 결정을 분리합니다. 빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다. 각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.

언어 버전을 설정하는 여러 가지 방법이 있습니다.

- [Visual Studio 빠른 작업](#visual-studio-quick-action)에 의존합니다.
- [Visual Studio UI](#set-the-language-version-in-visual-studio)에서 언어 버전을 설정합니다.
- [**.csproj** 파일](#edit-the-csproj-file)을 수동으로 편집합니다.
- [하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.
- [`-langversion` 컴파일러 옵션](#set-the-langversion-compiler-option)을 구성합니다.

## <a name="visual-studio-quick-action"></a>Visual Studio 빠른 작업

Visual Studio를 사용하면 필요한 언어 버전을 확인할 수 있습니다. 현재 구성된 버전에 사용할 수 없는 언어 기능을 사용하는 경우, Visual Studio는 프로젝트의 언어 버전을 업데이트하는 잠재적 수정을 보여 줍니다.

## <a name="set-the-language-version-in-visual-studio"></a>Visual Studio에서 언어 버전 설정

Visual Studio에서 버전을 설정할 수 있습니다. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **빌드** 탭을 선택하고 **고급** 단추를 선택합니다. 드롭다운에서 버전을 선택합니다. 다음 이미지는 "최신" 설정을 보여 줍니다.

![언어 버전을 지정할 수 있는 고급 빌드 설정의 스크린샷](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> Visual Studio IDE를 사용하여 csproj 파일을 업데이트하는 경우 IDE는 각 빌드 구성에 대한 별도 노드를 만듭니다. 일반적으로 모든 빌드 구성에서 값을 동일하게 설정하지만 각 빌드 구성에 대해 명시적으로 설정하거나 이 설정을 수정하는 경우 "모든 구성"을 선택해야 합니다. csproj 파일에 다음이 표시됩니다.
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a>csproj 파일 편집

**.csproj** 파일에서 언어 버전을 설정할 수 있습니다. 다음과 같은 요소를 추가합니다.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

`latest` 값은 C# 언어의 최신 부 버전을 사용합니다. 올바른 값은 다음과 같습니다.

|값|의미|
|------------|-------------|
|default|컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.|
|ISO-1|컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다. |
|ISO-2|컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다. |
|3|컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.|
|4|컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.|
|5|컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.|
|6|컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.|
|7|컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.|
|7.1|컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.|
|7.2|컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.|
|7.3|컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.|
|latest|컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다.|

특수한 문자열 `default` 및 `latest`는 각각 빌드 컴퓨터에 설치된 최신 주(C# 7.0) 및 부(C# 7.3) 언어 버전을 확인합니다.

## <a name="configure-multiple-projects"></a>여러 프로젝트 구성

`<LangVersion>` 요소를 포함하는 **Directory.build.props** 파일을 생성하여 여러 디렉터리를 구성할 수 있습니다. 일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다. 솔루션 디렉터리의 **Directory.build.props** 파일에 다음을 추가합니다.

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

이제 해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 C# 버전 7.3 구문을 사용합니다. 자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build.md)에 대한 문서를 참조하세요.

## <a name="set-the-langversion-compiler-option"></a>langversion 컴파일러 옵션 설정

`-langversion` 명령줄 옵션을 사용할 수 있습니다. 자세한 내용은 [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) 컴파일러 옵션에 대한 문서를 참조하세요. `csc -langversion:?`을 입력하면 유효한 값 목록을 볼 수 있습니다.
