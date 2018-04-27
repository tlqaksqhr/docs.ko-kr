---
title: DockerFile의 Windows PowerShell 명령을 사용 하 여 Windows 컨테이너 (Docker 표준 기반)를 설정
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f94da774954ce575d343f2de4cef500e57f126c3
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>DockerFile의 Windows PowerShell 명령을 사용 하 여 Windows 컨테이너 (Docker 표준 기반)를 설정

와 [Windows 컨테이너](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), Docker 이미지를 기존 Windows 응용 프로그램을 변환 하 고 Docker 생태계의 나머지 부분과 동일한 도구와 함께 배포할 수 있습니다.

Windows 컨테이너를 사용 하려면 하기만 하면는 DockerFile의 Windows PowerShell 명령을 작성 하는 다음 예제와 같이:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

이 경우 Windows PowerShell IIS 뿐만 아니라 Windows Server Core 기본 이미지를 설치 하는 데 사용 합니다.

이와 비슷한 방식으로도 사용할 수 있습니다 Windows PowerShell 명령을 기존의 ASP.NET과 같은 추가 구성 요소를 설정 하려면 4.x 및.NET 4.6 또는 다른 모든 Windows 소프트웨어를 다음과 같이 합니다.

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[이전] (visual-studio-도구-에-docker.md) [다음] (... /docker-devops-workflow/index.md)
