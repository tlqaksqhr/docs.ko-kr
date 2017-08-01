---
title: "dotnet 설치 스크립트"
description: ".NET Core CLI 도구 및 공유 런타임을 설치하는 dotnet-install 스크립트에 대해 알아봅니다."
keywords: "dotnet-install, dotnet-install 스크립트, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 07/10/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8af168e96f8f5b57626b126135d8b5e509fbb059
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-install-scripts-reference"></a>dotnet-install 스크립트 참조

## <a name="name"></a>이름

`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core CLI(명령줄 인터페이스) 도구 및 공유 런타임을 설치하는 데 사용되는 스크립트입니다.

## <a name="synopsis"></a>개요

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DebugSymbols] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress]`

macOS/Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

## <a name="description"></a>설명

`dotnet-install` 스크립트는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. [CLI GitHub 리포지토리](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain)에서 스크립트를 다운로드할 수 있습니다. 

이러한 스크립트의 주요 유용성은 자동화 시나리오 및 비관리자 설치입니다. 두 가지 스크립트가 있습니다. 하나는 Windows에서 작동하는 PowerShell 스크립트입니다. 또 다른 스크립트는 Linux/OS X에서 작동하는 bash 스크립트입니다. 두 스크립트 모두 동일하게 동작합니다. 또한 bash 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 PowerShell 스위치를 사용할 수 있습니다. 

설치 스크립트는 CLI 빌드 저장 위치에서 ZIP/tarball 파일을 다운로드하여 기본 위치나 `-InstallDir|--install-dir`로 지정한 위치에 설치를 계속 진행합니다. 기본적으로 설치 스크립트는 SDK를 다운로드하고 설치합니다. 공유 런타임만 가져오려는 경우 `--shared-runtime` 인수를 지정합니다. 

기본적으로 스크립트는 현재 세션에 대한 $PATH에 설치 위치를 추가합니다. `--no-path` 인수를 지정하여 이 기본 동작을 재정의합니다. 

