---
title: "서비스 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75069b00fa07078ff0eb2d49e64f046d5415d154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-services"></a><span data-ttu-id="c9674-102">서비스 배포</span><span class="sxs-lookup"><span data-stu-id="c9674-102">Deploying Services</span></span>
<span data-ttu-id="c9674-103">이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램을 런타임 환경에 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9674-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="c9674-104">응용 프로그램의 호스팅 환경 선택</span><span class="sxs-lookup"><span data-stu-id="c9674-104">Choosing the Hosting Environment for Your Application</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c9674-105"> 서비스는 관리 코드를 지원하는 모든 Windows 프로세스에서 실행할 수 있게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9674-105"> services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="c9674-106">활성화할 서비스는 서비스를 만들고 컨텍스트와 수명을 제어하는 런타임 환경에 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9674-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="c9674-107">호스팅 옵션은 가장 간단한 콘솔 응용 프로그램에서 Windows 서비스, IIS(Internet Information Services), 또는 WAS(Windows Activation Service)에서 관리하는 작업자 프로세스 등의 서버 환경까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="c9674-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="c9674-108">다른 호스팅 옵션을 검토 하 여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램 참조 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9674-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9674-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9674-109">See Also</span></span>  
 [<span data-ttu-id="c9674-110">호스팅</span><span class="sxs-lookup"><span data-stu-id="c9674-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="c9674-111">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="c9674-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
