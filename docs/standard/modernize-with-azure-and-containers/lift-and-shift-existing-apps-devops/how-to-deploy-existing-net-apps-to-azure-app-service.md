---
title: "Azure 앱 서비스를 기존.NET 응용 프로그램을 배포 하는 방법"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Azure 앱 서비스를 기존.NET 응용 프로그램을 배포 하는 방법"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: c83703c6f3dede0f92263e0d46bf48525c3eefaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="0a1ec-103">Azure 앱 서비스를 기존.NET 응용 프로그램을 배포 하는 방법</span><span class="sxs-lookup"><span data-stu-id="0a1ec-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="0a1ec-104">Azure 앱 서비스의 웹 응용 프로그램 기능은 호스팅 웹 사이트 및 웹 응용 프로그램에 최적화 된 계산을 완전히 관리 되는 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="0a1ec-105">Microsoft Azure 사용에서이 PaaS 제품 중점을 비즈니스 논리를 실행 하 고 앱의 크기를 조정 하도록 인프라에는 Azure를 담당 하는 동안.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="0a1ec-106">사이트의 유효성을 검사 하 고 있는 Azure 앱 서비스 Migration Assistant 앱 서비스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0a1ec-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="0a1ec-107">일반적으로 응용 프로그램 서비스에 응용 프로그램을 이동 하는 Visual Studio에서 새 응용 프로그램을 만들 때 하는 것은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="0a1ec-108">그러나 응용 프로그램 서비스에는 기존 응용 프로그램을 마이그레이션할 계획 이라면 먼저 응용 프로그램의 모든 종속성은 앱 서비스와 호환 되는지 여부를 평가할 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="0a1ec-109">서버 운영 체제 및 서버에 설치 된 모든 타사 소프트웨어와 같은 종속성 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="0a1ec-110">사용할 수 있습니다 [Azure 앱 서비스 Migration Assistant](https://www.migratetoazure.net/) 를 사이트 분석 한 다음 응용 프로그램 서비스에 Windows 및 Linux 웹 서버에서 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="0a1ec-111">마이그레이션의 일환으로,이 도구는 웹 응용 프로그램을 만듭니다 및 Azure에서 데이터베이스 필요에 따라 콘텐츠를 게시 하 고 데이터베이스를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="0a1ec-112">Azure 앱 서비스 Migration Assistant는 클라우드로 Windows Server에서 실행 되는 IIS에서로 마이그레이션하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="0a1ec-113">응용 프로그램 서비스는 Windows Server 2003 및 이후 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> <span data-ttu-id="0a1ec-115">**그림 4-5입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a1ec-115">**Figure 4-5.**</span></span> <span data-ttu-id="0a1ec-116">Azure 앱 서비스 마이그레이션 길잡이 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="0a1ec-116">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="0a1ec-117">앱 서비스 마이그레이션 도우미는 웹 서버에서 Azure 클라우드 웹 사이트를 이동 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-117">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="0a1ec-118">앱 서비스, 웹 사이트를 마이그레이션한 후 사이트에 안전 하 고 효율적으로 실행에 필요한 모든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-118">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="0a1ec-119">사이트를 설정 하 고 Azure 클라우드 PaaS 서비스 (앱 서비스)에서 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-119">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="0a1ec-120">앱 서비스 마이그레이션 도구 웹 사이트를 분석 하 고 응용 프로그램 서비스를 이동 하기 위한의 호환성을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-120">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="0a1ec-121">분석 만족 했으면 응용 프로그램 서비스 Migration Assistant 콘텐츠, 데이터 및 설정을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-121">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="0a1ec-122">사이트 매우 호환 되지 않으면 마이그레이션 도구를 작동 하도록 조정 해야 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ec-122">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0a1ec-123">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="0a1ec-123">Additional resources</span></span>

-   <span data-ttu-id="0a1ec-124">**Azure 앱 서비스 마이그레이션 길잡이**</span><span class="sxs-lookup"><span data-stu-id="0a1ec-124">**Azure App Service Migration Assistant**</span></span>

    [<span data-ttu-id="0a1ec-125">https://www.migratetoazure.net/</span><span class="sxs-lookup"><span data-stu-id="0a1ec-125">https://www.migratetoazure.net/</span></span>](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="0a1ec-126">[이전](what-about-cloud-optimized-applications.md)
[다음](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="0a1ec-126">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>
