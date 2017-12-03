---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1386d9ac7f58e4dd692bbca3ca3915bc3fe453f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="5d6ef-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="5d6ef-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="5d6ef-103">명명된 파이프 끝점에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ef-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="5d6ef-104">지정된 제한 시간 동안 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ef-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5d6ef-105">설명</span><span class="sxs-lookup"><span data-stu-id="5d6ef-105">Description</span></span>  
 <span data-ttu-id="5d6ef-106">이 정보 추적은 명명된 파이프 끝점에 연결할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ef-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="5d6ef-107">이 오류는 명명된 파이프 끝점을 찾을 수 없거나 사용 중인 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ef-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="5d6ef-108">연결되거나 OpenTimeout이 만료될 때까지 짧은 시간 단위로 구분된 추가 시도가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ef-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6ef-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d6ef-109">See Also</span></span>  
 [<span data-ttu-id="5d6ef-110">추적</span><span class="sxs-lookup"><span data-stu-id="5d6ef-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="5d6ef-111">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="5d6ef-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="5d6ef-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="5d6ef-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
