---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e72d3e400440b830b689f476753a7c8c40fe2586
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="msmq"></a><span data-ttu-id="0713f-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="0713f-102">MSMQ</span></span>
<span data-ttu-id="0713f-103">MSMQ 응용 프로그램에서는 대기 중인 채널에서 MSMQ로, 그리고 MSMQ에서 대기 중인 채널로 추가 동작이 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0713f-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="0713f-104">또한 보내기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0713f-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="0713f-105">받기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0713f-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="0713f-106">받기 작업에서 필요한 전송은 다른 모든 전송과 유사하게 실행됩니다(바이트 수신->메시지 처리-> 작업).</span><span class="sxs-lookup"><span data-stu-id="0713f-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
