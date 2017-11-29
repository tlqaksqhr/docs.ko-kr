---
title: "&#39; 사용자 지정 &#39; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords: BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 844bd033ea05e373b04a04f80777af77179c1263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="ea833-102">&#39; 사용자 지정 &#39; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea833-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="ea833-103">사용자 지정이 아닌 이벤트와 달리는 `Custom Event` 선언에 필요는 `As` 이벤트 이름 다음에 이벤트에 대 한 대리자 형식을 명시적으로 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="ea833-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="ea833-104">비-사용자 지정 이벤트 수 사용 하 여 정의할는 `As` 절과 명시적 대리자, 형식 또는 매개 변수가 즉시를 나열 이벤트 이름 다음에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea833-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="ea833-105">**오류 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="ea833-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea833-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ea833-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ea833-107">사용자 지정 이벤트로 동일한 매개 변수 목록 사용 하 여 대리자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea833-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="ea833-108">예를 들어 경우는 `Custom Event` 에 의해 정의 되었습니다 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, 있으면 해당 대리자 다음 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea833-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="ea833-109">매개 변수 목록으로 사용자 지정 이벤트 바꾸기는 `As` 절을 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea833-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="ea833-110">예제에 이어서 `Custom Event` 선언은 다음과 같이 작성 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea833-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="ea833-111">예제</span><span class="sxs-lookup"><span data-stu-id="ea833-111">Example</span></span>  
 <span data-ttu-id="ea833-112">이 예제에서는 선언는 `Custom Event` 필요한 지정 `As` 대리자 형식으로는 절.</span><span class="sxs-lookup"><span data-stu-id="ea833-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ea833-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea833-113">See Also</span></span>  
 [<span data-ttu-id="ea833-114">Event 문</span><span class="sxs-lookup"><span data-stu-id="ea833-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="ea833-115">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="ea833-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="ea833-116">이벤트</span><span class="sxs-lookup"><span data-stu-id="ea833-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
