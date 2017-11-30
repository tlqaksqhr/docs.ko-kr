---
title: "Azure에 대 한 개발 프로세스"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | Azure에 대 한 개발 프로세스"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: e676c1225f7d11381808040cf101e897e0726ad4
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="development-process-for-azure"></a>Azure에 대 한 개발 프로세스

> _"클라우드와 개인과 중소기업 맞추고 수 있습니다 손가락 즉시 엔터프라이즈 수준의 서비스를 설정 합니다."_  
> _-로 Stephan_

 ## <a name="vision"></a>비전

> *Visual Studio 또는 dotnet CLI 및 Visual Studio Code 또는 원하는 편집기를 사용 하 여 원하는 방식으로 잘 설계 된 ASP.NET Core 응용 프로그램을 개발 합니다.*

## <a name="development-environment-for-aspnet-core-apps"></a>ASP.NET Core 응용 프로그램에 대 한 개발 환경

### <a name="development-tools-choices-ide-or-editor"></a>개발 도구에서 선택 항목: IDE 또는 편집기

완전 하 고 강력한 IDE 또는 간단 하 고 agile 편집기를 원하는 지 여부를 Microsoft에 ASP.NET Core 응용 프로그램을 개발할 때 거둘 수 있습니다.

**Visual Studio 2017 합니다.** 사용 중인 경우 *Visual Studio 2017* 빌드할 수 ASP.NET Core 응용 프로그램을 있는 그대로 *.NET Core 플랫폼 간 개발* 설치 하는 작업입니다. 그림 10-1은 Visual Studio 2017 설정 대화 상자에서 필요한 작업을 보여 줍니다.

![](./media/image10-1.png)

**그림 10-1입니다.** Visual Studio 2017에.NET Core 작업 부하를 설치 합니다.

