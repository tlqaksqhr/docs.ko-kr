---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fe88e70ab4955305d78baa1158cd73a93ba2ed2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476322"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="0e4bc-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="0e4bc-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="0e4bc-103">WS-AT 프로토콜 서비스가 Prepare 메시지에 응답하지 않은 영속 참가자로부터 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4bc-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="0e4bc-104">따라서 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4bc-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e4bc-105">설명</span><span class="sxs-lookup"><span data-stu-id="0e4bc-105">Description</span></span>  
 <span data-ttu-id="0e4bc-106">영속 참가자가 준비하는 동안 Reply 메시지를 받을 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4bc-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="0e4bc-107">이 상태에 대한 잘못된 메시지로 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4bc-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0e4bc-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="0e4bc-108">Troubleshooting</span></span>  
 <span data-ttu-id="0e4bc-109">이 오류를 받는다면, Subordinate TransactionManager 등 영속 참가자가 오류를 복구했지만 트랜잭션 결과가 불확실함을 나타낼 수 있어 상태를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4bc-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4bc-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e4bc-110">See Also</span></span>  
 [<span data-ttu-id="0e4bc-111">추적</span><span class="sxs-lookup"><span data-stu-id="0e4bc-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0e4bc-112">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0e4bc-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0e4bc-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="0e4bc-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
