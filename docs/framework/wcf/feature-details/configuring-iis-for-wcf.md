---
title: "Windows Communication Foundation에 대해 Internet Information Services 7.0 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 185fa5e641a1834a7c5f7906b5e5cf84dacaa9f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a><span data-ttu-id="53a06-102">Windows Communication Foundation에 대해 Internet Information Services 7.0 구성</span><span class="sxs-lookup"><span data-stu-id="53a06-102">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>
<span data-ttu-id="53a06-103">IIS(인터넷 정보 서비스) 7.0은 필요한 구성 요소를 선택적으로 설치할 수 있는 모듈형 디자인입니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-103">Internet Information Services (IIS) 7.0 has a modular design that allows you to selectively install components that are required.</span></span> <span data-ttu-id="53a06-104">이러한 디자인은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에 도입된 새로운 매니페스트 기반의 컴포넌트화 기술을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-104">This design is based on the new manifest-driven componentization technology introduced in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="53a06-105">[!INCLUDE[iisver](../../../../includes/iisver-md.md)]에는 개별적으로 설치할 수 있는 40개 이상의 독립 실행형 기능 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-105">There are more than 40 standalone feature components of [!INCLUDE[iisver](../../../../includes/iisver-md.md)] that can be installed independently.</span></span> <span data-ttu-id="53a06-106">따라서 IT 전문가는 필요에 따라 편리하게 설치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-106">This allows IT professionals to easily customize the installation as required.</span></span> <span data-ttu-id="53a06-107">이 항목에서는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]을 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]와 함께 사용할 수 있도록 구성하는 방법과 필요한 구성 요소를 결정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-107">This topic discusses how to configure [!INCLUDE[iisver](../../../../includes/iisver-md.md)] for use with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and determine which components are required.</span></span>  
  
