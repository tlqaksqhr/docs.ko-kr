---
title: "DockerFile의 Windows PowerShell 명령을 사용 하 여 Windows 컨테이너 (Docker 표준 기반)를 설정"
description: "Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3c9a4bec4f48d988ecf8c75ff340300b83a1faef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="4ab29-104">DockerFile의 Windows PowerShell 명령을 사용 하 여 Windows 컨테이너 (Docker 표준 기반)를 설정</span><span class="sxs-lookup"><span data-stu-id="4ab29-104">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="4ab29-105">와 [Windows 컨테이너](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), Docker 이미지를 기존 Windows 응용 프로그램을 변환 하 고 Docker 생태계의 나머지 부분과 동일한 도구와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab29-105">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="4ab29-106">Windows 컨테이너를 사용 하려면 하기만 하면는 DockerFile의 Windows PowerShell 명령을 작성 하는 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="4ab29-106">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="4ab29-107">이 경우 Windows PowerShell IIS 뿐만 아니라 Windows Server Core 기본 이미지를 설치 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab29-107">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="4ab29-108">이와 비슷한 방식으로도 사용할 수 있습니다 Windows PowerShell 명령을 기존의 ASP.NET과 같은 추가 구성 요소를 설정 하려면 4.x 및.NET 4.6 또는 다른 모든 Windows 소프트웨어를 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab29-108">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="4ab29-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="4ab29-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>
