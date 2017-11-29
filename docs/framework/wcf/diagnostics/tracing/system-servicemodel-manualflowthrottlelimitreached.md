---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 556afe035697ee35d7ba86185b5b768a645c32c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="f5273-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="f5273-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="f5273-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="f5273-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="f5273-104">설명</span><span class="sxs-lookup"><span data-stu-id="f5273-104">Description</span></span>  
 <span data-ttu-id="f5273-105">시스템이 ManualFlowControlLimit 스로틀에 대해 설정된 제한에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5273-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="f5273-106">스로틀 값은 ServiceHost 또는 InstanceContext에서 ManualFlowControlLimit 속성을 수정하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5273-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="f5273-107">수동 흐름 제어 제한을 처음에 0으로 줄인 경우 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5273-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="f5273-108">다음에 0으로 변경하면 추적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5273-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="f5273-109">인스턴스 컨텍스트에 대한 흐름 제어 제한은 각 컨텍스트에 대해 한 번 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5273-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5273-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5273-110">See Also</span></span>  
 [<span data-ttu-id="f5273-111">추적</span><span class="sxs-lookup"><span data-stu-id="f5273-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f5273-112">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="f5273-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f5273-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="f5273-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
