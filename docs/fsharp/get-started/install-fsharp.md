---
title: 'F # 설치'
description: 'F #의 경우이 사용자 환경에 따라 설치 하는 방법에 알아봅니다.'
ms.date: 07/03/2018
ms.openlocfilehash: 142265a95e1d3ee1603a89f650a24c6a45709181
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878852"
---
# <a name="install-f"></a>F # 설치 #

설치할 수 있습니다 F # 여러 가지 방법으로 사용자 환경에 따라.

## <a name="install-f-with-visual-studio"></a>Visual Studio를 사용 하 여 F # 설치

다운로드 하는 경우 [Visual Studio](https://visualstudio.microsoft.com/) 처음으로이 먼저 설치는 Visual Studio 설치 관리자입니다. 설치 관리자에서 적절 한 SKU의 Visual Studio를 설치 합니다. 이미 있는 경우 설치를 클릭 **수정**합니다.

다음 워크 로드의 목록이 표시 됩니다. 선택 **ASP.NET 및 웹 개발**, F # 지원,.NET Core 지원 설치할지 및 ASP.NET Core에 대 한 지원 되는 F # 프로젝트입니다.

다음으로, 클릭 **수정** 오른쪽 아래에 있습니다.  그러면 선택한 모든 항목이 설치 됩니다. 클릭 하 여 F # 언어 지원과 Visual Studio 2017을 열고 다음 **시작**합니다.

## <a name="install-f-with-visual-studio-for-mac"></a>F # Visual Studio를 사용 하 여 Mac 용 설치

F #에서 기본적으로 설치 됩니다 [Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/), 어떤 구성에 관계 없이 선택 합니다.

설치가 완료 되 면 "Visual Studio 시작"을 선택 합니다. 또한 macOS에서 Finder를 통해 시작할 수도 있습니다.

## <a name="install-f-with-visual-studio-code"></a>Visual Studio Code를 사용 하 여 F # 설치

있어야 [설치 된 git가](https://git-scm.com/download) 되도록 경로에서 사용할 수 있습니다 Ionide 프로젝트 템플릿을 사용 합니다. 입력 하 여 제대로 설치 되었는지 확인할 수 있습니다 `git --version` 명령 프롬프트 및 키를 눌러 **Enter**합니다.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

다음을 사용 하 여 Ionide [Mono](http://www.mono-project.com)합니다. MacOS에서 Mono를 설치 하는 가장 쉬운 방법은 Homebrew 통해 됩니다. 터미널에 다음을 입력 하기만 하면 됩니다.

```console
brew install mono
```

또한 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

Linux에서 Ionide 또한 사용 하 여 [Mono](https://www.mono-project.com)합니다. Debian 또는 Ubuntu의 경우 다음을 사용할 수 있습니다.

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

또한 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Windows를 사용 하는 경우 수행 해야 합니다 [F # 지원을 사용 하 여 Visual Studio 설치](#install-f-with-visual-studio)합니다. 이 작성, 컴파일 및 F # 코드를 실행 하는 데 필요한 모든 구성 요소를 설치 합니다.

또한 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.

---

해야 [Visual Studio Code](https://code.visualstudio.com) 설치 합니다.

그런 다음 확장 아이콘 및 "Ionide"에 대 한 검색을 클릭 합니다.

Visual Studio Code에서 F # 지원에 필요한 유일한 플러그 인 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다. 그러나 설치할 수도 있습니다 [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 가져오려는 [가짜](https://fsharp.github.io/FAKE/) 지원 및 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 가져오려면 [Paket](https://fsprojects.github.io/Paket/) 지원 합니다. 모조 Paket 프로젝트를 빌드하고 각각 종속성을 관리 하기 위한 F # 커뮤니티 도구 추가 되며 합니다.