---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: fb5e50e7332269690a200334ef936dd0d5525e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475116"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="6c753-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="6c753-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="6c753-103">WS-AT 프로토콜 서비스가 제어 프로토콜에 대한 참가자를 등록하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6c753-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6c753-104">설명</span><span class="sxs-lookup"><span data-stu-id="6c753-104">Description</span></span>  
 <span data-ttu-id="6c753-105">MSDTC가 잘못된 등록 요청을 감지하는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c753-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="6c753-106">이는 여러 완료 등록 요청 및 내부 오류에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c753-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6c753-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="6c753-107">Troubleshooting</span></span>  
 <span data-ttu-id="6c753-108">완료를 두 번 이상 등록하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6c753-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="6c753-109">또한 추적 메시지 내의 상태 문자열을 검사하여 실행 가능한 항목이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c753-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c753-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c753-110">See Also</span></span>  
 [<span data-ttu-id="6c753-111">추적</span><span class="sxs-lookup"><span data-stu-id="6c753-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6c753-112">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6c753-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6c753-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="6c753-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