[Visual Studio 2017 다운로드](https://www.visualstudio.com/downloads/)

**Visual Studio Code 및 CLI dotnet** (Mac, Linux 및 Windows 용 플랫폼 간 도구). 모든 개발 언어를 지 원하는 플랫폼 간을 간단 하 고 편집기를 선호 하는 경우에 Microsoft Visual Studio 코드 및 CLI dotnet를 사용할 수 있습니다. 이러한 제품은 개발자 워크플로 간소화 하는 단순 하면서도 강력한 환경을 제공 합니다. 또한 Visual Studio Code C에 대 한 확장을 지원\# 및 웹 개발에 intellisense 및 편집기 내에서 바로 가기 작업을 제공 합니다.

[.NET Core SDK 다운로드](https://www.microsoft.com/net/download/core)

[Visual Studio 코드 다운로드](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Azure에서 호스팅되는 ASP.NET Core 응용 프로그램에 대 한 개발 워크플로

로컬 테스트 및 기본 설정된 언어를 사용 하 여 앱을 코딩 하는 각 개발자의 컴퓨터에서 응용 프로그램 개발 수명 주기를 시작 합니다. 개발자가 기본 소스 제어 시스템을 선택할 수 있습니다 및 연속 통합 (CI) 및/또는 연속 배달/배포 (CD) 빌드 서버를 사용 하 여 구성할 수 있습니다 또는 기본 제공 Azure 기능을 기반으로 합니다.

CI/CD를 사용 하 여 ASP.NET Core 응용 프로그램 개발을 시작 하려면 Visual Studio Team Services 또는 조직의 사용할 수 Team Foundation Server (TFS)를 소유 합니다.

### <a name="initial-setup"></a>초기 설치

앱에 대 한 릴리스 파이프라인을 만들려면 소스 제어에서 응용 프로그램 코드를 포함 하도록 해야 합니다. 로컬 저장소를 설정 하 고 팀 프로젝트의 원격 저장소에 연결 합니다. 이러한 지침을 따르세요.

-   [Git 및 Visual Studio와 코드를 공유할](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) 또는

-   [TFVC 및 Visual Studio와 코드 공유](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

Azure 앱 서비스 응용 프로그램 배포를 만듭니다. Azure 포털에서 응용 프로그램 서비스 블레이드로 이동 하 여 웹 앱을 만듭니다. 클릭 + 추가 웹 응용 프로그램 템플릿을 선택 하 만들기를 클릭 하 고 이름과 기타 세부 정보를 제공 합니다. 웹 응용 프로그램 {name}에서 액세스할 수 있습니다. azurewebsites.net 합니다.

![AzureWebApp](./media/image10-2.png)

**그림 10-2입니다.** Azure 포털에서 새 Azure 앱 서비스 웹 앱을 만듭니다.

CI 빌드 프로세스는 새 코드 프로젝트의 소스 제어 리포지토리에으로 모두 커밋됩니다 때마다 자동화 된 빌드를 수행 합니다. 이렇게 하면 코드를 작성 하는 즉각적인 피드백 (및을 이상적으로 자동화 된 테스트를 통과) 잠재적으로 배포할 수 있습니다. 이 CI 빌드는 웹을 생성 하는 패키지 아티팩트를 배포 하 고 CD 프로세스에서 사용할 수 있도록 게시 합니다.

[CI 빌드 프로세스 정의](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

시스템을 때마다 새 코드를 커밋합니다에 빌드 대기 하므로 연속 통합을 사용 하도록 설정 해야 합니다. 빌드를 테스트 하 고 웹 생성 되어 있는지 확인 하십시오. 해당 아티팩트 중 하나로 패키지를 배포 합니다.

빌드에 성공 하면 CD 프로세스는 CI 빌드 결과를 Azure 웹 앱에 배포 합니다. 이 구성 하려면 만들고 구성 된 *릴리스*, 있는 Azure 앱 서비스를 배포 합니다.

[CD 릴리스 프로세스를 정의 합니다.](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

CI/CD 파이프라인 구성 되 면 단순히 웹 응용 프로그램에 업데이트를 확인을 배포 하는 소스 제어에 커밋합니다.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Azure에서 호스팅되는 ASP.NET Core 응용 프로그램을 개발 하기 위한 워크플로

Azure 계정 및 CI/CD 프로세스를 구성한 후 Azure에서 호스팅되는 ASP.NET Core 응용 프로그램 개발은 간단 합니다. 그림 10-3을 보여 주는 것 처럼 웹 앱으로 Azure 앱 서비스에서 호스팅되는 ASP.NET Core 응용 프로그램을 빌드할 때 일반적으로 수행 하는 기본 단계는 다음과 같습니다.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**그림 10-3입니다.** Azure에서 호스트 하 고 ASP.NET Core 응용 프로그램을 빌드하기 위한 단계별 워크플로

#### <a name="step-1-local-dev-environment-inner-loop"></a>1단계: 로컬 개발 환경 내부 루프

Azure에 배포에 대 한 ASP.NET Core 응용 프로그램을 개발 하는 것은 그렇지 않은 경우 응용 프로그램을 개발 더 다릅니다. 로컬 개발 환경에 익숙하다면, Visual Studio 2017 또는 dotnet CLI 및 Visual Studio Code 또는 원하는 편집기를 사용 합니다. 코드를 작성, 실행 및 디버그 변경 내용을, 자동화 된 테스트를 실행 하 고 수 공유 소스 제어 리포지토리에 변경 내용을 푸시 준비가 되었습니다. 로컬 커밋의 소스 제어 변경 합니다.

#### <a name="step-2-application-code-repository"></a>2단계. 응용 프로그램 코드 리포지토리

코드를 팀과 공유할 준비가 될 때마다 팀의 공유 원본 리포지토리에 변경 내용을 원본 로컬 리포지토리에서 푸시할 해야 있습니다. 사용자 지정 분기에서 작업 한 경우이 단계 일반적 코드 공유 분기에 병합 (아마도 방법으로 [끌어오기 요청](https://www.visualstudio.com/docs/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>3단계. 빌드 서버: 연속 통합 합니다. 빌드, 테스트, 패키지

공유 응용 프로그램 코드 저장소에 새 커밋이 때마다 빌드 서버에서 새 빌드가 트리거됩니다. CI 프로세스의 일환으로,이 빌드는 응용 프로그램 컴파일 및 모든 것이 예상 대로 작동을 확인 하는 자동화 된 테스트 실행 완벽 하 게 해야 합니다. CI 프로세스의 최종 결과는 배포 준비 완료 웹 응용 프로그램의 패키지 버전 여야 합니다.

#### <a name="step-4-build-server-continuous-delivery"></a>4단계. 빌드 서버: 지속적인 업데이트

한 번 성공으로 빌드, CD 프로세스가 가져옵니다 생성 빌드 아티팩트. 여기에 웹 패키지를 배포 합니다. 빌드 서버에서 새로 만든 모든 기존 서비스 대체 되는 Azure 앱 서비스에이 패키지를 배포 합니다. 일반적으로이 단계는 스테이징 환경을 대상으로 하지만 일부 응용 프로그램 CD 프로세스를 통해 프로덕션 환경에 직접 배포 합니다.

#### <a name="step-5-azure-app-service-web-app"></a>5단계. Azure 앱 서비스입니다. 웹 앱입니다.

배포 된 후 Azure 앱 서비스 웹 앱의 컨텍스트 내에서 ASP.NET Core 응용 프로그램을 실행 합니다. 이 웹 앱을 모니터링할 수 있습니다 및 Azure 포털을 사용 하 여를 추가로 구성 합니다.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>6단계. 프로덕션 모니터링 및 진단

웹 앱이 실행 되는 동안 응용 프로그램의 상태를 모니터링할 수 있으며 진단 정보 및 사용자 동작 데이터를 수집할 수 있습니다. Application Insights는 Visual Studio에 포함 하 고 ASP.NET 응용 프로그램에 대 한 자동 계측을 제공 합니다. 사용, 예외, 요청, 성능 및 로그에 대 한 정보와 함께 있습니다 제공할 수 있습니다.

## <a name="references"></a>참조

**빌드 및 Azure에 ASP.NET Core 응용 프로그램 배포**  
<https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure>


>[!div class="step-by-step"]
[이전] [다음] (azure-hosting-recommendations-for-asp-net-web-apps.md) (test-asp-net-core-mvc-apps.md)
