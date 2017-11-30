---
title: "Docker 컨테이너에 대 한.NET Framework를 선택 하는 경우"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 컨테이너에 대 한.NET Framework를 선택 하는 경우"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Docker 컨테이너에 대 한.NET Framework를 선택 하는 경우

.NET Core에서는 새 응용 프로그램 및 응용 프로그램 패턴에 대 한 중요 한 혜택을 제공 하지만 대부분의 기존 시나리오에 적합 하려면.NET Framework 계속 됩니다.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Windows Server 컨테이너에 직접 기존 응용 프로그램 마이그레이션

Microservices 만들지 않는 경우에 배포를 단순화 하기 위해 Docker 컨테이너를 사용 수 있습니다. 예를 들어 아마도 향상 시키려면 Docker 통한 DevOps 워크플로-컨테이너 더 격리 된 테스트 환경을 제공할 수와 프로덕션 환경으로 이동 하면 누락 된 종속성에의 한 배포 문제를 제거할 수 있습니다. 이와 같은 경우에는 모놀리식 응용 프로그램을 배포 하는 경우에 의미가 현재.NET Framework 응용 프로그램에 대 한 Docker 및 Windows 컨테이너를 사용 하도록 합니다.

이 시나리오에 대 한 대부분의 경우 않아도 됩니다.NET Core; 하 여 기존 응용 프로그램 마이그레이션 기존.NET Framework를 포함 하는 Docker 컨테이너를 사용할 수 있습니다. 그러나 ASP.NET Core에서 새 서비스를 작성 하는 등 기존 응용 프로그램을 확장 하는 대로.NET Core를 사용 하는 것이 좋습니다.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>.NET Core에 대 한 제 3 자.NET 라이브러리 또는 사용할 수 없는 NuGet 패키지를 사용 하 여

타사 라이브러리의 디렉터리가 신속 하 게는 [.NET 표준](https://docs.microsoft.com/dotnet/standard/net-standard), 하면.NET Core를 포함 하 여 모든.NET 버전에서 공유 하는 코드가 있습니다. 다양 한 프레임 워크에서 호환성 크게 증가 되었습니다 API 화면.NET 표준 라이브러리 2.0 이상 및.NET Core 2.0에서 응용 프로그램 수를 직접 참조할 수도 기존.NET Framework 라이브러리 (참조 [호환 가능 shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

그러나 표준.NET 2.0 및.NET Core 2.0 이후 해당 뛰어난 진행, 된 경우에 있을 수 있습니다 특정 NuGet 패키지 해야 Windows를 실행 하 고.NET Core를 지원 하지 않을 수 있는 경우. 이러한 패키지를 응용 프로그램에 대 한 중요 한 경우 Windows 컨테이너에서.NET Framework를 사용 해야 합니다.

## <a name="usingnet-technologies-not-available-for-net-core"></a>.NET Core에 사용할 수 없는 Using.NET 기술 

일부.NET Framework 기술을.NET Core (버전 2.0 부터는)의 현재 버전에서 사용할 수 없는 합니다. 그 중 일부를 다음.NET Core 시리즈에서 사용할 수 있습니다 (.NET Core 2.x), 되지만 다른 패턴의 대상.NET Core 및 사용할 수 없습니다 새 응용 프로그램에 적용 되지 않습니다.

다음은 대부분의.NET Core 2.0에서 사용할 수 없는 기술입니다.

-   ASP.NET Web Forms 합니다. 이 기술은만.NET Framework에서 사용할 수 있습니다. 현재 .NET Core에 ASP.NET Web Forms를 적용할 계획은 없습니다.

-   WCF 서비스입니다. 경우에 한 [WCF 클라이언트 라이브러리](https://github.com/dotnet/wcf) .NET Core에서 WCF 서비스를 사용할 수 있습니다. 2017 중순 현재 WCF 서버 구현은.NET Framework에서 사용할 수만 있습니다. .NET Core의 이후 릴리스에서이 시나리오 고려 될 수 있습니다.

-   워크플로 관련 서비스입니다. Windows WF (Workflow Foundation), 워크플로 서비스 (WCF + 단일 서비스에서 WF) 및 WCF 데이터 서비스 (이전의 ADO.NET Data Services)은.NET Framework에서 사용할 수만 있습니다. 현재.NET Core 서로 일치 되지 않습니다.

공식에 나열 된 기술 외에도 [.NET Core 로드맵](https://github.com/aspnet/Home/wiki/Roadmap), 다른 기능과.NET Core로 이식 될 수 있습니다. 전체 목록에 대 한 것으로 태그 항목을 찾아야 [포트 코어](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) CoreFX GitHub 사이트에서. 이 목록에서 Microsoft.NET Core에 이러한 구성 요소를 업그레이드 하기 위한 코드를 나타내지 않는 참고-항목 커뮤니티에서 요청을 단순히 캡처. 위에 나열 된 구성 요소 중 하나에 대 한 관심이 있으면 음성을 답변을 받을 수 있도록 GitHub의 토론에 참여 하는 것이 좋습니다. 누락된 내용이 있다고 생각이 들면 [CoreFX 리포지토리에 새로운 문제를 등록](https://github.com/dotnet/corefx/issues/new)하세요.

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>플랫폼 또는.NET Core를 지원 하지 않는 API를 사용 하 여

일부 Microsoft 또는 타사 플랫폼과.NET Core를 지원 하지 않습니다. 예를 들어 일부 Azure 서비스가 아직 사용할 수 없는.NET Core에서 소비에 대 한 SDK를 제공 합니다. 모든 Azure 서비스는.NET Core를 사용 하 여 결국 때문 일시적입니다. 예를 들어는 [Azure DocumentDB SDK for.NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) 2016 년 11 월 16 일에 대 한 미리 보기로 릴리스된 그러나 이제에서는 안정적인 버전으로 사용할 수 있는 (GA).

그 동안에 모든 플랫폼 또는 Azure 서비스에에서 여전히를 지원 하지 않으면.NET Core는 클라이언트 API와.NET Framework에서 Azure 서비스 또는 SDK 클라이언트에서 해당 하는 REST API를 사용할 수 있습니다.

### <a name="additional-resources"></a>추가 리소스

-   **.NET core 가이드**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **.NET Framework에서.NET Core로 이식**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **Docker 설명서에.NET framework**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **.NET 구성 요소 개요**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[이전] (net-코어-컨테이너-scenarios.md) [다음] (컨테이너-프레임 워크-선택-factors.md)
