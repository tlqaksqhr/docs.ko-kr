---
title: "Azure에 대 한 개발 프로세스"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | Azure에 대 한 개발 프로세스"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 21826e2c90d234d873cc06bfae3bd22ce89a62d2
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="development-process-for-azure"></a><span data-ttu-id="e47f5-103">Azure에 대 한 개발 프로세스</span><span class="sxs-lookup"><span data-stu-id="e47f5-103">Development process for Azure</span></span>

> <span data-ttu-id="e47f5-104">_"클라우드와 개인과 중소기업 맞추고 수 있습니다 손가락 즉시 엔터프라이즈 수준의 서비스를 설정 합니다."_</span><span class="sxs-lookup"><span data-stu-id="e47f5-104">_"With the cloud, individuals and small businesses can snap their fingers and instantly set up enterprise-class services."_</span></span>  
> <span data-ttu-id="e47f5-105">_-로 Stephan_</span><span class="sxs-lookup"><span data-stu-id="e47f5-105">_- Roy Stephan_</span></span>

 ## <a name="vision"></a><span data-ttu-id="e47f5-106">비전</span><span class="sxs-lookup"><span data-stu-id="e47f5-106">Vision</span></span>

> <span data-ttu-id="e47f5-107">*Visual Studio 또는 dotnet CLI 및 Visual Studio Code 또는 원하는 편집기를 사용 하 여 원하는 방식으로 잘 설계 된 ASP.NET Core 응용 프로그램을 개발 합니다.*</span><span class="sxs-lookup"><span data-stu-id="e47f5-107">*Develop well-designed ASP .NET Core applications the way you like, using Visual Studio or the dotnet CLI and Visual Studio Code or your editor of choice.*</span></span>

## <a name="development-environment-for-aspnet-core-apps"></a><span data-ttu-id="e47f5-108">ASP.NET Core 응용 프로그램에 대 한 개발 환경</span><span class="sxs-lookup"><span data-stu-id="e47f5-108">Development environment for ASP.NET Core apps</span></span>

### <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="e47f5-109">개발 도구에서 선택 항목: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="e47f5-109">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="e47f5-110">완전 하 고 강력한 IDE 또는 간단 하 고 agile 편집기를 원하는 지 여부를 Microsoft에 ASP.NET Core 응용 프로그램을 개발할 때 거둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-110">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when developing ASP.NET Core applications.</span></span>

<span data-ttu-id="e47f5-111">**Visual Studio 2017.**</span><span class="sxs-lookup"><span data-stu-id="e47f5-111">**Visual Studio 2017.**</span></span> <span data-ttu-id="e47f5-112">사용 중인 경우 *Visual Studio 2017* 빌드할 수 ASP.NET Core 응용 프로그램을 있는 그대로 *.NET Core 플랫폼 간 개발* 설치 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-112">If you're using *Visual Studio 2017* you can build ASP.NET Core applications as long as you have the *.NET Core cross-platform development* workload installed.</span></span> <span data-ttu-id="e47f5-113">그림 10-1은 Visual Studio 2017 설정 대화 상자에서 필요한 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-113">Figure 10-1 shows the required workload in the Visual Studio 2017 setup dialog.</span></span>

![](./media/image10-1.png)

<span data-ttu-id="e47f5-114">**그림 10-1입니다.**</span><span class="sxs-lookup"><span data-stu-id="e47f5-114">**Figure 10-1.**</span></span> <span data-ttu-id="e47f5-115">Visual Studio 2017에.NET Core 작업 부하를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-115">Installing the .NET Core workload in Visual Studio 2017.</span></span>

