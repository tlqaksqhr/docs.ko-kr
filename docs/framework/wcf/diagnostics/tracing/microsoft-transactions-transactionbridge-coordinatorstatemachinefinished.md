---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: abb6a81d22da3a35c754c5d1485c5d612c9cd1e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473135"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="8df27-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="8df27-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="8df27-103">코디네이터 인리스트먼트를 위한 상태 시스템이 완료 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8df27-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8df27-104">설명</span><span class="sxs-lookup"><span data-stu-id="8df27-104">Description</span></span>  
 <span data-ttu-id="8df27-105">로컬 트랜잭션 관리자가 상위 코디네이터 인리스트먼트에서 2PC(2단계 커밋) 처리를 완료한 것으로 간주할 때 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df27-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="8df27-106">인리스트먼트 결과는 커밋됨 또는 중단됨 또는 잊어버림입니다.</span><span class="sxs-lookup"><span data-stu-id="8df27-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="8df27-107">로컬 트랜잭션 관리자가 준비 과정에서 ReadOnly를 선택하는 경우에도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df27-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df27-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8df27-108">See Also</span></span>  
 [<span data-ttu-id="8df27-109">추적</span><span class="sxs-lookup"><span data-stu-id="8df27-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8df27-110">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8df27-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8df27-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="8df27-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
