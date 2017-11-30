---
title: "속성 &#39; &lt;propertyname&gt;&#39; 대상이 &#39; t 일부 코드 경로에 값을 반환 합니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords: BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="d703b-102">속성 &#39; &lt;propertyname&gt;&#39; 대상이 &#39; t 일부 코드 경로에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="d703b-103">속성 '\<propertyname >' 모든 코드 경로 대해서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d703b-104">이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="d703b-105">속성 `Get` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d703b-106">속성에서 값을 반환할 수 `Get` 절차는 다음과 같은 방법 중 하나:</span><span class="sxs-lookup"><span data-stu-id="d703b-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="d703b-107">속성 이름에 값을 할당 한 후 수행 된 `Exit Property` 문.</span><span class="sxs-lookup"><span data-stu-id="d703b-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="d703b-108">속성 이름에 값을 할당 한 후 수행 된 `End Get` 문.</span><span class="sxs-lookup"><span data-stu-id="d703b-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="d703b-109">에 대 한 값이 포함 된 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="d703b-110">컨트롤을 전달 하는 경우 `Exit Property` 또는 `End Get` 속성 이름에 값을 할당 하지 않은 하 고는 `Get` 프로시저가 속성의 데이터 형식의 기본 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="d703b-111">자세한 내용은의 "동작" 참조 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d703b-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-112">By default, this message is a warning.</span></span> <span data-ttu-id="d703b-113">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d703b-114">**오류 ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="d703b-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d703b-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d703b-115">To correct this error</span></span>  
  
-   <span data-ttu-id="d703b-116">제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d703b-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d703b-117">항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="d703b-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d703b-118">이렇게 하면, 앞의 마지막 문이 `End Get` 이어야 합니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="d703b-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d703b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d703b-119">See Also</span></span>  
 [<span data-ttu-id="d703b-120">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="d703b-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="d703b-121">Property 문</span><span class="sxs-lookup"><span data-stu-id="d703b-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="d703b-122">Get 문</span><span class="sxs-lookup"><span data-stu-id="d703b-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
