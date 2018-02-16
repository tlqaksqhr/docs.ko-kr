---
title: "최신 웹 응용 프로그램의 특징"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | 최신 웹 응용 프로그램의 특징"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ecef23870ac547f4b4066628da71f8af98c91b27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="characteristics-of-modern-web-applications"></a>최신 웹 응용 프로그램의 특징

> "… 적절 한 디자인 기능 가지 저렴 합니다. 이 방법은 단절, 되었지만 계속 성공 합니다. "  
> _\- Dennis Ritchie_

## <a name="summary"></a>요약

최신 웹 응용 프로그램에 더 높은 사용자 기대 있고 이전 보다 요구 사항이 보다 있습니다. 오늘날의 웹 앱을 사용할 수 있는 24/7에서 전 세계의 모든 위치 및 거의 모든 장치에서 사용할 하거나 화면 크기 예상 됩니다. 안전 하 고 유연 하 고, 수요에서 급증을 충족 하기 위해 확장 가능한 웹 응용 프로그램 이어야 합니다. 점점 더 많이 풍부한 사용자 환경을 웹 Api 통해 효율적으로 통신 하 고 JavaScript를 사용 하 여 클라이언트에 생성할에서 복잡 한 시나리오를 처리 해야 합니다.

ASP.NET Core 웹 응용 프로그램 및 클라우드 기반 호스팅 시나리오를 위해 최적화 됩니다. 모듈형 디자인에는 실제로 사용 응용 프로그램 보안 및 호스팅 리소스 요구 사항을 줄이고 성능 향상 기능에 따라 달라 지도록 응용 프로그램이 있습니다.

## <a name="reference-application-eshoponweb"></a>Reference Application: eShopOnWeb

이 지침에는 참조 응용 프로그램에 포함 *eShopOnWeb*, 원칙과 권장 사항은 중 일부를 보여 주는 합니다. 응용 프로그램은 shirts, 커피 잔 및 마케팅 다른 항목의 카탈로그를 통해 검색을 지 원하는 간단한 온라인 상점입니다. 참조 응용 프로그램은 쉽게 이해할 수 있도록 하기 위해 매우 간단 합니다.

**그림 2-1입니다.** eShopOnWeb

![](./media/image2-1.png)

> ### <a name="reference-application"></a>참조 응용 프로그램
> - **eShopOnWeb**  
> <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>클라우드에서 호스트 되 고 확장 가능한

메모리 부족 및 처리량이 높은 있기 때문에 ASP.NET Core (공용 클라우드, 사설 클라우드, 클라우드의) 클라우드를 위해 최적화 됩니다. ASP.NET Core 응용 프로그램의 작은 사용 공간 있을 동일한 하드웨어를 호스팅할 수 있으며 사용량 기준 과금-으로-있습니다를 사용 하 여 클라우드 호스팅 서비스를 이동 하는 경우 더 적은 리소스에 대 한 지불을 의미 합니다. 더 높은 처리량 의미 서버와 호스팅 인프라에 투자할 필요가 줄이면서 동일한 하드웨어를 제공 하는 응용 프로그램에서 더 많은 고객 사용 될 수 있습니다.

## <a name="cross-platform"></a>플랫폼 간

ASP.NET Core는 플랫폼 간 이며 Windows 뿐만 아니라 Linux 및 MacOS에서 실행할 수 있습니다. 이 개발 및 ASP.NET Core를 사용 하 여 빌드한 앱 배포에 대 한 여러 가지 새로운 옵션 열립니다. 일반적으로 오늘 Linux를 실행, docker 컨테이너의 이점을 활용 하도록 허용는 ASP.NET Core 응용 프로그램을 호스트할 [컨테이너 및 microservices](../microservices-architecture/index.md)합니다.

## <a name="modular-and-loosely-coupled"></a>모듈식 고 느슨하게 결합 된

NuGet 패키지.NET Core에서는 완벽 하 게 통합 되며 다양 한 라이브러리 NuGet 통해 ASP.NET Core 응용 프로그램으로 구성 됩니다. 기능의이 세분성이 사용 하는 앱만 달라 지 며 실제로 필요한 해당 사용 공간 및 보안 취약성이 노출 영역 줄이기 기능 배포.

ASP.NET Core 내부적으로 및 응용 프로그램 수준 종속성 주입을 완전히 지원합니다. 인터페이스는 필요에 따라 아웃 바꿀 수 있는 여러 구현을 가질 수 있습니다. 종속성 주입 느슨하게 몇 확장, 유지 관리 및 테스트 작업을 좀 더 쉽게 이러한 인터페이스에는 앱을 허용 합니다.

## <a name="easily-tested-with-automated-tests"></a>쉽게 자동화 된 테스트를 사용 하 여 테스트

