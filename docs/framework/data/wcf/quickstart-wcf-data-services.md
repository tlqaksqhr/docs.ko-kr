---
title: "빠른 시작(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a5223f9b6e7854ec6575e8673bb874a1b9b60df7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="bb61a-102">빠른 시작(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="bb61a-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="bb61a-103">이 빠른 시작을 사용 하면 익숙해지는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 및 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 일련의 항목에서는 지 원하는 작업을 통해 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="bb61a-104">학습 내용</span><span class="sxs-lookup"><span data-stu-id="bb61a-104">What You Will Learn</span></span>  
 <span data-ttu-id="bb61a-105">이 퀵 스타트의 첫 번째 작업에서는 데이터 서비스를 만들어 Northwind 샘플 데이터베이스에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="bb61a-106">이후 항목에서는 웹 브라우저를 사용하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스하고 클라이언트 라이브러리를 사용하여 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 피드를 사용하는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 클라이언트 응용 프로그램도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bb61a-107">필수 조건</span><span class="sxs-lookup"><span data-stu-id="bb61a-107">Prerequisites</span></span>  
 <span data-ttu-id="bb61a-108">이 퀵 스타트를 수행하려면 다음 구성 요소를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="bb61a-109">.</span><span class="sxs-lookup"><span data-stu-id="bb61a-109">.</span></span>  
  
-   <span data-ttu-id="bb61a-110">[!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bb61a-111">여기에는 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]의 기본 설치에 들어 있는 SQL Server Express가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="bb61a-112">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="bb61a-112">The Northwind sample database.</span></span> <span data-ttu-id="bb61a-113">이 샘플 데이터베이스를 다운로드하려면 [SQL Server용 샘플 데이터베이스](http://go.microsoft.com/fwlink/?linkid=24758)다운로드 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb61a-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="bb61a-114">WCF Data Services 퀵 스타트 작업</span><span class="sxs-lookup"><span data-stu-id="bb61a-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="bb61a-115">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="bb61a-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="bb61a-116">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램과 데이터 모델을 정의하고, 데이터 서비스를 만들고, 리소스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="bb61a-117">웹 브라우저에서 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="bb61a-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="bb61a-118">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 에서 서비스를 시작하고 웹 브라우저를 통해 HTTP GET 요청을 노출된 피드로 전송하여 서비스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="bb61a-119">.NET Framework 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="bb61a-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="bb61a-120">[!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 클라이언트 응용 프로그램을 만들어 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용하고, 데이터를 Windows 컨트롤에 바인딩하고, 바인딩된 컨트롤의 데이터를 변경한 후 변경 내용을 데이터 서비스로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb61a-121">완성된 퀵 스타트 버전의 프로젝트 파일은 [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) 페이지에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb61a-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bb61a-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bb61a-122">Next Steps</span></span>  
 <span data-ttu-id="bb61a-123">[퀵 스타트를 시작합니다](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="bb61a-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb61a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb61a-124">See Also</span></span>  
 [<span data-ttu-id="bb61a-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bb61a-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
