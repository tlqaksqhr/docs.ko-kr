---
title: "WCF 및 웹 소켓"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 225bff20f514a653382f01becf133659dec4c5f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="80d98-102">WCF 및 웹 소켓</span><span class="sxs-lookup"><span data-stu-id="80d98-102">WCF and WebSockets</span></span>
<span data-ttu-id="80d98-103">.NET Framework 4.5부터 Windows Communication Foundation에서 WebSocket을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="80d98-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="80d98-104">WebSocket은 표준 HTTP 포트 80 및 443에서 양방향 통신을 가능하게 하는 효율적 표준 기반 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="80d98-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="80d98-105">표준 HTTP 포트를 사용하면 WebSocket이 매개자를 통해 웹에서 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80d98-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="80d98-106">WebSocket 전송에서 통신을 지원하기 위해</span><span class="sxs-lookup"><span data-stu-id="80d98-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="80d98-107"><xref:System.ServiceModel.NetHttpBinding>와 <xref:System.ServiceModel.NetHttpsBinding>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80d98-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="80d98-108">Websocket 관련 설정은 구성할 수 있습니다는 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 에 액세스 하 여는 <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80d98-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="80d98-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="80d98-109">In This Section</span></span>  
 [<span data-ttu-id="80d98-110">NetHttpBinding 사용</span><span class="sxs-lookup"><span data-stu-id="80d98-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="80d98-111"><xref:System.ServiceModel.NetHttpBinding> 및 해당 구성 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80d98-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="80d98-112">방법: Websocket을 통해 통신 하는 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="80d98-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="80d98-113">WebSocket을 통해 통신하는 WCF 서비스를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80d98-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="80d98-114">참조</span><span class="sxs-lookup"><span data-stu-id="80d98-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="80d98-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="80d98-115">Related Sections</span></span>