ASP.NET Core 응용 프로그램 단위 테스트, 지원 및 해당 느슨한 결합 및 종속성 주입에 대 한 지원을 사용 하면 쉽게 인프라 문제가 가짜 구현 테스트 목적으로 교체 합니다. ASP.NET Core에는 메모리에서 앱을 호스트 하는 데 사용할 수 있는 TestServer 함께 제공 됩니다. 기능 테스트 실행 (미들웨어, 라우팅, 모델 바인딩, 필터, 등 포함)는 전체 응용 프로그램 스택의이 메모리에 서버에 다음 요청을 수행할 수 있습니다 및 짧은 시간에 모두 응답을 받는 데 걸리는 실제 서버에서 응용 프로그램 호스트 한 네트워크 계층을 통해 요청을 수행 합니다. 이러한 테스트 특히 쉽게 작성할 수 고를 유용 하 게 Api에 대 한, 어느 최신 웹 응용 프로그램에서 점점 더 중요 합니다.

## <a name="traditional-and-spa-behaviors-supported"></a>기존의 및 SPA 동작 지원

기존 웹 응용 프로그램 거의 클라이언트 측 동작과 관련 되어 볼 수 있지만 대신가 모든 탐색, 쿼리 및 응용 프로그램을 수행 해야 하는 업데이트에 대 한 서버에 있습니다. 사용자가 새 작업 각 최종 사용자의 브라우저에서 전체 페이지 다시 로드 되 고 결과 함께 새 웹 요청을로 변환할 수 합니다. 클래식 모델-뷰-컨트롤러 (MVC) 프레임 워크는 일반적으로 해당을 다른 컨트롤러 작업에는 모델을 사용 하 고는 뷰를 반환 하는 각 새 요청에 따라이 방법은 따릅니다. AJAX (Asynchronous JavaScript and XML) 기능을 통해 지정된 된 페이지에 대 한 일부 개별 작업을 향상 시킬 수 있지만 많은 다른 MVC 뷰 및 URL 끝점을 사용 하는 응용 프로그램의 전반적인 아키텍처.

단일 페이지 응용 프로그램 (SPAs) (있는 경우) 동적으로 생성 된 서버 쪽 페이지 로드 매우 적은 반면, 작업이 포함 됩니다. 시작 하 고 응용 프로그램을 실행 하는 데 필요한 JavaScript 라이브러리를 로드 하는 정적 HTML 파일 내에서 많은 SPAs 초기화 됩니다. 이러한 앱의 데이터 요구 사항에 대 한 웹 Api에 대 한 많은 사용량을 확인 하며 훨씬 더 풍부한 사용자 환경을 제공할 수 있습니다.

많은 웹 응용 프로그램에는 기존 웹 응용 프로그램 동작 (일반적으로 대 한 콘텐츠 포함)와 SPAs (대화형 작업)을 위한 작업이 포함 됩니다. ASP.NET Core MVC 및 웹 기본 프레임 워크 라이브러리 및 도구의 동일한 집합을 사용 하 여 동일한 응용 프로그램에서 Api 모두 지원 합니다.

## <a name="simple-development-and-deployment"></a>간단한 개발 및 배포

간단한 텍스트 편집기 및 명령줄 인터페이스 또는 Visual Studio와 같은 모든 기능을 갖춘 개발 환경을 사용 하 여 ASP.NET Core 응용 프로그램을 작성할 수 있습니다. 모놀리식 응용 프로그램은 일반적으로 단일 끝점에 배포 됩니다. 배포 (CI) 연속 통합 및 지속적인 업데이트 (CD) 파이프라인의 일부로 발생을 쉽게 자동화할 수 있습니다. 기존 CI/CD 도구 외에도 Windows Azure에 통합 git 리포지토리에 대 한 지원이 하 고 지정한 git 분기 또는 태그에 내용이 자동으로 업데이트를 배포할 수 있습니다.

## <a name="traditional-aspnet-and-web-forms"></a>기존 ASP.NET 및 Web Forms

ASP.NET Core, 기존 ASP.NET 뿐만 아니라 4.x 웹 응용 프로그램을 구축 하기 위한 강력 하 고 안정적인 플랫폼으로 계속 유지 합니다. ASP.NET은 Web Forms 페이지 기반 응용 프로그램 개발에 잘 맞는 되 고 풍부한 타사 구성 요소 생태계 기능 뿐만 아니라 MVC 및 Web API 개발 모델을 지원 합니다. Windows Azure에 ASP.NET 4.x 응용 프로그램에 대 한 훌륭한 나누는 것 지원 하며 많은 개발자가이 플랫폼에 잘 알고 있습니다.

> ### <a name="references--modern-web-applications"></a>참조-최신 웹 응용 프로그램
> - **ASP.NET Core 소개**  
> <https://docs.microsoft.com/aspnet/core/>
> - **6 개의 키 이점의 ASP.NET Core 인데 다르게 지정 하 고 더 나은**  
> <https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/>
> - **ASP.NET Core에서 테스트**  
> <https://docs.microsoft.com/aspnet/core/testing/>

>[!div class="step-by-step"]
[이전] [다음] (choose-between-traditional-web-and-single-page-apps.md) (index.md)
