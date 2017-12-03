---
title: "채널 확장성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcda7f9edc741e8f0c9c56214119255ca2777d77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="c4c13-102">채널 확장성</span><span class="sxs-lookup"><span data-stu-id="c4c13-102">Channels Extensibility</span></span>
<span data-ttu-id="c4c13-103">이 단원에는 사용자 지정 채널을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4c13-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c4c13-104">In This Section</span></span>  
 [<span data-ttu-id="c4c13-105">로컬 채널</span><span class="sxs-lookup"><span data-stu-id="c4c13-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="c4c13-106">동일한 응용 프로그램 도메인 내에서 통신하는 데 사용되는 로컬 채널인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 전송 채널을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="c4c13-107">신뢰할 수 있는 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="c4c13-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="c4c13-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 RSP(Reliable Secure Profile)를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="c4c13-109">사용자 지정 채널 디스패처</span><span class="sxs-lookup"><span data-stu-id="c4c13-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="c4c13-110"><xref:System.ServiceModel.ServiceHostBase>를 직접 구현하여 사용자 지정 방식으로 채널 스택을 빌드하는 방법과 웹 호스트 환경에서 사용자 지정 채널 디스패처를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="c4c13-111">청크 채널</span><span class="sxs-lookup"><span data-stu-id="c4c13-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="c4c13-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 전송된 큰 메시지를 버퍼링하는 데 사용되는 메모리 양을 제한하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="c4c13-113">HTTP 승인 채널</span><span class="sxs-lookup"><span data-stu-id="c4c13-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="c4c13-114">단방향 메시징 패턴을 변경하는 계층화된 채널을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="c4c13-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="c4c13-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="c4c13-116">사용자 지정 프로토콜 채널을 빌드하여 세션 관리에 HTTP 쿠키를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="c4c13-117">사용자 지정 메시지 인터셉터</span><span class="sxs-lookup"><span data-stu-id="c4c13-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="c4c13-118">런타임 스택의 특정 지점에서 들어오고 나가는 모든 메시지를 가로채기 위해 채널 팩터리 및 채널 수신기를 만드는 사용자 지정 바인딩 요소의 구현 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4c13-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
