---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2931eec5646b44eea19d70b11eb43c056b0ee0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="0349c-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="0349c-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="0349c-103">메시지의 인바운드 수신 속도가 너무 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="0349c-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0349c-104">설명</span><span class="sxs-lookup"><span data-stu-id="0349c-104">Description</span></span>  
 <span data-ttu-id="0349c-105">이 추적은 인바운드 메시지를 처리하려 할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0349c-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="0349c-106">인접 부분에 설정된 할당량을 초과했기 때문에 특정 인접 부분에 메시지를 전달하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0349c-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="0349c-107">이 문제는 응답하지 않는 인접 부분에서 보류 중인 메시지의 백로그를 지우지 못한 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0349c-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0349c-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="0349c-108">Troubleshooting</span></span>  
 <span data-ttu-id="0349c-109">메시 내에서 메시지를 보내는 속도를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0349c-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0349c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0349c-110">See Also</span></span>  
 [<span data-ttu-id="0349c-111">추적</span><span class="sxs-lookup"><span data-stu-id="0349c-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0349c-112">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="0349c-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0349c-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="0349c-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
