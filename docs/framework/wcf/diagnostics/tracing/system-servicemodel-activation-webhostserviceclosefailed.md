---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: aa9df795ee8601a4c4f4e2ce7427ffb0dd530bba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476489"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="94cfe-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="94cfe-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="94cfe-103">서비스를 정상적으로 닫을 수 없고 중단된 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="94cfe-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="94cfe-104">설명</span><span class="sxs-lookup"><span data-stu-id="94cfe-104">Description</span></span>  
 <span data-ttu-id="94cfe-105">이 오류 코드는 로그 파일에서만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="94cfe-105">This error code only appears in the log file.</span></span> <span data-ttu-id="94cfe-106">예를 들어 중단을 이미 호출한 후 서비스를 닫으려는 경우와 같이 일반적으로 프로그래밍 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94cfe-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="94cfe-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="94cfe-107">Troubleshooting</span></span>  
 <span data-ttu-id="94cfe-108">응용 프로그램 소스 코드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94cfe-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cfe-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94cfe-109">See Also</span></span>  
 [<span data-ttu-id="94cfe-110">추적</span><span class="sxs-lookup"><span data-stu-id="94cfe-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="94cfe-111">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="94cfe-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="94cfe-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="94cfe-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
