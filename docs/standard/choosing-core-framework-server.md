---
title: "서버 앱에 대해 .NET Core와 .NET Framework 중에 선택"
description: ".NET에서 서버 앱을 구축할 때 고려해야 할 .NET 버전에 대한 가이드입니다."
keywords: .NET, .NET Core, .NET Framework
author: cartermp
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 155553e4-89a2-418d-be88-4e75f6c3cc69
translationtype: Human Translation
ms.sourcegitcommit: 572bec82e08d6b47a188e51964c8c2f440fa471c
ms.openlocfilehash: e23514daacb34739b26b7a31afea2ccb30296e79

---

# <a name="choosing-between-net-core-and-net-framework-for-server-apps"></a>서버 앱에 대해 .NET Core와 .NET Framework 중에 선택

.Net에서 서버 쪽 응용 프로그램을 구축하는 데 지원되는 두 가지 런타임은 .NET Framework 및 .NET Core입니다. 이 두 런타임은 동일한 많은 .NET 플랫폼 구성 요소를 공유하므로 둘 간에 코드를 공유할 수 있습니다. 그러나 두 구성 요소 간에는 기본적인 차이가 있으며 수행할 항목에 따라 선택이 달라집니다.  이 문서에서는 각각 사용하는 경우에 대한 지침을 제공합니다.

다음과 같은 경우에는 서버 응용 프로그램에 .NET Core를 사용해야 합니다.

* 플랫폼 간 요구 사항이 있습니다.
* 마이크로 서비스를 대상으로 합니다.
* Docker 컨테이너를 사용하고 있습니다.
* 고성능 및 확장 가능한 시스템이 필요합니다.
* .NET 버전이 응용 프로그램별로 함께 필요합니다.

다음과 같은 경우에는 서버 응용 프로그램에 .NET Framework를 사용해야 합니다.

* 사용 중인 응용 프로그램이 현재 .NET Framework를 사용합니다(마이그레이션하는 대신 확장 권장).
* .NET Core에 사용할 수 없는 타사 .NET 라이브러리 또는 NuGet 패키지를 사용해야 합니다.
* .NET Core에 사용할 수 없는 .NET 기술을 사용해야 합니다.
* .NET Core를 지원하지 않는 플랫폼을 사용해야 합니다.

## <a name="when-to-choose-net-core"></a>.NET Core를 선택하는 경우

다음은 .NET Core를 선택해야 하는 이전에 명시된 이유에 대해 설명합니다.

### <a name="cross-platform-needs"></a>플랫폼 간 요구 사항

플랫폼 전체(Windows, Linux 및 macOS)에서 실행할 수 있는 응용 프로그램을 구축하는 것이 목표라면 .NET Core를 사용하는 것이 가장 좋습니다.