[<span data-ttu-id="e47f5-116">Visual Studio 2017 다운로드</span><span class="sxs-lookup"><span data-stu-id="e47f5-116">Download Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

<span data-ttu-id="e47f5-117">**Visual Studio Code 및 CLI dotnet** (Mac, Linux 및 Windows 용 플랫폼 간 도구).</span><span class="sxs-lookup"><span data-stu-id="e47f5-117">**Visual Studio Code and dotnet CLI** (Cross-Platform Tools for Mac, Linux and Windows).</span></span> <span data-ttu-id="e47f5-118">모든 개발 언어를 지 원하는 플랫폼 간을 간단 하 고 편집기를 선호 하는 경우에 Microsoft Visual Studio 코드 및 CLI dotnet를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-118">If you prefer a lightweight and cross-platform editor supporting any development language, you can use Microsoft Visual Studio Code and the dotnet CLI.</span></span> <span data-ttu-id="e47f5-119">이러한 제품은 개발자 워크플로 간소화 하는 단순 하면서도 강력한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-119">These products provide a simple yet robust experience that streamlines the developer workflow.</span></span> <span data-ttu-id="e47f5-120">또한 Visual Studio Code C에 대 한 확장을 지원\# 및 웹 개발에 intellisense 및 편집기 내에서 바로 가기 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-120">Additionally, Visual Studio Code supports extensions for C\# and web development, providing intellisense and shortcut-tasks within the editor.</span></span>

[<span data-ttu-id="e47f5-121">.NET Core SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="e47f5-121">Download the .NET Core SDK</span></span>](https://www.microsoft.com/net/download/core)

[<span data-ttu-id="e47f5-122">Visual Studio 코드 다운로드</span><span class="sxs-lookup"><span data-stu-id="e47f5-122">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a><span data-ttu-id="e47f5-123">Azure에서 호스팅되는 ASP.NET Core 응용 프로그램에 대 한 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="e47f5-123">Development workflow for Azure-hosted ASP.NET Core apps</span></span>

<span data-ttu-id="e47f5-124">로컬 테스트 및 기본 설정된 언어를 사용 하 여 앱을 코딩 하는 각 개발자의 컴퓨터에서 응용 프로그램 개발 수명 주기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-124">The application development lifecycle starts from each developer's machine, coding the app using their preferred language and testing it locally.</span></span> <span data-ttu-id="e47f5-125">개발자가 기본 소스 제어 시스템을 선택할 수 있습니다 및 연속 통합 (CI) 및/또는 연속 배달/배포 (CD) 빌드 서버를 사용 하 여 구성할 수 있습니다 또는 기본 제공 Azure 기능을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-125">Developers may choose their preferred source control system and can configure Continuous Integration (CI) and/or Continuous Delivery/Deployment (CD) using a build server or based on built-in Azure features.</span></span>

<span data-ttu-id="e47f5-126">CI/CD를 사용 하 여 ASP.NET Core 응용 프로그램 개발을 시작 하려면 Visual Studio Team Services 또는 조직의 사용할 수 Team Foundation Server (TFS)를 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-126">To get started with developing an ASP.NET Core application using CI/CD, you can use Visual Studio Team Services or your organization's own Team Foundation Server (TFS).</span></span>

### <a name="initial-setup"></a><span data-ttu-id="e47f5-127">초기 설치</span><span class="sxs-lookup"><span data-stu-id="e47f5-127">Initial Setup</span></span>

<span data-ttu-id="e47f5-128">앱에 대 한 릴리스 파이프라인을 만들려면 소스 제어에서 응용 프로그램 코드를 포함 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-128">To create a release pipeline for your app, you need to have your application code in source control.</span></span> <span data-ttu-id="e47f5-129">로컬 저장소를 설정 하 고 팀 프로젝트의 원격 저장소에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-129">Set up a local repository and connect it to a remote repository in a team project.</span></span> <span data-ttu-id="e47f5-130">이러한 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e47f5-130">Follow these instructions:</span></span>

-   <span data-ttu-id="e47f5-131">[Git 및 Visual Studio와 코드를 공유할](https://docs.microsoft.com/vsts/git/share-your-code-in-git-vs) 또는</span><span class="sxs-lookup"><span data-stu-id="e47f5-131">[Share your code with Git and Visual Studio](https://docs.microsoft.com/vsts/git/share-your-code-in-git-vs) or</span></span>

-   [<span data-ttu-id="e47f5-132">TFVC 및 Visual Studio와 코드 공유</span><span class="sxs-lookup"><span data-stu-id="e47f5-132">Share your code with TFVC and Visual Studio</span></span>](https://docs.microsoft.com/vsts/tfvc/share-your-code-in-tfvc-vs)

<span data-ttu-id="e47f5-133">Azure 앱 서비스 응용 프로그램 배포를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-133">Create an Azure App Service where you'll deploy your application.</span></span> <span data-ttu-id="e47f5-134">Azure 포털에서 응용 프로그램 서비스 블레이드로 이동 하 여 웹 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-134">Create a Web App by going to the App Services blade on the Azure portal.</span></span> <span data-ttu-id="e47f5-135">클릭 + 추가 웹 응용 프로그램 템플릿을 선택 하 만들기를 클릭 하 고 이름과 기타 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-135">Click +Add, select the Web App template, click Create, and provide a name and other details.</span></span> <span data-ttu-id="e47f5-136">웹 응용 프로그램 {name}에서 액세스할 수 있습니다. azurewebsites.net 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-136">The web app will be accessible from {name}.azurewebsites.net.</span></span>

![AzureWebApp](./media/image10-2.png)

<span data-ttu-id="e47f5-138">**그림 10-2입니다.**</span><span class="sxs-lookup"><span data-stu-id="e47f5-138">**Figure 10-2.**</span></span> <span data-ttu-id="e47f5-139">Azure 포털에서 새 Azure 앱 서비스 웹 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-139">Creating a new Azure App Service Web App in the Azure Portal.</span></span>

<span data-ttu-id="e47f5-140">CI 빌드 프로세스는 새 코드 프로젝트의 소스 제어 리포지토리에으로 모두 커밋됩니다 때마다 자동화 된 빌드를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-140">Your CI build process will perform an automated build whenever new code is committed to the project's source control repository.</span></span> <span data-ttu-id="e47f5-141">이렇게 하면 코드를 작성 하는 즉각적인 피드백 (및을 이상적으로 자동화 된 테스트를 통과) 잠재적으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-141">This gives you immediate feedback that the code builds (and, ideally, passes automated tests) and can potentially be deployed.</span></span> <span data-ttu-id="e47f5-142">이 CI 빌드는 웹을 생성 하는 패키지 아티팩트를 배포 하 고 CD 프로세스에서 사용할 수 있도록 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-142">This CI build will produce a web deploy package artifact and publish it for consumption by your CD process.</span></span>

[<span data-ttu-id="e47f5-143">CI 빌드 프로세스 정의</span><span class="sxs-lookup"><span data-stu-id="e47f5-143">Define your CI build process</span></span>](https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core#ci)

<span data-ttu-id="e47f5-144">시스템을 때마다 새 코드를 커밋합니다에 빌드 대기 하므로 연속 통합을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-144">Be sure to enable continuous integration so the system will queue a build whenever someone on your team commits new code.</span></span> <span data-ttu-id="e47f5-145">빌드를 테스트 하 고 웹 생성 되어 있는지 확인 하십시오. 해당 아티팩트 중 하나로 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-145">Test the build and verify that it is producing a web deploy package as one of its artifacts.</span></span>

<span data-ttu-id="e47f5-146">빌드에 성공 하면 CD 프로세스는 CI 빌드 결과를 Azure 웹 앱에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-146">When a build succeeds, your CD process will deploy the results of your CI build to your Azure web app.</span></span> <span data-ttu-id="e47f5-147">이 구성 하려면 만들고 구성 된 *릴리스*, 있는 Azure 앱 서비스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-147">To configure this, you create and configure a *Release*, which will deploy to your Azure App Service.</span></span>

[<span data-ttu-id="e47f5-148">CD 릴리스 프로세스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-148">Define your CD release process</span></span>](https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core#cd)

<span data-ttu-id="e47f5-149">CI/CD 파이프라인 구성 되 면 단순히 웹 응용 프로그램에 업데이트를 확인을 배포 하는 소스 제어에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-149">Once your CI/CD pipeline is configured, you can simply make updates to your web app and commit them to source control to have them deployed.</span></span>

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a><span data-ttu-id="e47f5-150">Azure에서 호스팅되는 ASP.NET Core 응용 프로그램을 개발 하기 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="e47f5-150">Workflow for developing Azure-hosted ASP.NET Core applications</span></span>

<span data-ttu-id="e47f5-151">Azure 계정 및 CI/CD 프로세스를 구성한 후 Azure에서 호스팅되는 ASP.NET Core 응용 프로그램 개발은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-151">Once you have configured your Azure account and your CI/CD process, developing Azure-hosted ASP.NET Core applications is simple.</span></span> <span data-ttu-id="e47f5-152">그림 10-3을 보여 주는 것 처럼 웹 앱으로 Azure 앱 서비스에서 호스팅되는 ASP.NET Core 응용 프로그램을 빌드할 때 일반적으로 수행 하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-152">The following are the basic steps you usually take when building an ASP.NET Core app, hosted in Azure App Service as a Web App, as illustrated in Figure 10-3.</span></span>

![EndToEndDevDeployWorkflow](./media/image10-3.png)

<span data-ttu-id="e47f5-154">**그림 10-3입니다.**</span><span class="sxs-lookup"><span data-stu-id="e47f5-154">**Figure 10-3.**</span></span> <span data-ttu-id="e47f5-155">Azure에서 호스트 하 고 ASP.NET Core 응용 프로그램을 빌드하기 위한 단계별 워크플로</span><span class="sxs-lookup"><span data-stu-id="e47f5-155">Step-by-step workflow for building ASP.NET Core apps and hosting them in Azure</span></span>

#### <a name="step-1-local-dev-environment-inner-loop"></a><span data-ttu-id="e47f5-156">1단계:</span><span class="sxs-lookup"><span data-stu-id="e47f5-156">Step 1.</span></span> <span data-ttu-id="e47f5-157">로컬 개발 환경 내부 루프</span><span class="sxs-lookup"><span data-stu-id="e47f5-157">Local Dev Environment Inner Loop</span></span>

<span data-ttu-id="e47f5-158">Azure에 배포에 대 한 ASP.NET Core 응용 프로그램을 개발 하는 것은 그렇지 않은 경우 응용 프로그램을 개발 더 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-158">Developing your ASP.NET Core application for deployment to Azure is no different from developing your application otherwise.</span></span> <span data-ttu-id="e47f5-159">로컬 개발 환경에 익숙하다면, Visual Studio 2017 또는 dotnet CLI 및 Visual Studio Code 또는 원하는 편집기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-159">Use the local development environment you're comfortable with, whether that's Visual Studio 2017 or the dotnet CLI and Visual Studio Code or your preferred editor.</span></span> <span data-ttu-id="e47f5-160">코드를 작성, 실행 및 디버그 변경 내용을, 자동화 된 테스트를 실행 하 고 수 공유 소스 제어 리포지토리에 변경 내용을 푸시 준비가 되었습니다. 로컬 커밋의 소스 제어 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-160">You can write code, run and debug your changes, run automated tests, and make local commits to source control until you're ready to push your changes to your shared source control repository.</span></span>

#### <a name="step-2-application-code-repository"></a><span data-ttu-id="e47f5-161">2단계.</span><span class="sxs-lookup"><span data-stu-id="e47f5-161">Step 2.</span></span> <span data-ttu-id="e47f5-162">응용 프로그램 코드 리포지토리</span><span class="sxs-lookup"><span data-stu-id="e47f5-162">Application Code Repository</span></span>

<span data-ttu-id="e47f5-163">코드를 팀과 공유할 준비가 될 때마다 팀의 공유 원본 리포지토리에 변경 내용을 원본 로컬 리포지토리에서 푸시할 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-163">Whenever you're ready to share your code with your team, you should push your changes from your local source repository to your team's shared source repository.</span></span> <span data-ttu-id="e47f5-164">사용자 지정 분기에서 작업 한 경우이 단계 일반적 코드 공유 분기에 병합 (아마도 방법으로 [끌어오기 요청](https://docs.microsoft.com/vsts/git/pull-requests)).</span><span class="sxs-lookup"><span data-stu-id="e47f5-164">If you've been working in a custom branch, this step usually involves merging your code into a shared branch (perhaps by means of a [pull request](https://docs.microsoft.com/vsts/git/pull-requests)).</span></span>

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a><span data-ttu-id="e47f5-165">3단계.</span><span class="sxs-lookup"><span data-stu-id="e47f5-165">Step 3.</span></span> <span data-ttu-id="e47f5-166">빌드 서버: 연속 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-166">Build Server: Continuous Integration.</span></span> <span data-ttu-id="e47f5-167">빌드, 테스트, 패키지</span><span class="sxs-lookup"><span data-stu-id="e47f5-167">Build, Test, Package</span></span>

<span data-ttu-id="e47f5-168">공유 응용 프로그램 코드 저장소에 새 커밋이 때마다 빌드 서버에서 새 빌드가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-168">A new build is triggered on the build server whenever a new commit is made to the shared application code repository.</span></span> <span data-ttu-id="e47f5-169">CI 프로세스의 일환으로,이 빌드는 응용 프로그램 컴파일 및 모든 것이 예상 대로 작동을 확인 하는 자동화 된 테스트 실행 완벽 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-169">As part of the CI process, this build should fully compile the application and run automated tests to confirm everything is working as expected.</span></span> <span data-ttu-id="e47f5-170">CI 프로세스의 최종 결과는 배포 준비 완료 웹 응용 프로그램의 패키지 버전 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-170">The end result of the CI process should be a packaged version of the web app, ready for deployment.</span></span>

#### <a name="step-4-build-server-continuous-delivery"></a><span data-ttu-id="e47f5-171">4단계.</span><span class="sxs-lookup"><span data-stu-id="e47f5-171">Step 4.</span></span> <span data-ttu-id="e47f5-172">빌드 서버: 지속적인 업데이트</span><span class="sxs-lookup"><span data-stu-id="e47f5-172">Build Server: Continuous Delivery</span></span>

<span data-ttu-id="e47f5-173">한 번 성공으로 빌드, CD 프로세스가 가져옵니다 생성 빌드 아티팩트.</span><span class="sxs-lookup"><span data-stu-id="e47f5-173">Once a build as succeeded, the CD process will pick up the build artifacts produced.</span></span> <span data-ttu-id="e47f5-174">여기에 웹 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-174">This will include a web deploy package.</span></span> <span data-ttu-id="e47f5-175">빌드 서버에서 새로 만든 모든 기존 서비스 대체 되는 Azure 앱 서비스에이 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-175">The build server will deploy this package to Azure App Service, replacing any existing service with the newly created one.</span></span> <span data-ttu-id="e47f5-176">일반적으로이 단계는 스테이징 환경을 대상으로 하지만 일부 응용 프로그램 CD 프로세스를 통해 프로덕션 환경에 직접 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-176">Typically this step targets a staging environment, but some applications deploy directly to production through a CD process.</span></span>

#### <a name="step-5-azure-app-service-web-app"></a><span data-ttu-id="e47f5-177">5단계.</span><span class="sxs-lookup"><span data-stu-id="e47f5-177">Step 5.</span></span> <span data-ttu-id="e47f5-178">Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="e47f5-178">Azure App Service.</span></span> <span data-ttu-id="e47f5-179">웹 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-179">Web App.</span></span>

<span data-ttu-id="e47f5-180">배포 된 후 Azure 앱 서비스 웹 앱의 컨텍스트 내에서 ASP.NET Core 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-180">Once deployed, the ASP.NET Core application runs within the context of an Azure App Service Web App.</span></span> <span data-ttu-id="e47f5-181">이 웹 앱을 모니터링할 수 있습니다 및 Azure 포털을 사용 하 여를 추가로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-181">This Web App can be monitored and further configured using the Azure Portal.</span></span>

#### <a name="step-6-production-monitoring-and-diagnostics"></a><span data-ttu-id="e47f5-182">6단계.</span><span class="sxs-lookup"><span data-stu-id="e47f5-182">Step 6.</span></span> <span data-ttu-id="e47f5-183">프로덕션 모니터링 및 진단</span><span class="sxs-lookup"><span data-stu-id="e47f5-183">Production Monitoring and Diagnostics</span></span>

<span data-ttu-id="e47f5-184">웹 앱이 실행 되는 동안 응용 프로그램의 상태를 모니터링할 수 있으며 진단 정보 및 사용자 동작 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-184">While the Web App is running, you can monitor the health of the application and collect diagnostics and user behavior data.</span></span> <span data-ttu-id="e47f5-185">Application Insights는 Visual Studio에 포함 하 고 ASP.NET 응용 프로그램에 대 한 자동 계측을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-185">Application Insights is included in Visual Studio, and offers automatic instrumentation for ASP.NET apps.</span></span> <span data-ttu-id="e47f5-186">사용, 예외, 요청, 성능 및 로그에 대 한 정보와 함께 있습니다 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47f5-186">It can provide you with information on usage, exceptions, requests, performance, and logs.</span></span>

## <a name="references"></a><span data-ttu-id="e47f5-187">참조</span><span class="sxs-lookup"><span data-stu-id="e47f5-187">References</span></span>

<span data-ttu-id="e47f5-188">**빌드 및 Azure에 ASP.NET Core 응용 프로그램 배포**</span><span class="sxs-lookup"><span data-stu-id="e47f5-188">**Build and Deploy Your ASP.NET Core App to Azure**</span></span>  
<https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core>


>[!div class="step-by-step"]
<span data-ttu-id="e47f5-189">[이전] [다음] (azure-hosting-recommendations-for-asp-net-web-apps.md) (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e47f5-189">[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)</span></span>
