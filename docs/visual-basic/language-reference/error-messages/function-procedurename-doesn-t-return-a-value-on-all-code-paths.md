---
title: 함수 &#39; &lt;procedurename&gt;&#39; 대상이 &#39; t 일부 코드 경로에 값을 반환 합니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="24a25-102">함수 &#39; &lt;procedurename&gt;&#39; 대상이 &#39; t 일부 코드 경로에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="24a25-103">함수 '\<procedurename >' 모든 코드 경로 대해서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="24a25-104">'Return' 문은 없습니다?</span><span class="sxs-lookup"><span data-stu-id="24a25-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="24a25-105">A `Function` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="24a25-106">값을 반환할 수는 `Function` 절차는 다음과 같은 방법 중 하나:</span><span class="sxs-lookup"><span data-stu-id="24a25-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="24a25-107">에 대 한 값이 포함 된 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="24a25-108">값을 할당는 `Function` 프로시저 이름을 지정 하 고 다음을 수행할는 `Exit Function` 문.</span><span class="sxs-lookup"><span data-stu-id="24a25-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="24a25-109">값을 할당는 `Function` 프로시저 이름을 지정 하 고 다음을 수행할는 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="24a25-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="24a25-110">컨트롤을 전달 하는 경우 `Exit Function` 또는 `End Function` 및 프로시저 이름에 값을 할당 하지 않은, 프로시저가 반환 데이터 형식의 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="24a25-111">자세한 내용은의 "동작" 참조 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="24a25-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-112">By default, this message is a warning.</span></span> <span data-ttu-id="24a25-113">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="24a25-114">**오류 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="24a25-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24a25-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="24a25-115">To correct this error</span></span>  
  
-   <span data-ttu-id="24a25-116">제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a25-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="24a25-117">항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="24a25-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="24a25-118">이렇게 하면, 앞의 마지막 문이 `End Function` 이어야 합니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="24a25-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a25-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24a25-119">See Also</span></span>  
 [<span data-ttu-id="24a25-120">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="24a25-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="24a25-121">Function 문</span><span class="sxs-lookup"><span data-stu-id="24a25-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="24a25-122">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24a25-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