스크립트를 실행하기 전에 필요한 모든 [종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 설치하세요.

`--version` 인수를 사용하여 특정 버전을 설치할 수 있습니다. 버전은 세 부분으로 구성된 버전(예: 1.0.0-13232)으로 지정해야 합니다. 생략하면 스크립트가 호출된 폴더 위의 계층 구조에서 검색된, `version` 속성을 포함하는 첫 번째 [global.json](global-json.md) 파일로 기본 설정됩니다. 없으면 최신 버전을 사용합니다.

또한 이 스크립트를 사용하면 `--debug` 인수를 사용하여 디버그 기호와 함께 SDK 또는 공유 런타임 디버그 이진 파일을 가져올 수 있습니다. 처음 설치할 때 이 작업을 수행하지 못하고 나중에 디버그 기호가 필요하다는 사실을 알게 되면 `--debug` 인수와 설치한 SDK 버전으로 스크립트를 다시 실행하여 디버그 기호를 얻을 수 있습니다. 

## <a name="options"></a>옵션

참고: 옵션은 스크립트 구현에 따라 다릅니다. 

### <a name="powershell-windows"></a>PowerShell(Windows)

`-Channel <CHANNEL>`

설치에 대한 소스 채널을 지정합니다. 가능한 값은 다음과 같습니다.

- `Current` - 현재 릴리스
- `LTS` - 장기 지원 채널(현재 지원되는 릴리스)
- 특정 릴리스를 나타내는 X.Y 형식의 두 부분으로 된 버전(예: `2.0` 또는 `1.0`)
- 분기 이름[예: `master` 분기에서 온 최신 값의 경우 `release/2.0.0`, `release/2.0.0-preview2` 또는 `master`("bleeding edge" 야간 릴리스)]

기본값은 `LTS`입니다. .NET 지원 채널에 대한 자세한 내용은 [.NET Core 지원 주기](https://www.microsoft.com/net/core/support) 항목을 참조하세요.

`-Version <VERSION>`

소스 채널의 빌드 버전을 나타냅니다(`-Channel` 옵션 참조). 가능한 값은 다음과 같습니다.

- `latest` - 채널의 최신 빌드
- `coherent` - 채널의 일관된 최신 빌드, 안정적인 최신 패키지 조합 사용
- 특정 빌드 버전을 나타내는 X.Y.Z 형식의 세 부분으로 구성된 버전(예: 패치 버전을 나타내는 `x`가 있는 `1.0.x` 또는 `2.0.0-preview2-006120`과 같은 특정 빌드)

생략하면 `-Version`은 `version` 멤버를 포함하는 첫 번째 [global.json](global-json.md)으로 기본 설정됩니다. 이것이 존재하지 않을 경우 `-Version`은 `latest`로 기본 설정됩니다.

`-InstallDir <DIRECTORY>`

설치 경로를 지정합니다. 디렉터리가 없을 경우 만듭니다. 기본값은 *%LocalAppData%\.dotnet*입니다. 이진 파일은 디렉터리에 직접 배치됩니다.

`-Architecture <ARCHITECTURE>`

설치할 .NET Core 바이너리의 아키텍처입니다. 가능한 값은 `auto`, `x64` 및 `x86`입니다. 기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `auto`입니다.

`-SharedRuntime`

설정되면 이 스위치는 설치를 공유 런타임으로 제한합니다. 전체 SDK가 설치되지는 않습니다.

`-DebugSymbols`(참고 참조)

설정된 경우 설치 관리자가 설치에 디버깅 기호를 포함합니다.

> [!NOTE]
> `-DebugSymbols` 스위치는 현재 사용할 수 없지만 향후 릴리스에 포함될 예정입니다.

`-DryRun`

설정된 경우 스크립트에서 설치를 수행하지는 않지만 대신 현재 요청된 버전의 .NET Core CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다. 예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다. 또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.

`-NoPath`

설정된 경우 현재 세션에 대한 경로로 접두사/installdir을 내보내지 않습니다. 기본적으로 스크립트는 경로를 수정하여, 설치 후 CLI 도구를 즉시 사용할 수 있게 만듭니다.

`-AzureFeed`

설치 관리자에 대한 Azure 피드의 URL을 지정합니다. 이 값은 변경하는 것이 좋습니다. 기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.

`-ProxyAddress`

설정된 경우 설치 관리자에서 웹 요청을 만들 때 프록시를 사용합니다.

### <a name="bash-macoslinux"></a>Bash(Linux/macOS)

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

`-Channel <CHANNEL>`

설치에 대한 소스 채널을 지정합니다. 가능한 값은 다음과 같습니다.

- `Current` - 현재 릴리스
- `LTS` - 장기 지원 채널(현재 지원되는 릴리스)
- 특정 릴리스를 나타내는 X.Y 형식의 두 부분으로 된 버전(예: `2.0` 또는 `1.0`)
- 분기 이름[예: `master` 분기에서 온 최신 값의 경우 `release/2.0.0`, `release/2.0.0-preview2` 또는 `master`("bleeding edge" 야간 릴리스)]

기본값은 `LTS`입니다. .NET 지원 채널에 대한 자세한 내용은 [.NET Core 지원 주기](https://www.microsoft.com/net/core/support) 항목을 참조하세요.

`-Version <VERSION>`

소스 채널의 빌드 버전을 나타냅니다(`-Channel` 옵션 참조). 가능한 값은 다음과 같습니다.

- `latest` - 채널의 최신 빌드
- `coherent` - 채널의 일관된 최신 빌드, 안정적인 최신 패키지 조합 사용
- 특정 빌드 버전을 나타내는 X.Y.Z 형식의 세 부분으로 구성된 버전(예: 패치 버전을 나타내는 `x`가 있는 `1.0.x` 또는 `2.0.0-preview2-006120`과 같은 특정 빌드)

생략하면 `-Version`은 `version` 멤버를 포함하는 첫 번째 [global.json](global-json.md)으로 기본 설정됩니다. 이것이 존재하지 않을 경우 `-Version`은 `latest`로 기본 설정됩니다.

`--install-dir <DIRECTORY>`

설치 경로를 지정합니다. 디렉터리가 없을 경우 만듭니다. 기본값은 `$HOME/.dotnet`입니다.

`--architecture <ARCHITECTURE>`

설치할 .NET Core 바이너리의 아키텍처입니다. 가능한 값은 `auto`, `x64` 및 `amd64`입니다. 기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `auto`입니다.

`--shared-runtime`

설정되면 이 스위치는 설치를 공유 런타임으로 제한합니다. 전체 SDK가 설치되지는 않습니다.

`--debug-symbols`

설정된 경우 설치 관리자가 설치에 디버깅 기호를 포함합니다.

> [!NOTE]
> 이 스위치는 현재 사용할 수 없지만 향후 릴리스에 포함될 예정입니다.

`--dry-run`

설정된 경우 스크립트에서 설치를 수행하지는 않지만 대신 현재 요청된 버전의 .NET Core CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다. 예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다. 또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.

`--no-path`

설정된 경우 현재 세션에 대한 경로로 접두사/installdir을 내보내지 않습니다. 기본적으로 스크립트는 경로를 수정하여, 설치 후 CLI 도구를 즉시 사용할 수 있게 만듭니다.

`--verbose`

진단 정보를 표시합니다.

`--azure-feed`

설치 관리자에 대한 Azure 피드의 URL을 지정합니다. 이 값은 변경하는 것이 좋습니다. 기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.

`--help`

스크립트에 대한 도움말을 출력합니다.

## <a name="examples"></a>예제

기본 위치에 최신 개발 버전을 설치합니다.

Windows:

`./dotnet-install.ps1 -Channel Future`

macOS/Linux:

`./dotnet-install.sh --channel Future`

지정된 위치에 최신 미리 보기를 설치합니다.

Windows:

`./dotnet-install.ps1 -Channel preview -InstallDir C:\cli`

macOS/Linux:

`./dotnet-install.sh --channel preview --install-dir ~/cli`

## <a name="see-also"></a>참고 항목

[.NET Core 릴리스](https://github.com/dotnet/core/releases)   
[.NET Core 런타임 및 SDK 다운로드 아카이브](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)

