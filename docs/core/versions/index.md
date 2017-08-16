---
title: ".NET Core 버전 관리"
description: ".NET Core 버전 관리의 작동 방식을 이해합니다."
author: bleroy
ms.author: mairaw
ms.date: 08/10/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f6f684b1-1d2c-4105-8376-7c1959e23803
ms.translationtype: HT
ms.sourcegitcommit: 3a25c1c3b540bac8ef963a8bbf708b0700c3e9e2
ms.openlocfilehash: 94614e436734389df7bf3a6e2df2abe49593021a
ms.contentlocale: ko-kr
ms.lasthandoff: 08/12/2017

---
# <a name="net-core-versioning"></a>.NET Core 버전 관리

.NET Core는 [NuGet 패키지](../packages.md), 도구 및 하나의 단위로 배포되는 프레임워크로 구성됩니다. 각 플랫폼 계층에 대해 개별적으로 버전 관리가 가능하므로 보다 나은 유연성을 이용할 수 있습니다. 그 점과 관련하여 버전 관리 유연성도 중요하지만 제품을 더 쉽게 이해하기 위해 플랫폼의 버전을 하나의 단위로 관리하려고 할 수 있습니다.

이 문서에서는 .NET Core SDK 및 런타임 버전이 어떻게 관리되는지에 대해 명확히 설명합니다.

.NET Core에는 독립적으로 버전 관리가 이루어지는 작동 부분이 많습니다. 그러나 .NET Core 2.0부터는 최상위 버전 번호를 이해하기 쉬우므로 “.NET Core”의 버전임을 누구나 알 수 있습니다. 이 문서의 나머지 부분에서는 모든 부품의 버전 관리에 대해 구체적으로 설명합니다. 패키지 관리자인 경우에는 이러한 세부 정보가 중요할 수 있습니다.

## <a name="versioning-details"></a>버전 관리 정보

.NET Core 2.0부터는 다운로드 파일 이름에 단일 버전 번호가 표시됩니다. 다음 버전 번호가 통합되었습니다.

* 공유 프레임워크 및 관련된 런타임
* .NET Core SDK 및 관련된 .NET Core CLI
* `Microsoft.NETCore.App` 메타패키지

단일 버전 번호를 사용하면 어떤 버전의 SDK를 사용자의 개발 컴퓨터에 설치해야 할지 그리고 프로덕션 환경이 프로비전되는 시점에 공유 프레임워크의 해당 버전이 무엇이 되어야 할지를 보다 쉽게 알 수 있습니다. SDK 또는 런타임을 다운로드할 때 표시되는 버전 번호가 동일하게 됩니다.

### <a name="installers"></a>설치 관리자

