---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 6fb1463b811d985f54b9a99e59d1280eaa040256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482816"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="af67f-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="af67f-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="af67f-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="af67f-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="af67f-104">설명</span><span class="sxs-lookup"><span data-stu-id="af67f-104">Description</span></span>  
 <span data-ttu-id="af67f-105">메시지를 처리하는 동안 스레드가 전환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af67f-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="af67f-106">메시지 처리는 다음 이유로 인해 일시 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af67f-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="af67f-107">ConcurrencyMode가 단일하거나 재진입할 수 있으며, 서비스가 다른 메시지를 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af67f-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="af67f-108">트랜잭션이 사용하도록 설정되어 있으며, 서비스가 다른 트랜잭션을 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af67f-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="af67f-109">현재 동기화 컨텍스트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="af67f-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af67f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af67f-110">See Also</span></span>  
 [<span data-ttu-id="af67f-111">추적</span><span class="sxs-lookup"><span data-stu-id="af67f-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="af67f-112">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="af67f-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="af67f-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="af67f-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
