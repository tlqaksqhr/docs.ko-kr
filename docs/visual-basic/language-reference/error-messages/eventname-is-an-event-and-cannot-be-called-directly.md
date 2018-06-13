---
title: '&#39;&lt;eventname&gt; &#39; 은 (는) 이벤트 이므로 직접 호출할 수 없습니다'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587334"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="51266-102">&#39;&lt;eventname&gt; &#39; 은 (는) 이벤트 이므로 직접 호출할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="51266-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="51266-103">' <`eventname`>'은 (는) 이벤트 및 이므로 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51266-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="51266-104">사용 하 여 한 `RaiseEvent` 이벤트를 발생 시키는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="51266-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="51266-105">프로시저 호출이 프로시저 이름에 대 한 이벤트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51266-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="51266-106">이벤트 처리기는 프로시저는 있지만 이벤트 자체는 발생 하 고 처리 해야 하는 신호 장치.</span><span class="sxs-lookup"><span data-stu-id="51266-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="51266-107">**오류 ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="51266-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51266-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="51266-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="51266-109">사용 하 여 한 `RaiseEvent` 문을 이벤트 신호를 보내고 처리 하는 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="51266-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51266-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51266-110">See Also</span></span>  
 [<span data-ttu-id="51266-111">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="51266-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
