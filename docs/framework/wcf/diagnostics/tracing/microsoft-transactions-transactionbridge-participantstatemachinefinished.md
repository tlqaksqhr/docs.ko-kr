---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 85b8cc4e5044cc7c87ea784e09c160cc527dddaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473534"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="1c216-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="1c216-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="1c216-103">참가자 인리스트먼트에 대한 상태 시스템이 완료 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c216-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c216-104">설명</span><span class="sxs-lookup"><span data-stu-id="1c216-104">Description</span></span>  
 <span data-ttu-id="1c216-105">하위 참여 인리스트먼트에서 2PC(2단계 커밋) 처리를 완료한 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c216-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="1c216-106">인리스트먼트 결과는 커밋됨 또는 중단됨입니다.</span><span class="sxs-lookup"><span data-stu-id="1c216-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="1c216-107">참가자가 준비 과정에서 ReadOnly를 선택하는 경우에도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c216-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c216-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c216-108">See Also</span></span>  
 [<span data-ttu-id="1c216-109">추적</span><span class="sxs-lookup"><span data-stu-id="1c216-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1c216-110">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1c216-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1c216-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="1c216-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
