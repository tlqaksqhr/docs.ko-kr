---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28924f04dc83387f49c2369c2598c028f9b8d4bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="b0ebd-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b0ebd-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="b0ebd-103">포이즌 메시지가 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b0ebd-104">설명</span><span class="sxs-lookup"><span data-stu-id="b0ebd-104">Description</span></span>  
 <span data-ttu-id="b0ebd-105">이 추적은 포이즌 메시지가 발생되어 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="b0ebd-106">이는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="b0ebd-107">거부 된 메시지가 보낸 사람의에 다시 배달 [배달 못 한 편지 큐](http://go.microsoft.com/fwlink/?LinkId=99544)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="b0ebd-108">참조 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkId=99546) 경우 메시지가 포이즌이 되 고 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="b0ebd-109">참조 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) MSMQ의 의미는 거부 된 메시지에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ebd-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0ebd-110">See Also</span></span>  
 [<span data-ttu-id="b0ebd-111">추적</span><span class="sxs-lookup"><span data-stu-id="b0ebd-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b0ebd-112">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b0ebd-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b0ebd-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="b0ebd-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="b0ebd-114">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="b0ebd-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="b0ebd-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b0ebd-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