.NET Core 2.0부터는 [일별 빌드](https://github.com/dotnet/core-setup#daily-builds) 및 [Microsoft 릴리스](https://www.microsoft.com/net/download/core)의 다운로드가 보다 이해하기 쉬운 새 명명 체계를 따릅니다.
이 다운로드의 설치 관리자 UI는 설치되는 구성 요소의 이름과 버전을 명확히 제공하도록 수정되었습니다. 특히 제목은 다운로드의 파일 이름에 있는 것과 동일한 버전 번호를 표시합니다.

#### <a name="file-name-format"></a>파일 이름 형식

`[product]-[component]-[major].[minor].[patch]-[previewN]-[optional build #]-[rid].[file ext]`

다음은 이 형식의 몇 가지 예제입니다.

```
dotnet-runtime-2.0.4-macos.10.12-x64.pkg            # Mac runtime installer
dotnet-sdk-2.0.4-win10-x64.exe                      # Windows SDK installer
dotnet-sdk-2.0.4-fedora.24-x64.tar.gz               # Fedora 24 binary archive

#Ubuntu file set needed for the SDK
dotnet-host-2.0.4-ubuntu.16.04-x64.deb              # Host / muxer and host policy
dotnet-runtime-2.0.4-ubuntu.16.04-x64.deb           # runtime
dotnet-sdk-2.0.4-ubuntu.16.04-x64.deb               # SDK tools
```

형식은 읽기가 가능하며, 다운로드하는 내용, 그 버전 그리고 어디에 사용할 수 있는지를 명확히 보여 줍니다. 런타임 패키지 이름에는 `runtime`이 포함되며 SDK에는 `SDK`가 포함됩니다.

#### <a name="ui-string-format"></a>UI 문자열 형식

설치 관리자의 모든 웹 사이트 설명 및 UI 문자열은 일관적이고 정확하며 간단하게 유지됩니다. 다음 표는 몇 가지 예를 보여 줍니다.

| Installer | 창 제목                          | 설치 관리자의 다른 내용 | 설치된 기능                               |
| :--       | :--                                   | :--                        | :--                                             |
| SDK       | .NET Core 2.0 SDK(x64) 설치 관리자     | .NET Core 2.0.4 SDK        | .NET Core 2.0.4 도구 + .NET Core 2.0.4 런타임 |
| 런타임   | .NET Core 2.0 런타임(x64) 설치 관리자 | .NET Core 2.0.4 런타임    | .NET Core 2.0.4 런타임                         |

미리 보기 릴리스는 약간 다릅니다.

| Installer | 창 제목                                    | 설치 관리자의 다른 내용        | 설치된 기능                                                   |
| :--       | :--                                             | :--                               | :--                                                                 |
| SDK       | .NET Core 2.0 미리 보기 1 SDK(x64) 설치 관리자     | .NET Core 2.0.0 미리 보기 1 SDK     | .NET Core 2.0.0 미리 보기 1 도구 + .NET Core 2.0.0 미리 보기 1 런타임 |
| 런타임   | .NET Core 2.0 미리 보기 1 런타임(x64) 설치 관리자 | .NET Core 2.0.0 미리 보기 1 런타임 | .NET Core 2.0.0 미리 보기 1 런타임                                   |

SDK 릴리스에는 런타임 버전이 하나 이상 포함되어 있을 수 있습니다. 이 경우 설치 관리자 UX는 다음과 같습니다(SDK 버전만 표시되고 설치된 런타임 버전은 Windows 및 Mac에서 설치 프로세스의 끝에 있는 요약 페이지에 표시됩니다.).

| Installer | 창 제목                      | 설치 관리자의 다른 내용                                   | 설치된 기능                                                         |
| :--       | :--                               | :--                                                          | :--                                                                       |
| SDK       | .NET Core 2.1 SDK(x64) 설치 관리자 | .NET Core 2.1.1 SDK <br> .NET Core 2.1.1 런타임 <br> .NET Core 2.0.6 런타임 | .NET Core 2.1.1 도구 + .NET Core 2.1.1 런타임 + .NET Core 2.0.6 런타임 |

.NET Core 도구를 런타임 변경 없이 업데이트해야 할 수도 있습니다. 이 경우 SDK 버전이 예를 들어 2.1.2로 높아지면 다음에 출시될 때 런타임이 이에 따라 높아집니다(즉, 런타임과 SDK가 2.1.3으로 출시됨).

### <a name="package-managers"></a>패키지 관리자

Microsoft가 아닌 엔터티가 .NET Core를 배포할 수 있습니다. 특히 Linux 배포 소유자 및 패키지 유지 관리자가 .NET Core 패키지를 그들의 패키지 관리자에 추가할 수 있습니다. 해당 패키지의 이름 지정 및 버전 관리 방법에 대한 권장 사항을 보려면 [.NET Core 배포 패키징](../build/distribution-packaging.md)을 참조하세요.

#### <a name="minimum-package-set"></a>최소 패키지 집합

* `dotnet-runtime-[major].[minor]`: 지정된 버전의 런타임(패키지 관리자에서는 지정된 주+부 조합의 최신 패치 버전만 사용 가능해야 함). 새 패치 버전은 패키지를 업데이트하지만 새 주 버전 또는 부 버전은 별도의 패키지입니다.
 
  **종속성**: `dotnet-host`

* `dotnet-sdk`: 최신 SDK. `update`는 주 버전, 부 버전 및 패치 버전을 롤포워드합니다.

  **종속성**: 최신 `dotnet-sdk-[major].[minor]`.

* `dotnet-sdk-[major].[minor]`: 지정된 버전의 SDK. 지정된 버전은 포함된 공유 프레임워크 중 최고 포함 버전이므로 사용자가 SDK를 공유 프레임워크에 쉽게 연결할 수 있습니다. 새 패치 버전은 패키지를 업데이트하지만 새 주 버전 또는 부 버전은 별도의 패키지입니다.

  **종속성**: `dotnet-host`, 하나 이상의 `dotnet-runtime-[major].[minor]`(런타임 중 하나는 SDK 코드 자체에 의해 사용되며 나머지는 사용자가 빌드하고 실행하는 데 사용됨).

* `dotnet-host`: 최신 호스트

##### <a name="preview-versions"></a>미리 보기 버전

패키지 유지 관리자는 런타임 및 SDK의 미리 보기 버전을 포함하도록 결정할 수 있습니다. 버전이 지정되지 않은 `dotnet-sdk` 패키지에 이러한 미리 보기 버전을 포함해서는 안 되지만, 이름의 주 버전 및 부 버전 섹션에 추가 미리 보기 마커를 추가하여 버전이 지정된 패키지로서 릴리스할 수 있습니다. 예를 들어 `dotnet-sdk-2.0-preview-1-final` 패키지가 있을 수 있습니다.

### <a name="docker"></a>Docker

일반 Docker 태그 명명 규칙은 버전 번호를 구성 요소 이름 앞에 놓는 것입니다. 이 규칙을 계속 사용할 수 있습니다. 현재 태그는 다음과 같이 런타임 버전만 포함합니다.

* 1.0.8-runtime
* 1.0.8-sdk
* 2.0.4-runtime
* 2.0.4-sdk
* 2.1.1-runtime
* 2.1.1-sdk

런타임 대신 SDK 버전을 나타내기 위해 SDK 태그를 업데이트해야 합니다.

.NET Core 도구를 수정해야 하지만 기존의 런타임을 다시 출시해야 할 수도 있습니다. 이 경우 SDK 버전이 예를 들어 2.1.2로 높아지면 다음에 출시될 때 런타임이 이에 따라 높아집니다(즉, 런타임과 SDK가 2.1.3으로 출시됨).

## <a name="semantic-versioning"></a>유의적 버전

.NET Core는 [유의적 버전(SemVer)](http://semver.org/)을 사용하여 `MAJOR.MINOR.PATCH` 버전 관리를 사용하고 버전 번호의 다양한 부분으로 변경의 수준 및 종류를 설명합니다.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

선택적 `PRERELEASE` 및 `BUILDNUMBER` 부분은 지원되는 버전의 일부가 되지 않으며, 소스 대상에서 로컬로 빌드되는 야간 빌드 및 지원되지 않는 미리 보기 릴리스에만 존재합니다.

### <a name="how-version-numbers-are-incremented"></a>버전 번호는 어떻게 높아지나요?

다음 경우에는 `MAJOR`가 증가합니다.
  - 이전 버전이 더 이상 지원되지 않는 경우
  - 기존 종속성의 최신 `MAJOR` 버전이 채택된 경우
  - 호환성 쿼크의 기본 설정이 “off”로 변경된 경우

다음 경우에는 `MINOR`가 증가합니다.
  - 공용 API 노출 영역이 추가된 경우
  - 새 동작이 추가된 경우
  - 기존 종속성의 최신 `MINOR` 버전이 채택된 경우
  - 새 종속성이 도입된 경우
  
다음 경우에는 `PATCH`가 증가합니다.
  - 버그 수정이 이루어진 경우
  - 최신 플랫폼에 대한 지원이 추가된 경우
  - 기존 종속성의 최신 `PATCH` 버전이 채택된 경우
  - 이전의 경우와 맞지 않는 다른 변경 사항이 있는 경우

여러 가지 변경이 이루어진 경우에는 개별 변경의 영향을 받는 가장 높은 요소가 증가되고 다음은 0으로 다시 설정됩니다. 예를 들어 `MAJOR`가 증가하면 `MINOR` 및 `PATCH`는 0으로 다시 설정됩니다. `MINOR`가 증가하면 `PATCH`는 0으로 다시 설정되지만 `MAJOR`는 변경되지 않습니다.

### <a name="preview-versions"></a>미리 보기 버전

미리 보기 버전에는 `-preview-[number]-([build]|"final")`이 추가됩니다. 예를 들어, `2.0.0-preview-1-final`을 입력합니다.

### <a name="lts-vs-current"></a>LTS 및 Current

.NET Core에는 Long Term Support(LTS) 및 Current의 두 가지 릴리스 학습이 있습니다. 사용자는 원하는 안정성 수준과 새 기능을 선택할 수 있으며 지원은 계속 이루어집니다.

- LTS를 이용하면 새로운 기능을 얻는 빈도가 적더라도 더 안정적인 플랫폼을 이용할 수 있습니다. 또한 LTS의 지원 기간이 더 깁니다.
- Current를 이용하면 새 기능과 API를 더 자주 얻을 수 있지만 업데이트를 설치할 수 있는 시간 창이 더 짧고 그러한 업데이트가 보다 자주 이루어진다는 단점이 있습니다. 또한 Current는 전체가 지원되지만 지원 기간은 LTS보다 짧습니다.

“Current” 버전을 LTS로 승격시킬 수도 있습니다.

“LTS” 및 “Current”는 관련된 지원 수준에 대한 문을 작성하기 위해 특정 릴리스에 넣을 레이블로 간주해야 합니다.

자세한 내용은 [.NET Core 지원 수명 주기 팩트 시트](https://www.microsoft.com/net/core/support)를 참조하세요.

## <a name="versioning-scheme-details"></a>버전 관리 체계 세부 정보

.NET core는 다음 부분으로 구성됩니다.

- 호스트(muxer라고도 함): `hostfxr` 정책 라이브러리를 포함한 `dotnet.exe`
- SDK(개발자의 컴퓨터에 필요하지만 프로덕션에는 필요하지 않은 도구 집합)
- 런타임
- 패키지로 배포되는 공유 프레임워크 구현. 특히 패치 버전 관리의 경우 각 패키지 버전을 독립적으로 관리합니다.
- 세분화된 패키지를 버전이 있는 단위로 참조하는 선택적 [메타패키지](../packages.md) 집합. 메타패키지는 패키지와 별도로 버전 관리할 수 있습니다.

.NET Core에는 버전 번호가 증가함에 따라 점점 커지는 API 집합을 나타내는 대상 프레임워크 집합(예를 들어 `netstandard` 또는 `netcoreapp`)도 포함됩니다.

### <a name="net-standard"></a>.NET Standard

.NET Standard는 `MAJOR.MINOR` 버전 관리 체계를 사용해 왔습니다. `PATCH` 수준은 덜 빈번하게 반복되며 실제 구현과 동일한 버전 관리 요건을 제시하지 않는 계약 집합을 표현하므로 .NET Standard에 유용하지 않습니다.

.NET Standard 버전과 .NET Core 버전 간에는 실제 결합이 없습니다. .NET Core 2.0은 .NET Standard 2.0을 구현하기도 하지만 향후 .NET Core 버전이 동일한 .NET Standard 버전으로 매핑된다는 보장은 없습니다. .NET Core는 .NET Standard에 의해 정의되지 않는 API를 출시하므로 새 .NET Standard 없이 새로운 버전을 출시할 수도 있습니다. .NET Standard는 그 개시는 .NET Core와 일치했다 하더라도 .NET Framework 또는 Mono 등의 다른 대상에 적용되는 개념이기도 합니다.

### <a name="packages"></a>패키지

라이브러리 패키지는 독립적으로 발전하고 버전 관리됩니다. .NET Framework System.\* 어셈블리와 겹치는 패키지는 일반적으로 .NET Framework 4.x 버전 관리(기록 선택)를 지원하는 4.x 버전을 사용합니다. .NET Framework 라이브러리(예: [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata))와 겹치지 않는 패키지는 일반적으로 1.0에서 시작하여 증가합니다.

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library)에 설명된 패키지는 플랫폼의 맨 아래에 있기 때문에 특별하게 처리됩니다.

`NETStandard.Library` 패키지는 해당 패키지 간에 구현 수준 종속성이 있기 때문에 일반적으로 집합으로 버전 관리됩니다.

### <a name="metapackages"></a>메타패키지

.NET Core 메타패키지에 대한 버전 관리는 해당 메타패키지의 일부인 .NET Core 버전을 기반으로 합니다.

예를 들어 .NET Core 2.1.3의 메타패키지의 `MAJOR` 및 `MINOR` 버전 번호는 모두 2.1이어야 합니다.

메타패키지의 패치 버전은 참조된 패키지가 업데이트될 때마다 증가합니다. 패치 버전에는 업데이트된 프레임워크 버전이 포함되지 않습니다. 결과적으로 메타패키지의 버전 관리 체계에서는 기본 패키지의 변경 수준을 나타내지 않고 주로 API 수준을 나타내기 때문에 메타패키지는 엄격하게 SemVer 규격이 아닙니다. 

현재 .NET Core에 대한 주 메타패키지는 두 가지가 있습니다.

**Microsoft.NETCore.App**

- .NET Core 1.0 기준 v1.0(이러한 버전은 일치함).
- `netcoreapp` 프레임워크에 매핑됩니다.
- .NET Core 배포의 패키지를 설명합니다.

참고: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility)는 .NET의 이전 .NET Standard 구현과의 호환이 가능하도록 하기 위해 존재하는 다른 .NET Core 메타패키지입니다. 이것은 특정 프레임워크에 매핑되지 않으므로 패키지처럼 버전 관리합니다.

**NETStandard.Library**

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library)는 [.NET Standard](../../standard/library.md)의 일부인 라이브러리를 설명합니다. .NET Standard를 지원하는 모든 .NET 구현(예: .NET Framework, .NET Core 및 Mono)에 적용됩니다.

