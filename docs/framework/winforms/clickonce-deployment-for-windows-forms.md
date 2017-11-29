---
title: "Windows Forms에 대한 ClickOnce 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ClickOnce deployment [Windows Forms]
- Windows Forms, ClickOnce deployment
- walkthroughs [Windows Forms], ClickOnce deployment
ms.assetid: 1451fce9-1965-4a03-b4d3-831b5fe4ad66
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 550ef4951cc7d5b0a9b25c5e7d038588b0a911f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="clickonce-deployment-for-windows-forms"></a><span data-ttu-id="f005a-102">Windows Forms에 대한 ClickOnce 배포</span><span class="sxs-lookup"><span data-stu-id="f005a-102">ClickOnce Deployment for Windows Forms</span></span>
<span data-ttu-id="f005a-103">다음 항목에서는 Windows Forms 응용 프로그램을 클라이언트 컴퓨터에 쉽게 배포하는 데 사용되는 기술인 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-103">The following topics describe [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], a technology used for easily deploying Windows Forms applications to client computers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f005a-104">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f005a-104">Related Sections</span></span>  
 [<span data-ttu-id="f005a-105">ClickOnce 배포 전략 선택</span><span class="sxs-lookup"><span data-stu-id="f005a-105">Choosing a ClickOnce Deployment Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)  
 <span data-ttu-id="f005a-106">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 배포하는 여러 가지 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-106">Presents several options for deploying [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="f005a-107">ClickOnce 업데이트 전략 선택</span><span class="sxs-lookup"><span data-stu-id="f005a-107">Choosing a ClickOnce Update Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-update-strategy)  
 <span data-ttu-id="f005a-108">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 업데이트하는 여러 가지 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-108">Presents several options for updating [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="f005a-109">ClickOnce 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="f005a-109">Securing ClickOnce Applications</span></span>](/visualstudio/deployment/securing-clickonce-applications)  
 <span data-ttu-id="f005a-110">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 배포의 보안 관련 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-110">Explains the security implications of [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployment.</span></span>  
  
 [<span data-ttu-id="f005a-111">ClickOnce 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f005a-111">Troubleshooting ClickOnce Deployments</span></span>](/visualstudio/deployment/troubleshooting-clickonce-deployments)  
 <span data-ttu-id="f005a-112">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램 배포 시 발생할 수 있는 다양한 문제를 설명하고 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]에서 생성할 수 있는 최상위 오류 메시지를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-112">Describes various problems that can occur when deploying [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications, and documents the top-level error messages that [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] might generate.</span></span>  
  
 [<span data-ttu-id="f005a-113">ClickOnce 및 응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="f005a-113">ClickOnce and Application Settings</span></span>](/visualstudio/deployment/clickonce-and-application-settings)  
 <span data-ttu-id="f005a-114">이후 검색을 위해 응용 프로그램 및 사용자 설정을 저장하는 응용 프로그램 설정을 통해 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 배포가 작동하는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-114">Describes how [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployment works with application settings, which stores application and user settings for future retrieval.</span></span>  
  
 [<span data-ttu-id="f005a-115">신뢰할 수 있는 응용 프로그램 배포 개요</span><span class="sxs-lookup"><span data-stu-id="f005a-115">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)  
 <span data-ttu-id="f005a-116">클라이언트 컴퓨터에서 신뢰할 수 있는 응용 프로그램을 상위 권한 수준으로 실행할 수 있게 해주는 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-116">Describes a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] feature that allows trusted applications to run with a higher level of permission on client computers.</span></span>  
  
 [<span data-ttu-id="f005a-117">ClickOnce 및 Authenticode</span><span class="sxs-lookup"><span data-stu-id="f005a-117">ClickOnce and Authenticode</span></span>](/visualstudio/deployment/clickonce-and-authenticode)  
 <span data-ttu-id="f005a-118">신뢰할 수 있는 응용 프로그램 배포에서 Authenticode 기술을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-118">Describes how Authenticode technology is used in trusted application deployment.</span></span>  
  
 [<span data-ttu-id="f005a-119">연습: ClickOnce 응용 프로그램 수동 배포</span><span class="sxs-lookup"><span data-stu-id="f005a-119">Walkthrough: Manually Deploying a ClickOnce Application</span></span>](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 <span data-ttu-id="f005a-120">Visual Studio를 사용하지 않고 명령줄 및 SDK 도구를 통해 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 배포하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-120">Demonstrates using command-line and SDK tools to deploy a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application without using Visual Studio.</span></span>  
  
 [<span data-ttu-id="f005a-121">방법: ClickOnce 응용 프로그램의 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가</span><span class="sxs-lookup"><span data-stu-id="f005a-121">How to: Add a Trusted Publisher to a Client Computer for ClickOnce Applications</span></span>](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)  
 <span data-ttu-id="f005a-122">신뢰할 수 있는 응용 프로그램 배포에 필요한 클라이언트 컴퓨터의 일회성 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-122">Demonstrates the one-time configuration of client computers required for trusted application deployment.</span></span>  
  
 [<span data-ttu-id="f005a-123">방법: 배포 업데이트를 위한 대체 위치 지정</span><span class="sxs-lookup"><span data-stu-id="f005a-123">How to: Specify an Alternate Location for Deployment Updates</span></span>](/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates)  
 <span data-ttu-id="f005a-124">SDK 도구를 사용하여 다른 위치에서 응용 프로그램의 새 버전을 확인하도록 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-124">Demonstrates configuring a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application, using SDK tools, to check a different location for new versions of an application.</span></span>  
  
 [<span data-ttu-id="f005a-125">연습: ClickOnce 배포 API에서 요청 시 어셈블리 다운로드</span><span class="sxs-lookup"><span data-stu-id="f005a-125">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api)  
 <span data-ttu-id="f005a-126">응용 프로그램이 처음 로드하려고 시도할 때 API 호출을 사용하여 어셈블리를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-126">Demonstrates using API calls to retrieve an assembly the first time your application attempts to load it.</span></span>  
  
 [<span data-ttu-id="f005a-127">방법: 온라인 ClickOnce 응용 프로그램에서 쿼리 문자열 정보 검색</span><span class="sxs-lookup"><span data-stu-id="f005a-127">How to: Retrieve Query String Information in an Online ClickOnce Application</span></span>](/visualstudio/deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application)  
 <span data-ttu-id="f005a-128">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 실행하는 데 사용되는 URL에서 매개 변수를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-128">Demonstrates retrieving parameters from the URL used to run a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application.</span></span>  
  
 [<span data-ttu-id="f005a-129">ClickOnce 캐시 개요</span><span class="sxs-lookup"><span data-stu-id="f005a-129">ClickOnce Cache Overview</span></span>](/visualstudio/deployment/clickonce-cache-overview)  
 <span data-ttu-id="f005a-130">로컬 컴퓨터에 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램을 저장하는 데 사용되는 캐시를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-130">Describes the cache used to store [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications on the local computer.</span></span>  
  
 [<span data-ttu-id="f005a-131">ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="f005a-131">Accessing Local and Remote Data in ClickOnce Applications</span></span>](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)  
 <span data-ttu-id="f005a-132">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램에서 로컬 데이터 파일 및 원격 데이터 소스에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-132">Describes how to access local data files and remote data sources from a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application.</span></span>  
  
 [<span data-ttu-id="f005a-133">방법: ClickOnce 응용 프로그램에 데이터 파일 포함</span><span class="sxs-lookup"><span data-stu-id="f005a-133">How to: Include a Data File in a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application)  
 <span data-ttu-id="f005a-134">[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 데이터 디렉터리에서 사용할 수 있도록 파일을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f005a-134">Demonstrates how to mark a file so that it is available in the [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] data directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f005a-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f005a-135">See Also</span></span>  
 [<span data-ttu-id="f005a-136">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="f005a-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="f005a-137">ClickOnce 응용 프로그램 게시</span><span class="sxs-lookup"><span data-stu-id="f005a-137">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)  
 [<span data-ttu-id="f005a-138">명령줄에서 ClickOnce 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="f005a-138">Building ClickOnce Applications from the Command Line</span></span>](/visualstudio/deployment/building-clickonce-applications-from-the-command-line)  
 [<span data-ttu-id="f005a-139">System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버그</span><span class="sxs-lookup"><span data-stu-id="f005a-139">Debugging ClickOnce Applications That Use System.Deployment.Application</span></span>](http://msdn.microsoft.com/library/86f31948-2ca8-47c0-8e8b-c2b817bbf79f)  
 [<span data-ttu-id="f005a-140">ClickOnce를 사용하여 COM 구성 요소 배포</span><span class="sxs-lookup"><span data-stu-id="f005a-140">Deploying COM Components with ClickOnce</span></span>](/visualstudio/deployment/deploying-com-components-with-clickonce)  
 [<span data-ttu-id="f005a-141">방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시</span><span class="sxs-lookup"><span data-stu-id="f005a-141">How to: Publish a ClickOnce Application using the Publish Wizard</span></span>](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)
