---
title: AddHandler 문
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: bc0dce442db9d62b9fbee857b6e711696ad87fb8
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936817"
---
# <a name="addhandler-statement"></a><span data-ttu-id="a6ba8-102">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="a6ba8-102">AddHandler Statement</span></span>
<span data-ttu-id="a6ba8-103">런타임에 이벤트 처리기를 사용 하 여 이벤트를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ba8-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6ba8-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a6ba8-105">요소</span><span class="sxs-lookup"><span data-stu-id="a6ba8-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="a6ba8-106">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="a6ba8-106">event</span></span>|<span data-ttu-id="a6ba8-107">처리할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="a6ba8-108">이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a6ba8-109">설명</span><span class="sxs-lookup"><span data-stu-id="a6ba8-109">Remarks</span></span>  
 <span data-ttu-id="a6ba8-110">합니다 `AddHandler` 고 `RemoveHandler` 문을 시작 하 고 프로그램 실행 중 언제 든 지 이벤트 처리를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a6ba8-111">서명의 합니다 `eventhandler` 프로시저는 이벤트의 시그니처와 일치 해야 `event`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a6ba8-112">`Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a6ba8-113">`AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a6ba8-114">특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a6ba8-115">자세한 내용은 [처리](../../../visual-basic/language-reference/statements/handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6ba8-116">사용자 지정 이벤트에 대 한 합니다 `AddHandler` 문은 호출 이벤트의 `AddHandler` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a6ba8-117">사용자 지정 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트 연결 문으로](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ba8-118">예</span><span class="sxs-lookup"><span data-stu-id="a6ba8-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a6ba8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6ba8-119">See Also</span></span>  
 [<span data-ttu-id="a6ba8-120">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="a6ba8-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="a6ba8-121">Handles</span><span class="sxs-lookup"><span data-stu-id="a6ba8-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="a6ba8-122">Event 문</span><span class="sxs-lookup"><span data-stu-id="a6ba8-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="a6ba8-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="a6ba8-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