### <a name="target-frameworks"></a>대상 프레임워크

대상 프레임워크 버전은 새 API가 추가될 때 업데이트됩니다. 이러한 버전은 구현 관련 사항이 아닌 API 셰이프를 나타내므로 패치 버전에 대한 개념이 없습니다. 주 버전 및 부 버전 관리는 이전에 지정한 SemVer 규칙을 따르며 이를 구현하는 .NET Core 배포의 `MAJOR` 및 `MINOR` 번호와 일치합니다.

## <a name="versioning-in-practice"></a>실제 버전 관리

.NET Core를 다운로드하면 다운로드한 파일 이름에 버전이 추가됩니다(예: `dotnet-sdk-2.0.4-win10-x64.exe`).

GitHub의 .NET Core 리포지토리에는 매일 많은 라이브러리의 새로운 빌드를 생성하는 커밋 및 끌어오기 요청이 있습니다. .NET Core의 모든 변경 내용에 대해 새로운 공개 버전을 만드는 것은 실용적이지 않습니다. 대신 확정적이지 않은 일정 기간(예: 주 또는 월) 동안 변경 내용을 집계한 후 .NET Core의 안정적인 새 공개 버전을 만듭니다.

.NET Core의 새 버전은 다음과 같은 여러 가지를 의미할 수 있습니다.

