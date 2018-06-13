---
title: 의사 결정 테이블. Docker에 사용할 .NET Framework
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 의사 결정 테이블, Docker에 사용할 .NET Framework
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 0e384fabca88d8ad6f93ae626140fb3d5dcaf971
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589326"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>의사 결정 테이블: Docker에 사용할 .NET Framework

다음은 .NET Framework 또는 .NET Core 중 무엇을, 그리고 Windows 또는 Linux 컨테이너 중 무엇을 사용할지 요약하는 내용입니다. Linux 컨테이너의 경우 Linux 기반 Docker 호스트(VM 또는 서버)가 필요하고, Windows 컨테이너의 경우 Windows Server 기반 Docker 호스트(VM 또는 서버)가 필요하다는 사실을 기억해야 합니다.

의사 결정에 영향을 주는 몇 가지 응용 프로그램 기능이 있습니다. 의사를 결정할 때 이러한 기능의 중요도에 가중치를 부여해야 합니다.

> [!IMPORTANT]
> 개발 컴퓨터에서 Docker 호스트(Linux 또는 Windows)를 하나 실행해야 합니다. 한 솔루션에서 함께 실행하고 테스트할 관련 마이크로 서비스가 전부 동일한 컨테이너 플랫폼에서 실행되어야 합니다.

* 응용 프로그램 아키텍처로 **컨테이너의 마이크로 서비스**를 선택합니다.
    - .NET 구현으로 *.NET Core*를 선택합니다.
    - 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.
* 응용 프로그램 아키텍처로 **모놀리식 응용 프로그램**을 선택합니다.
    - .NET 구현으로 *.NET Core*를 선택해도 되고 *.NET Framework*를 선택해도 됩니다.
    - *.NET Core*를 선택한 경우 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.
    - *.NET Framework*를 선택한 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
* 응용 프로그램은 **새 컨테이너 기반 개발("그린 필드")** 입니다.
    - .NET 구현으로 *.NET Core*를 선택합니다.
    - 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.
* 응용 프로그램은 **컨테이너로의 Windows Server 레거시 앱("브라운 필드") 마이그레이션**
    - .NET 구현으로 프레임워크 종속성 기반의 *.NET Framework*를 선택합니다.
    - .NET Framework 종속성 때문에 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
* 응용 프로그램의 디자인 목표는 **동급 최고의 성능 및 확장성**입니다.
    - .NET 구현으로 *.NET Core*를 선택합니다.
    - 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.
* **ASP.NET Core**를 사용하여 응용 프로그램을 빌드합니다.
    - .NET 구현으로 *.NET Core*를 선택합니다.
    - 다른 프레임워크 종속성이 있는 경우 *.NET Framework* 구현을 사용할 수 있습니다.
    - *.NET Core*를 선택한 경우 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.
    - *.NET Framework*를 선택한 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
* **ASP.NET 4(MVC 5, Web API 2 및 Web Forms)** 를 사용하여 응용 프로그램을 빌드합니다.
    - .NET 구현으로 프레임워크 종속성 기반의 *.NET Framework*를 선택합니다.
    - .NET Framework 종속성 때문에 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
* 응용 프로그램에서는 **SignalR 서비스**를 사용합니다.
    - .NET 구현으로 *.NET Framework*를 선택해도 되고 *.NET Core 2.1 이상(릴리스된 경우)* 을 선택해도 됩니다.
    - .NET Framework에서 SignalR 구현을 선택한 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
    - .NET Core 2.1 이상(릴리스된 경우)에서 SignalR 구현을 선택한 경우 컨테이너 플랫폼으로 Linux 컨테이너를 선택해도 되고 Windows 컨테이너를 선택해도 됩니다.  
    - **SignalR 서비스**가 *.NET Core*에서 실행되면 *Linux 컨테이너 또는 Windows 컨테이너*를 사용할 수 있습니다.
* 응용 프로그램에서는 **WCF, WF 및 기타 레거시 프레임워크**를 사용합니다.
    - .NET 구현으로 *.NET Framework* 또는 *.NET Core(향후 릴리스에 대한 로드맵에 있는)* 를 선택합니다.
    - .NET Framework 종속성 때문에 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
* 응용 프로그램에서는 **Azure 서비스를 사용**합니다.
    - .NET 구현으로 *.NET Framework* 또는 *.NET Core(궁극적으로 모든 Azure 서비스 클라이언트에서 SDKs for .NET Core 제공)* 를 선택합니다.
    - .NET Framework 클라이언트 API를 사용하는 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.
    - *.NET Core*에 제공되는 클라이언트 API를 사용하는 경우 *Linux 컨테이너 및 Windows 컨테이너* 중에 선택할 수도 있습니다.

>[!div class="step-by-step"]
[이전] (net-framework-container-scenarios.md) [다음] (net-container-os-targets.md)
