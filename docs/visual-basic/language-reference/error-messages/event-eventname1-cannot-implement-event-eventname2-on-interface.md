---
title: 이벤트 &#39; &lt;행사 이름 1&gt;&#39; 이벤트 &#39; 구현할 수 없습니다.&lt; eventname2&gt;&#39; 인터페이스 &#39;에&lt; 인터페이스&gt;&#39; 대리자 형식 &#39;&lt; delegate1&gt;&#39; 및 &#39;&lt; delegate2&gt;&#39; 일치 하지 않습니다
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0fcbbf8a6e23270e4dcbf9d813c773e1522a92a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="0a0f7-102">이벤트 &#39; &lt;행사 이름 1&gt;&#39; 이벤트 &#39; 구현할 수 없습니다.&lt; eventname2&gt;&#39; 인터페이스 &#39;에&lt; 인터페이스&gt;&#39; 대리자 형식 &#39;&lt; delegate1&gt;&#39; 및 &#39;&lt; delegate2&gt;&#39; 일치 하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="0a0f7-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="0a0f7-103">이벤트의 대리자 형식과 인터페이스에서 이벤트의 대리자 형식과 일치 하지 않는 이벤트를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-103"> cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="0a0f7-104">이 오류는 인터페이스에서 여러 이벤트를 정의한 다음 동일한 이벤트로 함께 구현하려고 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="0a0f7-105">구현된 모든 이벤트가 `As` 구문을 사용하여 선언되고 동일한 대리자 형식을 지정하는 경우에만 이벤트에서 둘 이상의 이벤트를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="0a0f7-106">**오류 ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="0a0f7-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0a0f7-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0a0f7-107">To correct this error</span></span>  
  
-   <span data-ttu-id="0a0f7-108">이벤트를 개별적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="0a0f7-109">또는</span><span class="sxs-lookup"><span data-stu-id="0a0f7-109">—or—</span></span>  
  
-   <span data-ttu-id="0a0f7-110">사용 하는 인터페이스의 이벤트를 정의 고 `As` 구문 동일한 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0f7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a0f7-111">See Also</span></span>  
 [<span data-ttu-id="0a0f7-112">Event 문</span><span class="sxs-lookup"><span data-stu-id="0a0f7-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="0a0f7-113">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="0a0f7-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="0a0f7-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="0a0f7-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