## <a name="minimal-installation-installing-was"></a><span data-ttu-id="53a06-108">최소 설치: WAS 설치</span><span class="sxs-lookup"><span data-stu-id="53a06-108">Minimal Installation: Installing WAS</span></span>  
 <span data-ttu-id="53a06-109">전체 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 패키지를 최소 설치하려면 WAS(Windows Process Activation Service)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-109">The minimal installation of the whole [!INCLUDE[iisver](../../../../includes/iisver-md.md)] package is to install the Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="53a06-110">WAS는 독립 실행형 기능으로, 모든 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 운영 체제(Home Basic, Home Premium, Business, Ultimate 및 Enterprise)에서 사용할 수 있는 [!INCLUDE[wv](../../../../includes/wv-md.md)]의 유일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-110">WAS is a standalone feature and it is the only feature from the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] that is available for all [!INCLUDE[wv](../../../../includes/wv-md.md)] operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).</span></span>  
  
 <span data-ttu-id="53a06-111">제어판에서 클릭 **프로그램** 클릭 하 고 **Windows 기능 설정 또는 해제** 아래에 나열 된 **프로그램 및 기능**, WAS 구성 요소가에 표시 되는 다음 그림과 같이 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-111">From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.</span></span>  
  
 <span data-ttu-id="53a06-112">![기능 켜기 / 끄기 대화](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span><span class="sxs-lookup"><span data-stu-id="53a06-112">![Turn Features On or Off Dialog](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span></span>  
  
 <span data-ttu-id="53a06-113">이 기능에는 다음과 같은 하위 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-113">This feature has the following sub-components:</span></span>  
  
-   <span data-ttu-id="53a06-114">.NET 환경</span><span class="sxs-lookup"><span data-stu-id="53a06-114">.NET Environment</span></span>  
  
-   <span data-ttu-id="53a06-115">구성 API</span><span class="sxs-lookup"><span data-stu-id="53a06-115">Configuration APIs</span></span>  
  
-   <span data-ttu-id="53a06-116">프로세스 모델</span><span class="sxs-lookup"><span data-stu-id="53a06-116">Process Model</span></span>  
  
 <span data-ttu-id="53a06-117">만 WAS의 루트 노드를 선택 하는 경우는 **프로세스 모델** 하위 노드는 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-117">If you select the root node of WAS, only the **Process Model** sub-node is checked by default.</span></span> <span data-ttu-id="53a06-118">이 설치에서는 웹 서버에 대한 지원이 없으므로 WAS만 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-118">Please note that with this installation you are only installing WAS, because there is no support for a Web server.</span></span>  
  
 <span data-ttu-id="53a06-119">있도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 또는 모든 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작동 하도록 하는 응용 프로그램 확인는 **.NET 환경** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-119">To make [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or any [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application to work, check the **.NET Environment** checkbox.</span></span> <span data-ttu-id="53a06-120">이는 모든 WAS 구성 요소가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작동에 필요함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-120">This means that all of WAS components are required to make [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] to work well.</span></span> <span data-ttu-id="53a06-121">이러한 구성 요소는 일단 설치되면 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-121">These are automatically checked once you install any of those components.</span></span>  
  
## <a name="iis-70-default-installation"></a><span data-ttu-id="53a06-122">IIS 7.0: 기본 설치</span><span class="sxs-lookup"><span data-stu-id="53a06-122">IIS 7.0: Default Installation</span></span>  
 <span data-ttu-id="53a06-123">선택 하 여는 **인터넷 정보 서비스** 다음 그림에 나와 있는 것 처럼 기능 하위 노드 일부가 자동으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-123">By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="53a06-124">![IIS 7.0 기능에 대 한 기본 설정](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span><span class="sxs-lookup"><span data-stu-id="53a06-124">![Default settings for IIS 7.0 features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span></span>  
  
 <span data-ttu-id="53a06-125">이것은 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]의 기본 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-125">This is the default installation of [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="53a06-126">이 설치에서는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]을 사용하여 HTML 페이지나 기타 콘텐츠와 같은 정적 콘텐츠를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-126">With this installation, you can use [!INCLUDE[iisver](../../../../includes/iisver-md.md)] to service static content (such as HTML pages and other content).</span></span> <span data-ttu-id="53a06-127">하지만 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 또는 CGI 응용 프로그램을 실행하거나 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-127">However, you cannot run [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] or CGI applications or host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
## <a name="iis-70-installation-with-aspnet-support"></a><span data-ttu-id="53a06-128">IIS 7.0: ASP.NET 지원과 함께 설치</span><span class="sxs-lookup"><span data-stu-id="53a06-128">IIS 7.0: Installation with ASP.NET Support</span></span>  
 <span data-ttu-id="53a06-129">IIS 7.0에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]이 작동하도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-129">You must install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] to make [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] work on IIS 7.0.</span></span> <span data-ttu-id="53a06-130">확인 한 후 **ASP.NET**, 화면이 다음 그림과 같이 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-130">After checking **ASP.NET**, your screen should look like the following illustration.</span></span>  
  
 <span data-ttu-id="53a06-131">![Asp.NET 필수 설정](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span><span class="sxs-lookup"><span data-stu-id="53a06-131">![Asp.NET required settings](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span></span>  
  
 <span data-ttu-id="53a06-132">이는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램이 모두 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에서 작동하기 위한 최소 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-132">This is the minimal environment for both [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applications to work in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span>  
  
## <a name="iis-70-installation-with-iis-60-compatibility-components"></a><span data-ttu-id="53a06-133">IIS 7.0: IIS 6.0 호환성 구성 요소와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="53a06-133">IIS 7.0: Installation with IIS 6.0 Compatibility Components</span></span>  
 <span data-ttu-id="53a06-134">설치할 때 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 는 Visual Studio 2005 또는 일부 다른 자동화 스크립트 또는 도구 (예: Adsutil.vbs)를 사용 하는 가상 응용 프로그램을 구성 하는 시스템에서 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 메타 베이스 API를 확인 하는 확인 된 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]  **스크립팅 도구**합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-134">When installing [!INCLUDE[iisver](../../../../includes/iisver-md.md)] on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use [!INCLUDE[iis601](../../../../includes/iis601-md.md)] Metabase API, ensure that you check the [!INCLUDE[iis601](../../../../includes/iis601-md.md)]**Scripting Tools**.</span></span> <span data-ttu-id="53a06-135">다른 하위 노드를 자동으로 확인이 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] **관리 호환성**합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-135">This automatically checks the other sub-nodes of [!INCLUDE[iis601](../../../../includes/iis601-md.md)]**Management Compatibility**.</span></span> <span data-ttu-id="53a06-136">이 작업이 끝나면 화면이 다음 그림과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-136">The following illustration shows the screen after this is done.</span></span>  
  
 <span data-ttu-id="53a06-137">![IIS 6.0 관리 호환성 설정](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span><span class="sxs-lookup"><span data-stu-id="53a06-137">![IIS 6.0 Management Compatibility Settings](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span></span>  
  
 <span data-ttu-id="53a06-138">이 설치에서는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기능을 사용하는 데 필요한 모든 요소와 웹에서 사용할 수 있는 샘플이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-138">With this installation, you have everything required to use [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and samples available on the Web.</span></span>  
  
## <a name="request-limits"></a><span data-ttu-id="53a06-139">요청 제한</span><span class="sxs-lookup"><span data-stu-id="53a06-139">Request Limits</span></span>  
 <span data-ttu-id="53a06-140">IIS 7이 설치된 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 `maxUri` 및 `maxQueryStringSize` 설정의 기본값이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-140">On [!INCLUDE[wv](../../../../includes/wv-md.md)] with IIS 7 the default value of the `maxUri` and `maxQueryStringSize` settings have been changed.</span></span> <span data-ttu-id="53a06-141">기본적으로 IIS 7.0의 요청 필터링은 URL 길이로 4096자를 허용하며 쿼리 문자열 길이로 2048자를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-141">By default, request filtering in IIS 7.0 allows a URL length of 4096 characters and a query string length of 2048 characters.</span></span> <span data-ttu-id="53a06-142">이러한 기본값을 변경하려면 다음 XML을 App.config 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="53a06-142">To change these defaults add the following XML to your App.config file.</span></span>  
  
 `<system.webServer>`  
  
 `<security>`  
  
 `<requestFiltering>`  
  
 `<requestLimits maxUrl="8192" maxQueryString="8192" />`  
  
 `</requestFiltering>`  
  
 `</security>`  
  
 `</system.webServer>`  
  
## <a name="see-also"></a><span data-ttu-id="53a06-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53a06-143">See Also</span></span>  
 [<span data-ttu-id="53a06-144">WAS Activation 아키텍처</span><span class="sxs-lookup"><span data-stu-id="53a06-144">WAS Activation Architecture</span></span>](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [<span data-ttu-id="53a06-145">WCF와 함께 사용 하도록 WAS 구성</span><span class="sxs-lookup"><span data-stu-id="53a06-145">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [<span data-ttu-id="53a06-146">방법: 설치 하 고 WCF Activation 구성 요소 구성</span><span class="sxs-lookup"><span data-stu-id="53a06-146">How to: Install and Configure WCF Activation Components</span></span>](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [<span data-ttu-id="53a06-147">Windows Server App Fabric 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="53a06-147">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
