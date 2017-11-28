---
title: "WCF 라이브러리 프로젝트 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04567b0b06ef5c8f105e866e150bfaa221d64057
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="e279d-102">WCF 라이브러리 프로젝트 배포</span><span class="sxs-lookup"><span data-stu-id="e279d-102">Deploying a WCF Library Project</span></span>
<span data-ttu-id="e279d-103">이 항목에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 라이브러리 프로젝트를 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="e279d-104">WCF 서비스 라이브러리 배포</span><span class="sxs-lookup"><span data-stu-id="e279d-104">Deploying a WCF Service Library</span></span>  
 <span data-ttu-id="e279d-105">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리는 DDL(동적 연결 라이브러리)입니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="e279d-106">따라서 자체적으로 실행될 수 없으며</span><span class="sxs-lookup"><span data-stu-id="e279d-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="e279d-107">호스팅 환경에서 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="e279d-108">이 프로세스에 대 한 자세한 내용은 참조 [호스팅 및 WCF 서비스를 사용해](http://go.microsoft.com/fwlink/?LinkId=99932)합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-108">For more information about this process, see [Hosting and Consuming WCF Services](http://go.microsoft.com/fwlink/?LinkId=99932).</span></span>  
  
 <span data-ttu-id="e279d-109">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리는 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와 같이 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-109">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be deployed like any other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="e279d-110">그러나 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]는 DLL의 구성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-110">However, be aware that [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support configuration for DLLs.</span></span> <span data-ttu-id="e279d-111"><xref:System.Configuration>은 응용 프로그램 도메인당 하나의 구성 파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="e279d-112">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트는 개발하는 동안 라이브러리의 App.config 파일을 제공하여 이 제한을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-112">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="e279d-113">그러나 App.config 파일은 배포 후에 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="e279d-114">구성 코드를 호스팅 환경에서 인식하는 구성 파일로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="e279d-115">자체 호스팅의 경우 App.config 파일의 내용을 호스팅 실행 파일의 App.config 파일에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="e279d-116">IIS를 사용하여 서비스를 호스팅하려면 App.config 파일의 내용을 가상 디렉터리의 Web.config 파일에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e279d-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
