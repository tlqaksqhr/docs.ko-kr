---
title: "&quot;Custom&quot; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 449e5a690f06ce35d1ccc799daf5f2c1ad1c6dac
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="4c53b-102">'Custom' 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c53b-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="4c53b-103">사용자 지정이 아닌 이벤트와 달리는 `Custom Event` 선언 필요는 `As` 이벤트 이름 다음에 이벤트에 대 한 대리자 형식을 명시적으로 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="4c53b-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="4c53b-104">비-사용자 지정 이벤트 수 사용 하 여 정의할는 `As` 절과 명시적 대리자 형식, 또는 매개 변수와 함께 나열 즉시 이벤트 이름 다음에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c53b-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="4c53b-105">**오류 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="4c53b-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c53b-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4c53b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="4c53b-107">사용자 지정 이벤트와 동일한 매개 변수 목록 사용 하 여 대리자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c53b-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="4c53b-108">예를 들어 하는 경우는 `Custom Event` 정의한 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, 해당 대리자에는 다음 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c53b-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     <span data-ttu-id="4c53b-109">[!code-vb[VbVbalrEventError #&18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c53b-109">[!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span></span>  
  
2.  <span data-ttu-id="4c53b-110">매개 변수 목록을 사용 하 여 사용자 지정 이벤트의 대체는 `As` 절을 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c53b-110">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="4c53b-111">예를 들어 계속 `Custom Event` 선언을 다음과 같이 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c53b-111">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     <span data-ttu-id="4c53b-112">[!code-vb[VbVbalrEventError #&19;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c53b-112">[!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c53b-113">예제</span><span class="sxs-lookup"><span data-stu-id="4c53b-113">Example</span></span>  
 <span data-ttu-id="4c53b-114">이 예제에서는 선언는 `Custom Event` 필수 지정 `As` 대리자 형식으로 절.</span><span class="sxs-lookup"><span data-stu-id="4c53b-114">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 <span data-ttu-id="4c53b-115">[!code-vb[VbVbalrEventError #&2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4c53b-115">[!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c53b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c53b-116">See Also</span></span>  
 <span data-ttu-id="4c53b-117">[Event 문](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4c53b-117">[Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="4c53b-118"> [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4c53b-118"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="4c53b-119"> [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="4c53b-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
