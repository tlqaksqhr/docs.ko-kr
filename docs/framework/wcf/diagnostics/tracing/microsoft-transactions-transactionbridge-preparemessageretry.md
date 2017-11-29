---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b8199398e4e0bfe8ad42f6c8ba8adb11e883236e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="bff51-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="bff51-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="bff51-103">준비 메시지 재시도를 응답하지 않는 참가자에게 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="bff51-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bff51-104">설명</span><span class="sxs-lookup"><span data-stu-id="bff51-104">Description</span></span>  
 <span data-ttu-id="bff51-105">로컬 트랜잭션 관리자가 주어진 시간 내에 응답을 받지 못해서 준비 메시지를 하위 참가자에게 다시 전송해야 할 경우에 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff51-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bff51-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="bff51-106">Troubleshooting</span></span>  
 <span data-ttu-id="bff51-107">응답을 제시간에 전달하지 못하도록 하는 잠재적인 네트워크 문제 또는 제품 문제를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="bff51-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="bff51-108">이러한 메시지 중 대부분이 표시되면 이는 인프라 문제 또는 비정상적으로 긴 응답 시간을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff51-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="bff51-109">두 가지 문제 모두 시스템 내의 트랜잭션 처리량을 심각하게 감소시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bff51-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff51-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bff51-110">See Also</span></span>  
 [<span data-ttu-id="bff51-111">추적</span><span class="sxs-lookup"><span data-stu-id="bff51-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="bff51-112">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="bff51-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="bff51-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="bff51-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
