---
title: WF의 오류 처리 활동
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 51431e367f0ec8874588a52cb4dbd76d714768fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512387"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="b29bd-102">WF의 오류 처리 활동</span><span class="sxs-lookup"><span data-stu-id="b29bd-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="b29bd-103">에서는 오류 처리 및 복구를 구현하기 위해 여러 시스템 제공 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b29bd-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="b29bd-104">자세한 내용은 참조 [예외](../../../docs/framework/windows-workflow-foundation/exceptions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29bd-104">For more information, see [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="b29bd-105">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="b29bd-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="b29bd-106">`TryCatch` 활동에서 throw된 마지막 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b29bd-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="b29bd-107">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b29bd-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="b29bd-108">예외 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b29bd-108">Implements exception handling.</span></span>|
