---
title: ".NET Core 배포 패키징"
description: "배포를 위해 .NET Core를 패키지하고 이름과 버전을 지정하는 방법에 관해 알아봅니다."
keywords: ".NET, .NET Core, 소스, 빌드"
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 71b9d722-c5a8-4271-9ce1-d87e7ae2494d
ms.openlocfilehash: 7ff5ed127ad0d4f435c697a8f35b33c7ba3b56ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-distribution-packaging"></a>.NET Core 배포 패키징

.NET Core를 점점 더 많은 플랫폼에서 사용할 수 있게 되므로 이를 패키지하고 이름과 버전을 지정하는 방법을 알아보는 것이 도움이 됩니다. 이를 통해 패키지 유지 관리자는 사용자가 .NET을 어디서 실행하든 상관없이 일관된 환경을 보장할 수 있습니다.

## <a name="net-core-components"></a>.NET Core 구성 요소

.NET Core는 패키지해야 하는 세 개의 주요 부분으로 구성됩니다.

1. **호스트**("muxer"라고도 함)는 런타임을 활성화하여 응용 프로그램을 시작하고 SDK를 활성화하여 명령을 보내는 두 가지의 고유한 역할을 가지고 있습니다. 호스트는 네이티브 실행 파일(`dotnet.exe`) 및 해당 지원 정책 라이브러리(`host/fxr`에 설치됨)입니다. 호스트는 [`dotnet/core-setup`](https://github.com/dotnet/core-setup/) 리포지토리의 코드에서 작성됩니다. 엄격한 요구 사항은 아니지만, 일반적으로 특정 컴퓨터에는 하나의 호스트만 존재합니다.
2. **프레임워크**는 런타임 및 관리되는 지원 라이브러리로 구성됩니다. 프레임워크는 응용 프로그램의 일부로 설치하거나 여러 응용 프로그램에서 다시 사용할 수 있는 중앙 위치의 공유 프레임워크로 설치할 수 있습니다. 임의 개수의 공유 프레임워크가 특정 컴퓨터에 설치되어 있을 수 있습니다. 공유 프레임워크는 `shared/Microsoft.NETCore.App/<version>` 아래에 있습니다. 호스트는 패치 버전 간에 롤포워드됩니다. 응용 프로그램이 `Microsoft.NETCore.App` 1.0.0을 대상으로 하지만 1.0.4만 있는 경우 앱이 1.0.4에 대해 실행됩니다.
3. **SDK**("도구"라고도 함)는 .NET Core 라이브러리 및 응용 프로그램을 작성하고 빌드하는 데 사용할 수 있는 관리되는 도구 집합입니다. SDK에는 CLI, MSBuild, 관련 빌드 작업 및 대상, NuGet, 새 프로젝트 템플릿 등이 포함됩니다. 컴퓨터에 여러 SDK가 있을 수 있지만(예: 명시적으로 이전 버전을 요구하는 프로젝트 빌드), 출시된 최신 도구를 사용하는 것이 좋습니다.

## <a name="recommended-package-names"></a>권장 패키지 이름

다음 지침은 패키지 이름에 대한 권장 사항입니다. 패키지 유지 관리자는, 대상으로 하는 특정 배포의 기존 방식이 다른 경우 등 여러 가지 이유에 따라 다른 옵션을 선택할 수 있습니다.

### <a name="minimum-package-set"></a>최소 패키지 집합

* `dotnet-runtime-[major].[minor]`: 지정된 버전의 공유 프레임워크(패키지 관리자에서는 지정된 주+부 조합의 최신 패치 버전만 사용 가능해야 함). **종속성**: `dotnet-host`
* `dotnet-sdk`: 최신 SDK. **종속성**: 최신 `dotnet-sdk-[major].[minor]`.
* `dotnet-sdk-[major].[minor]`: 지정된 버전의 SDK. 지정된 버전은 포함된 공유 프레임워크 중 최고 포함 버전이므로 사용자가 SDK를 공유 프레임워크에 쉽게 연결할 수 있습니다. **종속성**: `dotnet-host`, 하나 이상의 `dotnet-runtime-[major].[minor]`(런타임 중 하나는 SDK 코드 자체에 의해 사용되며 나머지는 사용자가 빌드하고 실행하는 데 사용됨).
* `dotnet-host`: 최신 호스트

#### <a name="preview-versions"></a>미리 보기 버전

패키지 유지 관리자는 공유 프레임워크 및 SDK의 미리 보기 버전을 포함하도록 결정할 수 있습니다. 버전이 지정되지 않은 `dotnet-sdk` 패키지에 이들을 포함해서는 안 되지만, 이름의 주 버전 및 부 버전 섹션에 추가 미리 보기 마커를 추가하여 버전이 지정된 패키지로서 릴리스할 수 있습니다. 예를 들어 `dotnet-sdk-2.0-preview-final` 패키지가 있을 수 있습니다.

### <a name="optional-additional-packages"></a>선택적인 추가 패키지

일부 유지 관리자는 다음과 같은 추가 패키지를 제공하도록 선택할 수 있습니다.

* `dotnet-lts`: 공유 프레임워크의 최신 LTS(장기 지원) 버전. [LTS 및 현재 릴리스 트레인](~/docs/core/versions/lts-current.md)은 .NET Core가 출시될 때 서로 다른 주기에 해당합니다. 사용자는 업데이트 빈도에 따라 원하는 트레인을 채택할 수 있습니다. 이것은 지원 수준과 연결된 개념이므로 고려 중인 배포판에 따라 해당하지 않을 수도 있습니다.

## <a name="disk-layout"></a>디스크 레이아웃

.NET Core 패키지를 설치할 때 디스크에서 해당 대상의 상대 위치가 중요합니다.
`dotnet.exe` 호스트는 버전이 지정된 `dotnet-sdk` SDK 패키지의 내용 및 `dotnet-runtime` 공유 프레임워크 패키지가 포함된 `sdk` 및 `shared` 폴더 옆에 배치해야 합니다.

패키지 내 파일 및 디렉터리의 디스크 레이아웃은 버전이 지정됩니다. 즉, 최신 `dotnet-runtime`으로 업데이트하면 새 버전이 이전 버전과 나란히 설치되므로, 패키지를 업데이트하여 기존 응용 프로그램의 손상 가능성을 줄일 수 있습니다. 패키지 업데이트로 인해 이전 버전이 제거되지 않아야 합니다.

## <a name="update-policies"></a>업데이트 정책

`update`가 수행되면 각 패키지는 다음과 같이 작동합니다.

* `dotnet-runtime-[major].[minor]`: 새 패치 버전은 패키지를 업데이트하지만 새 주 버전 또는 부 버전은 별도의 패키지입니다.
* `dotnet-sdk`: `update`가 주 버전, 부 버전 및 패치 버전을 롤포워드합니다.
* `dotnet-sdk-[major].[minor]`: 새 패치 버전은 패키지를 업데이트하지만 새 주 버전 또는 부 버전은 별도의 패키지입니다.
* `dotnet-lts`: `update`가 주 버전, 부 버전 및 패치 버전을 롤포워드합니다.

이 항목에서는 .NET Core 패키징 권장 사항을 제시했지만, 각 배포판에서 언제 어떤 버전을 제공할지 자유롭게 선택할 수 있습니다. 예를 들어 최신성보다 안정성을 중시하는 배포판에서는 LTS 릴리스 트레인으로 스냅하는 버전만 릴리스할 수 있습니다.