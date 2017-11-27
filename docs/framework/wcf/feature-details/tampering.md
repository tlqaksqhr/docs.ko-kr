---
title: "변조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8852c4d19c48af2beee598f4ddfae7b775a025f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="tampering"></a><span data-ttu-id="952a6-102">변조</span><span class="sxs-lookup"><span data-stu-id="952a6-102">Tampering</span></span>
<span data-ttu-id="952a6-103">*변조* 은 변경, 메시지 또는 메시지를 배달 하 고 메시지 변경된 의도 된 것 이외의 용도로 사용 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="952a6-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="952a6-104">WS-Addressing 활성화</span><span class="sxs-lookup"><span data-stu-id="952a6-104">Do Not Disable WS-Addressing</span></span>  
 <span data-ttu-id="952a6-105">WS-Addressing 사양은 각 메시지에 대한 주소 헤더를 제공하여 메시지 받는 사람이 메시지를 보낸 사람을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a6-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="952a6-106"><xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 속성을 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>으로 설정하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a6-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="952a6-107">보안 모드를 메시지로 설정하는 경우 WS-Addressing을 사용하지 않도록 설정하면 공격자가 클라이언트에서 요청을 가져와 다른 서비스에 보낼 수 있으며 두 번째 서비스는 메시지가 원래 클라이언트에서 전송되었는지를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="952a6-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="952a6-108">실제로 첫 번째 서비스는 두 번째 서비스와 통신할 때 클라이언트인 것처럼 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a6-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="952a6-109">이러한 문제를 줄이려면 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 속성을 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>으로 설정하지 않고 <xref:System.ServiceModel.Channels.MessageVersion> 속성을 <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>로 설정하는 정적 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 속성과 같이 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="952a6-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952a6-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="952a6-110">See Also</span></span>  
 [<span data-ttu-id="952a6-111">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="952a6-111">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="952a6-112">정보 공개 문제점</span><span class="sxs-lookup"><span data-stu-id="952a6-112">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [<span data-ttu-id="952a6-113">권한 상승 문제점</span><span class="sxs-lookup"><span data-stu-id="952a6-113">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [<span data-ttu-id="952a6-114">서비스 거부</span><span class="sxs-lookup"><span data-stu-id="952a6-114">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [<span data-ttu-id="952a6-115">지원 되지 않는 시나리오</span><span class="sxs-lookup"><span data-stu-id="952a6-115">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [<span data-ttu-id="952a6-116">재생 공격</span><span class="sxs-lookup"><span data-stu-id="952a6-116">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