- 패키지 및 메타패키지의 새 버전.
- 새 API의 추가를 가정하는 다양한 프레임워크의 새 버전.
- .NET Core 배포의 새 버전.

### <a name="shipping-a-patch-release"></a>패치 릴리스 전달

버전 2.0.0과 같은 주요 .NET Core 릴리스를 전달한 후 버그를 수정하고 성능 및 안정성을 개선하기 위해 .NET Core 라이브러리에 대해 패치 수준 변경을 수행합니다. 따라서 새로운 API는 도입되지 않습니다. 다양한 메타패키지가 업데이트된 .NET Core 라이브러리 패키지를 참조하도록 업데이트됩니다. 메타패키지는 패치 업데이트로 버전 관리됩니다(`MAJOR.MINOR.PATCH`). 대상 프레임워크는 패치 릴리스의 일부로 업데이트되지 않습니다. 새 .NET Core 배포는 `Microsoft.NETCore.App` 메타패키지와 일치하는 버전 번호로 릴리스됩니다.

### <a name="shipping-a-minor-release"></a>부 릴리스 전달

증가된 `MAJOR` 버전 번호를 가진 .NET Core 버전을 전달한 후에는 새 시나리오를 이용할 수 있도록 새로운 API가 .NET Core 라이브러리에 추가됩니다. 다양한 메타패키지가 업데이트된 .NET Core 라이브러리 패키지를 참조하도록 업데이트됩니다. 메타패키지는 `MAJOR` 및 `MINOR` 버전 번호가 새 프레임워크 버전과 일치하는 패치 업데이트로 버전 관리됩니다. 새 `MAJOR.MINOR` 버전의 새로운 대상 프레임워크 이름이 새로운 API를 설명하기 위해 추가됩니다(예: `netcoreapp2.1`). 새로운 .NET Core 배포가 `Microsoft.NETCore.App` 메타패키지와 일치하는 버전 번호로 릴리스됩니다.

### <a name="shipping-a-major-release"></a>주 릴리스 전달

.NET Core의 새로운 주 버전이 출시될 때마다 `MAJOR` 버전 번호는 증가하고 `MINOR` 버전 번호는 0으로 다시 설정됩니다. 새 주 버전에는 이전의 주 버전 이후 부 릴리스에 의해 추가된 모든 API가 포함됩니다. 새 주 버전은 중요한 새 시나리오를 사용하도록 설정해야 하며 이전 플랫폼에 대한 지원을 삭제할 수도 있습니다.

다양한 메타패키지가 업데이트된 .NET Core 라이브러리 패키지를 참조하도록 업데이트됩니다. [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) 메타패키지 및 `netcore` 대상 프레임워크는 새 릴리스의 `MAJOR` 버전 번호와 일치하는 주 업데이트로 버전 관리됩니다.

## <a name="see-also"></a>참고 항목
[대상 프레임워크](../../standard/frameworks.md)   
[.NET Core 배포 패키징](../build/distribution-packaging.md)   
[.NET Core 지원 수명 주기 팩트 시트](https://www.microsoft.com/net/core/support)   
[.NET Core 2+ 버전 바인딩](https://github.com/dotnet/designs/issues/3)   

