---
title: "Mac에서 .NET Core의 필수 구성 요소 | Microsoft Docs"
description: "macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 macOS 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: da75f5fd56b7ce66b2c46ef488e6e26c55a63ee2
ms.lasthandoff: 03/20/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a>Mac에서 .NET Core의 필수 구성 요소

이 문서에서는 macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 필요한 지원되는 macOS 버전 및 .NET Core 종속성을 보여 줍니다. 다음에 나오는 지원되는 OS 버전 및 종속성은 Mac에서 .NET Core 앱을 개발하기 위한 세 가지 방법, 즉 [즐겨 사용하는 편집기를 통한 명령줄](tutorials/using-with-xplat-cli.md), [VS Code(Visual Studio Code)](https://code.visualstudio.com/) 및 [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)에 적용됩니다.

## <a name="supported-macos-versions"></a>지원되는 macOS 버전

.NET Core는 다음 macOS 버전에서 지원됩니다.

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

[.NET Core 릴리스 정보](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md)에서 지원되는 운영 체제의 전체 집합을 볼 수 있습니다.

## <a name="net-core-dependencies"></a>.NET Core 종속성

.NET Core를 macOS에서 실행할 때는 OpenSSL이 필요합니다. OpenSSL을 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](http://brew.sh/) 패키지 관리자를 사용하는 것입니다. *brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 OpenSSL을 설치합니다.

```Terminal
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

OpenSSL을 설치한 후 공식적인 [.NET Core SDK for Mac 설치 관리자](https://go.microsoft.com/fwlink/?linkid=843444)를 다운로드합니다. .NET Core 1.1.1이 최신 버전입니다. 장기 지원 버전 및 기타 다운로드에 대한 자세한 내용은 [.NET 다운로드: 모든 다운로드](https://www.microsoft.com/net/download/core)를 방문하세요. macOS에서 설치하는 데 문제가 있는 경우 [알려진 문제 및 해결 방법](https://github.com/dotnet/core/blob/master/cli/known-issues.md)을 참조하세요.

## <a name="visual-studio-for-mac"></a>Visual Studio for Mac

Visual Studio for Mac을 사용하여 macOS에서 .NET Core로 개발하려면 다음이 필요합니다.

* 지원되는 macOS 운영 체제 버전
* Openssl
* .NET Core SDK for Mac
* [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

