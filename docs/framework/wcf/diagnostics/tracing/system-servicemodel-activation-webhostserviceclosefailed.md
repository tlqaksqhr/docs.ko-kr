---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc2b0dc75e8e8748e25c1faf28150e0c156a20ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="97126-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="97126-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="97126-103">서비스를 정상적으로 닫을 수 없고 중단된 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="97126-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="97126-104">설명</span><span class="sxs-lookup"><span data-stu-id="97126-104">Description</span></span>  
 <span data-ttu-id="97126-105">이 오류 코드는 로그 파일에서만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="97126-105">This error code only appears in the log file.</span></span> <span data-ttu-id="97126-106">예를 들어 중단을 이미 호출한 후 서비스를 닫으려는 경우와 같이 일반적으로 프로그래밍 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="97126-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="97126-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="97126-107">Troubleshooting</span></span>  
 <span data-ttu-id="97126-108">응용 프로그램 소스 코드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97126-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97126-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97126-109">See Also</span></span>  
 [<span data-ttu-id="97126-110">추적</span><span class="sxs-lookup"><span data-stu-id="97126-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="97126-111">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="97126-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="97126-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="97126-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
