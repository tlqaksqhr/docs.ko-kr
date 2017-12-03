---
title: "방법: COM+ 통합 응용 프로그램 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c63478620a2b604d27f2d9d154383cb0bae6b6da
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="cbd74-102">방법: COM+ 통합 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="cbd74-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="cbd74-103">COM+ 통합 응용 프로그램을 작성했다면 이를 다른 컴퓨터에 배포해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="cbd74-104">이 항목에서는 한 컴퓨터에서 다른 컴퓨터로 COM+ 통합 응용 프로그램을 이동하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="cbd74-105">COM+ 호스팅 통합 응용 프로그램 이동</span><span class="sxs-lookup"><span data-stu-id="cbd74-105">Moving a COM+ hosted Integration App</span></span>  
  
1.  <span data-ttu-id="cbd74-106">두 컴퓨터 모두에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-106">Ensure that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="cbd74-107">컴퓨터 A에서 응용 프로그램을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-107">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="cbd74-108">컴퓨터 B로 응용 프로그램을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-108">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="cbd74-109">응용 프로그램 루트 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-109">Set the Application Root Directory.</span></span> <span data-ttu-id="cbd74-110">규칙에 따라 이는 %PROGRAMFILES%/ComPlus Applications/{AppGUID}입니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5.  <span data-ttu-id="cbd74-111">컴퓨터 A에 있는 응용 프로그램 루트 디렉터리의 Application.config 및 Application.manifest 파일을 컴퓨터 B의 응용 프로그램 루트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6.  <span data-ttu-id="cbd74-112">해당 컴퓨터를 식별하기 위해 컴퓨터 B의 Application.config 파일에서 서비스 끝점 주소를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="cbd74-113">예를 들어 http://machineA/MyService를 http://machineB/MyService로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-113">For example, change http://machineA/MyService to http://machineB/MyService.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="cbd74-114">웹 호스팅 통합 응용 프로그램 이동</span><span class="sxs-lookup"><span data-stu-id="cbd74-114">Moving a Web-hosted integration application</span></span>  
  
1.  <span data-ttu-id="cbd74-115">두 컴퓨터 모두에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-115">Ensure that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="cbd74-116">컴퓨터 A에서 응용 프로그램을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-116">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="cbd74-117">컴퓨터 B로 응용 프로그램을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-117">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="cbd74-118">컴퓨터 B에서 IIS vroot를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-118">Create an IIS vroot on machine B.</span></span>  
  
5.  <span data-ttu-id="cbd74-119">컴퓨터 A의 vroot에 있는 .svc 파일(componentName.svc) 및 Web.config 파일을 컴퓨터 B의 새로 만들어진 vroot로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd74-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd74-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbd74-120">See Also</span></span>  
 [<span data-ttu-id="cbd74-121">COM + 응용 프로그램 개요와 통합</span><span class="sxs-lookup"><span data-stu-id="cbd74-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [<span data-ttu-id="cbd74-122">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="cbd74-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [<span data-ttu-id="cbd74-123">방법: COM + 서비스 모델 구성 도구를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="cbd74-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