또한 .NET Core는 앞에서 언급한 운영 체제를 개발 워크스테이션으로 지원합니다. Visual Studio는 Windows용 IDE(통합 개발 환경)를 제공합니다.  macOS, Linux 및 Windows에서 IntelliSense 및 디버깅을 비롯하여 .NET Core를 완벽하게 지원하는 Visual Studio Code를 사용할 수도 있습니다. Sublime, Emacs, VI 같은 타사 편집기로 .NET Core를 대상으로 지정하고, 오픈 소스 [Omnisharp](http://www.omnisharp.net/) 프로젝트를 사용하여 편집기 IntelliSense를 가져올 수도 있습니다. 어떤 코드 편집기도 사용하지 않고, 지원되는 모든 플랫폼에서 사용할 수 있는 .NET Core 명령줄 도구를 직접 사용할 수도 있습니다.

### <a name="microservices-architecture"></a>마이크로 서비스 아키텍처

동적으로 확장 가능하고 독립적인 여러 상태 저장 또는 상태 비저장 마이크로 서비스로 구성된 마이크로 서비스 중심의 시스템을 수용하는 경우 .NET Core가 가장 적합한 대상입니다. .NET Core는 간단하며, API 화면을 마이크로 서비스의 범위로 최소화할 수 있습니다. 마이크로 서비스 아키텍처를 사용하면 서비스 경계를 벗어나 여러 기술을 융합할 수 있습니다. 이를 통해 .NET Framework, Java, Ruby 또는 다른 모놀리식 기술로 개발된 서비스나 다른 마이크로 서비스와 결합하여 사용되는 새로운 마이크로 서비스에 .NET Core를 점진적으로 적용할 수 있습니다.

사용할 수 있는 인프라 플랫폼은 많습니다. 크고 복잡한 마이크로 서비스 시스템의 경우 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)을 사용할 수 있습니다. 상태 비저장 마이크로 서비스의 경우 [Azure App Service](https://azure.microsoft.com/services/app-service/)와 같은 다른 제품을 사용할 수도 있습니다. 또한 Docker를 바탕으로 하는 마이크로 서비스 대안의 경우 다음에 설명된 대로 모든 종류의 마이크로 서비스 접근 방식과 맞습니다. 이러한 모든 플랫폼은 .NET Core를 지원하므로 마이크로 서비스를 호스팅하는 데 적합합니다.

### <a name="containers"></a>컨테이너

컨테이너는 아키텍처 패턴을 따르는 웹앱 또는 서비스를 컨테이너화하는 데 사용할 수 있지만 일반적으로 마이크로 서비스 아키텍처와 연계하여 사용됩니다. Windows 컨테이너에 .NET Framework를 사용할 수 있지만 .NET Core의 모듈화된 간단한 특성은 컨테이너에 적합합니다.  컨테이너를 만들고 배포할 때 해당 이미지의 크기가 .NET Framework보다 .NET Core를 사용할 때 훨씬 작습니다.  플랫폼 간 사용되므로 예를 들어 서버 앱을 Linux Docker 컨테이너에 배포할 수 있습니다.

그런 다음 고유한 Linux 또는 Windows 인프라에서 Docker 컨테이너를 호스트하거나, 컨테이너 기반 응용 프로그램을 클라우드에서 관리, 오케스트레이션, 확장할 수 있는 [Azure Container Service](https://azure.microsoft.com/services/container-service/)와 같은 클라우드 서비스를 사용할 수 있습니다.

### <a name="a-need-for-high-performance-and-scalable-systems"></a>고성능 및 확장 가능한 시스템에 대한 요구 사항

시스템에 가장 적합한 성능 및 확장성이 필요한 경우 .NET Core와 ASP.NET Core를 선택하는 것이 최고입니다. ASP.NET Core는 ASP.NET보다 10배 성능이 뛰어나며, Java 서블릿, Go 및 node.js와 같은 마이크로 서비스에 대한 업계의 다른 유명 기술을 선도합니다.

수백 개의 마이크로 서비스를 실행하는 마이크로 서비스 아키텍처의 경우 특히 그렇습니다. ASP.NET Core를 사용하여 VM당 서버 수가 훨씬 적은 상태로 시스템을 실행할 수 있게 되어 궁극적으로 인프라와 호스팅에 대한 비용이 절감됩니다.

### <a name="a-need-for-side-by-side-of-net-versions-per-application-level"></a>응용 프로그램 수준별로 .NET 버전이 함께 필요

여러 버전의 .NET 프레임워크에 대한 종속성이 있는 응용 프로그램을 설치하려면 응용 프로그램에 따라 100% 완벽하게 제공하는 .NET Core를 사용해야 합니다. 동일한 컴퓨터에 여러 버전의 .NET Core을 쉽게 설치하면 동일한 서버에서 여러 서비스를 NET Core 각 버전에서 구현할 수 있어 응용 프로그램 업그레이드 및 IT 운영 비용을 절약할 수 있습니다.

## <a name="when-to-choose-net-framework"></a>.NET Framework를 선택하는 경우

.NET Core은 새 응용 프로그램 및 응용 프로그램 패턴에 많은 혜택을 제공하는 반면 .NET Framework는 다양한 기존 시나리오에 대해 계속 자연스럽게 선택되므로 .NET Core가 모든 서버 응용 프로그램에 대해 대체되는 것이 아닙니다.

### <a name="current-net-framework-applications"></a>현재 .NET Framework 응용 프로그램

대부분의 경우 .NET Core로 기존 응용 프로그램을 마이그레이션할 필요가 없습니다. 대신 ASP.NET 코어에서 새 웹 서비스를 작성하는 등 기존 응용 프로그램을 확장할 때 .NET Core를 사용하는 것이 좋습니다.

### <a name="a-need-to-use-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>.NET Core에 사용할 수 없는 타사 .NET 라이브러리 또는 NuGet 패키지를 사용해야 하는 필요성

라이브러리는 .NET 표준을 빠르게 수용하여 .NET Core를 포함하여 모든 .NET 버전에서 공유 코드를 사용할 수 있게 합니다. .NET 표준 2.0을 사용하면 이 작업은 더 간편해 집니다. .NET Core API 화면이 상당히 커지고, .NET Core 응용 프로그램에서 기존.NET Framework 라이브러리를 직접 사용할 수 있습니다. 하지만 이 전환은 즉시 발생하지는 않습니다. 따라서 결정을 여러 방법으로 내리기 전에 응용 프로그램에 필요한 특정 라이브러리를 검사하는 것이 좋습니다.

### <a name="a-need-to-use-net-technologies-not-available-for-net-core"></a>.NET Core에 사용할 수 없는 .NET 기술을 사용해야 하는 필요성

일부.NET Framework 기술은 .NET Core에서는 사용할 수 없습니다. 그 중 일부는 이후 .NET Core 릴리스에서 사용할 수 있겠지만 나머지는 .NET Core에서 대상으로 하는 새 응용 프로그램 패턴에 적용되지 않아 사용하지 못할 수도 있습니다. 다음 목록은 .NET Core 1.0에서 제공되지 않는 가장 일반적인 기술입니다.

* ASP.NET Web Forms 응용 프로그램: ASP.NET Web Forms는 .NET Framework에서만 사용할 수 있으므로 이 시나리오에서는 ASP.NET Core / .NET Core를 사용할 수 없습니다. 현재 .NET Core에 ASP.NET Web Forms를 적용할 계획은 없습니다.

* ASP.NET Web Pages 응용 프로그램: ASP.NET Web Pages는 [.NET Core 로드맵](https://github.com/aspnet/Home/wiki/Roadmap)에 설명된 대로 이후 버전에 포함될 예정이지만 ASP.NET Core 1.0에는 포함되지 않습니다.

* ASP.NET SignalR 서버/클라이언트 구현: .NET Core 1.0 릴리스 시점부터(2016년 6월) ASP.NET SignalR은 ASP.NET Core에서 사용할 수 없습니다(클라이언트 또는 서버 모두). [.NET Core 로드맵](https://github.com/aspnet/Home/wiki/Roadmap)에 설명된 대로 이후 버전에는 포함될 예정입니다. Preview 상태는 [서버 쪽](https://github.com/aspnet/SignalR-Server) 및 [클라이언트 라이브러리](https://github.com/aspnet/SignalR-Client-Net) GitHub 리포지토리에서 확인할 수 있습니다.

* WCF 서비스 구현. .NET Core에서 WCF 서비스를 사용할 수 있는 [WCF-클라이언트 라이브러리](https://github.com/dotnet/wcf)가 있더라도(2016년 6월 기준) WCF 서버 구현은 .NET Framework에서만 사용할 수 있습니다. 이 시나리오는 .NET Core에 대한 현재 계획의 일부가 아니지만 차후에 고려될 예정입니다.

* 워크플로 관련 서비스: Windows WF(Workflow Foundation), 워크플로 서비스(단일 서비스에서 WCF + WF) 및 WCF Data Services(이전의 "ADO.NET 데이터 서비스")는 .NET Framework에서만 사용할 수 있으며 .NET Core에 적용할 계획은 아직 없습니다.

* 언어 지원: Visual Basic 및 F#에는 현재 도구 지원 .NET Core가 없지만 둘 다 Visual Studio 2017 이상 버전에서 지원될 예정입니다.

공식 로드맵 외에 .NET Core로 이식할 수 있는 다른 프레임워크가 있습니다. 이에 대한 전체 목록은 [포트-코어](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core)로 표시된 CoreFX 문제를 살펴보세요. 이 목록은 이러한 구성 요소를 .NET Core에 적용하겠다는 Microsoft의 약속을 나타내는 것은 아닙니다. 단지 커뮤니티에서 원하는 항목을 캡처한 것입니다. 즉 위에 나열된 구성 요소 중 하나에 관심이 있는 경우에는 의견을 낼 수 있도록 GitHub의 토론에 참여해 보세요. 누락된 내용이 있다고 생각이 들면 [CoreFX 리포지토리에 새로운 문제를 등록](https://github.com/dotnet/corefx/issues/new)하세요.

### <a name="a-need-to-use-a-platform-that-doesnt-support-net-core"></a>.NET Core를 지원하지 않는 플랫폼을 사용하는 필요성

일부 Microsoft 또는 타사 플랫폼에서는 .NET Core를 지원하지 않습니다. 예를 들어 Service Fabric Stateful Reliable Services 및 Service Fabric Reliable Actors와 같은 일부 Azure Services에는 .NET Framework가 필요합니다. 일부 다른 서비스에서는 .NET Core에서 사용할 수 없는 SDK를 제공합니다. 현재 Azure Services는 모두 .NET Core를 사용하므로 이 상황은 전환되고 있습니다. 그 동안에는 클라이언트 SDK 대신 상응하는 REST API를 항상 사용할 수 있습니다.

## <a name="further-resources"></a>추가 리소스

* [.NET Core 가이드](../core/index.md)
* [.NET Framework에서 .NET Core로 이식](../core/porting/index.md)
* [Docker 가이드의 .NET Framework](../framework/index.md)
* [.NET 구성 요소 개요](components.md)



<!--HONumber=Jan17_HO3-->


