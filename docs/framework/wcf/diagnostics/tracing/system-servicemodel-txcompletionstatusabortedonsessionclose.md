---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 695ebb2089147093601f2d51f11f11ca45861590
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="0549c-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="0549c-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="0549c-103">세션을 닫고 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute가 false로 설정되었을 때 지정된 트랜잭션이 완료되지 않았기 때문에 해당 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0549c-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0549c-104">설명</span><span class="sxs-lookup"><span data-stu-id="0549c-104">Description</span></span>  
 <span data-ttu-id="0549c-105">현재 활성 세션을 닫고 트랜잭션이 완료되지 않았으며 TransactionAutoCompleteOnSessionClose가 `false`로 설정된 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0549c-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0549c-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="0549c-106">Troubleshooting</span></span>  
 <span data-ttu-id="0549c-107">이 추적은 조사해야 하는 발생 가능한 응용 프로그램 버그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0549c-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0549c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0549c-108">See Also</span></span>  
 [<span data-ttu-id="0549c-109">추적</span><span class="sxs-lookup"><span data-stu-id="0549c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0549c-110">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="0549c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0549c-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="0549c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
