---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4cecacdcc9ec1155fbb374bb763f6858da6ccc57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="69b81-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="69b81-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="69b81-103">메시지를 이동하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69b81-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="69b81-104">설명</span><span class="sxs-lookup"><span data-stu-id="69b81-104">Description</span></span>  
 <span data-ttu-id="69b81-105">이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69b81-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="69b81-106">NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용하는 경우 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 MSMQ 메시지를 사용합니다. 이 추적은 NetMsmqBinding 또는 MsmqIntegrationBinding의 선택한 `ReceiveErrorHandling` 속성 값과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="69b81-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="69b81-107">이 추적은 전체 시스템 오류를 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69b81-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="69b81-108">그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69b81-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="69b81-109">참조 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546) 경우 메시지가 포이즌이 되 고 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b81-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b81-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69b81-110">See Also</span></span>  
 [<span data-ttu-id="69b81-111">추적</span><span class="sxs-lookup"><span data-stu-id="69b81-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="69b81-112">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="69b81-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="69b81-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="69b81-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
