---
title: "dotnet-install 스크립트 | Microsoft 문서"
description: ".NET Core CLI 도구 및 공유 런타임을 설치하는 dotnet-install 스크립트에 대해 알아봅니다."
keywords: "dotnet-install, dotnet-install 스크립트, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
translationtype: Human Translation
ms.sourcegitcommit: 4a1f0c88fb1ccd6694f8d4f5687431646adbe000
ms.openlocfilehash: fbc1ce8d864a5c2150c61f4b8bf7cb8544921634
ms.lasthandoff: 03/22/2017

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

설치에 대한 소스 채널을 지정합니다. 값은 `future`, `preview` 및 `production`입니다. 기본값은 `production`입니다.

`-Version <VERSION>`

설치할 CLI의 버전을 지정합니다. 버전은 세 부분으로 구성된 버전(예: 1.0.0-13232)으로 지정해야 합니다. 생략하면 `version` 속성을 포함하는 첫 번째 [global.json](global-json.md)으로 기본 설정됩니다. 없으면 최신 버전을 사용합니다.

`-InstallDir <DIRECTORY>`

설치 경로를 지정합니다. 디렉터리가 없을 경우 만듭니다. 기본값은 *%LocalAppData%\.dotnet*입니다.

`-Architecture <ARCHITECTURE>`

설치할 .NET Core 바이너리의 아키텍처입니다. 가능한 값은 `auto`, `x64` 및 `x86`입니다. 기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `auto`입니다.

`-SharedRuntime`

설정되면 이 스위치는 설치를 공유 런타임으로 제한합니다. 전체 SDK가 설치되지는 않습니다.

`-DebugSymbols`(참고 참조)

설정된 경우 설치 관리자가 설치에 디버깅 기호를 포함합니다.

> [!NOTE]
> `-DebugSymbols` 스위치는 현재 사용할 수 없지만 향후 릴리스에 포함될 예정입니다.

`-DryRun`

설정된 경우 스크립트에서 설치를 수행하지는 않지만 대신 현재 요청된 버전의 .NET CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다. 예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다. 또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.

`-NoPath`

설정된 경우 현재 세션에 대한 경로로 접두사/installdir을 내보내지 않습니다. 기본적으로 스크립트는 경로를 수정하여, 설치 후 CLI 도구를 즉시 사용할 수 있게 만듭니다.

`-AzureFeed`

설치 관리자에 대한 Azure 피드의 URL을 지정합니다. 이 값은 변경하는 것이 좋습니다. 기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.

`-ProxyAddress`

설정된 경우 설치 관리자에서 웹 요청을 만들 때 프록시를 사용합니다.

### <a name="bash-macoslinux"></a>Bash(Linux/macOS)

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

`--channel <CHANNEL>`

설치에 대한 소스 채널을 지정합니다. 값은 `future`, `dev` 및 `production`입니다. 기본값은 `production`입니다.

`--version <VERSION>`

설치할 CLI의 버전을 지정합니다. 버전은 세 부분으로 구성된 버전(예: 1.0.0-13232)으로 지정해야 합니다. 생략하면 `version` 속성을 포함하는 첫 번째 [global.json](global-json.md)으로 기본 설정됩니다. 없으면 최신 버전을 사용합니다.

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

설정된 경우 스크립트에서 설치를 수행하지는 않지만 대신 현재 요청된 버전의 .NET CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다. 예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다. 또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.

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
