---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3595b98ca8c78fb6bdf86a08dcd56b37a4770405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="6bdb0-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6bdb0-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="6bdb0-103">비동기 중단으로 인해 지정된 작업에 대한 지정된 트랜잭션이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb0-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6bdb0-104">설명</span><span class="sxs-lookup"><span data-stu-id="6bdb0-104">Description</span></span>  
 <span data-ttu-id="6bdb0-105">다른 참가자가 중단을 응답하거나, 시간 초과가 발생하거나, 트랜잭션 참가자 내부에서 다른 오류가 발생하여 현재 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb0-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6bdb0-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="6bdb0-106">Troubleshooting</span></span>  
 <span data-ttu-id="6bdb0-107">이 중단이 예기치 않은 동작인 경우 모든 시스템 로그에서 실제 중단 이유를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb0-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdb0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bdb0-108">See Also</span></span>  
 [<span data-ttu-id="6bdb0-109">추적</span><span class="sxs-lookup"><span data-stu-id="6bdb0-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6bdb0-110">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="6bdb0-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6bdb0-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="6bdb0-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
