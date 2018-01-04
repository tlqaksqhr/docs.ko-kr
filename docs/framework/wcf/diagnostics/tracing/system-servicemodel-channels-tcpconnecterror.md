---
title: System.ServiceModel.Channels.TcpConnectError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22d93797-072e-405d-a3e0-5c519ddf290b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 758147d91a49fe248ba0ead1ff2c339e30e6dfe0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelstcpconnecterror"></a><span data-ttu-id="08a32-102">System.ServiceModel.Channels.TcpConnectError</span><span class="sxs-lookup"><span data-stu-id="08a32-102">System.ServiceModel.Channels.TcpConnectError</span></span>
<span data-ttu-id="08a32-103">TCP 연결 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08a32-103">The TCP connect operation failed.</span></span>  
  
## <a name="description"></a><span data-ttu-id="08a32-104">설명</span><span class="sxs-lookup"><span data-stu-id="08a32-104">Description</span></span>  
 <span data-ttu-id="08a32-105">이 경고 수준 추적은 TCP 끝점에 연결하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08a32-105">This warning level trace indicates a failure to connect to a TCP endpoint.</span></span> <span data-ttu-id="08a32-106">이 오류는 원격 끝점이 지정된 IP 주소 및 포트에서 응답하지 않는 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08a32-106">This could happen if the remote endpoint is not responding at a given IP address and port.</span></span> <span data-ttu-id="08a32-107">이후에 다른 유효한 IP 주소(예를 들어 IPv4 또는 IPv6 주소 또는 지정된 호스트 이름을 나타내는 다른 IP 주소)에 대한 연결을 시도하여 성공한 경우 이 추적은 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08a32-107">This trace can be ignored if subsequent attempts to connect to other valid IP addresses (such as IPv4 or IPv6 addresses, or other IP addresses representing a given hostname) succeed.</span></span> <span data-ttu-id="08a32-108">이 추적 내의 예외는 오류에 대한 추가 정보를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08a32-108">The exception within this trace can reveal additional information about the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a32-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08a32-109">See Also</span></span>  
 [<span data-ttu-id="08a32-110">추적</span><span class="sxs-lookup"><span data-stu-id="08a32-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="08a32-111">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="08a32-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="08a32-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="08a32-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
