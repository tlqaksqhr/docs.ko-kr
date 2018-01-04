---
title: "방법: 채널 팩터리를 만들어 채널을 만들고 관리하는 데 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d41dfc85df1b706028fd95465596a980c040d512
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a><span data-ttu-id="a795f-102">방법: 채널 팩터리를 만들어 채널을 만들고 관리하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="a795f-102">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>
<span data-ttu-id="a795f-103"><xref:System.ServiceModel.DuplexChannelFactory%601> 클래스에서는 서비스 끝점에서 메시지를 받거나 보내기 위해 클라이언트에서 사용하는 여러 형식의 이중 채널을 만들고 관리하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a795f-103">The <xref:System.ServiceModel.DuplexChannelFactory%601> class provides the means to create and manage duplex channels of different types that clients use to send and receive messages to and from service endpoints.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a795f-104">예</span><span class="sxs-lookup"><span data-stu-id="a795f-104">Example</span></span>  
 <span data-ttu-id="a795f-105">다음 코드에서는 채널 팩터리를 만드는 방법과 이 채널 팩터리를 사용하여 채널을 만들고 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a795f-105">The following code shows how to create a channel factory and use it to create and manage channels.</span></span>  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a795f-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a795f-106">See Also</span></span>  
 <xref:System.ServiceModel.DuplexChannelFactory%601>
