---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1bbad8d743ff64aea923e7fbf62871e495253aea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="37703-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="37703-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="37703-103">HTTP 채널을 통해 메시지를 받지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="37703-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="37703-104">설명</span><span class="sxs-lookup"><span data-stu-id="37703-104">Description</span></span>  
 <span data-ttu-id="37703-105">이 추적은 경고 또는 오류로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37703-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="37703-106">두 가지 경우 모두, 들어오는 HTTP 요청에 대해 호환되는 수신기가 없고 HTTP 요청이 삭제되는 경우 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="37703-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="37703-107">이 동작은 요청의 HTTP 동사를 HTTP 수신기가 인식하지 않거나 수신기가 요청 대상 주소에서 수신 대기하지 않기 때문에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37703-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="37703-108">추적은 자체 호스팅 환경에서는 경고로 내보내지고 서비스가 IIS에서 호스팅되는 경우에는 오류로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="37703-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37703-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37703-109">See Also</span></span>  
 [<span data-ttu-id="37703-110">추적</span><span class="sxs-lookup"><span data-stu-id="37703-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="37703-111">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="37703-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="37703-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="37703-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
