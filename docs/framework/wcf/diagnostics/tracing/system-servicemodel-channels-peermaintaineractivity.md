---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3cde90bf5e9c57ff54378eaaf970aec219871a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="c6d1e-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="c6d1e-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="c6d1e-103">PeerMaintainer 모듈이 특정 작업을 수행하고 있습니다(상세 정보는 추적 메시지 본문에 포함).</span><span class="sxs-lookup"><span data-stu-id="c6d1e-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="c6d1e-104">설명</span><span class="sxs-lookup"><span data-stu-id="c6d1e-104">Description</span></span>  
 <span data-ttu-id="c6d1e-105">이 추적은 다양한 PeerMaintainer 작업을 수행하는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="c6d1e-106">PeerMaintainer는 PeerNode의 내부 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="c6d1e-107">1분마다 또는 메시지 32개를 받을 때마다 PeerMaintainer는 교환된 메시지 수 및 유용한 메시지(손상되지 않은 비중복 메시지) 수에 대한 통계가 포함된 LinkUtility 메시지를 인접한 환경에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="c6d1e-108">이렇게 하면 특정 환경의 링크 유틸리티를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="c6d1e-109">약 5분마다 유지 관리자는 환경 연결의 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="c6d1e-110">환경 연결 수가 이상적인 값을 초과하면 유지 관리자가 가장 덜 유용한 연결을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="c6d1e-111">연결 수가 충분하지 않으면 유지 관리자가 새 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d1e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6d1e-112">See Also</span></span>  
 [<span data-ttu-id="c6d1e-113">추적</span><span class="sxs-lookup"><span data-stu-id="c6d1e-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c6d1e-114">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="c6d1e-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c6d1e-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="c6d1e-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
