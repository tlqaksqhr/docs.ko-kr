---
title: "함수 &quot;&lt;procedurename&gt;&quot; 모든 코드 경로에서 값을 반환 하지 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
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
ms.openlocfilehash: cec047644bfbf82c5c3c206b23af6b0fc37f834d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="f33d9-102">함수 '&lt;procedurename&gt;' 모든 코드 경로 대해서만 값을 반환</span><span class="sxs-lookup"><span data-stu-id="f33d9-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="f33d9-103">함수 '\<procedurename > ' 모든 코드 경로 대해서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="f33d9-104">'에 Return' 문이 없습니다?</span><span class="sxs-lookup"><span data-stu-id="f33d9-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="f33d9-105">A `Function` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="f33d9-106">값을 반환할 수는 `Function` 절차는 다음 방법 중 하나:</span><span class="sxs-lookup"><span data-stu-id="f33d9-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="f33d9-107">값을 포함 한 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="f33d9-108">에 값을 할당은 `Function` 프로시저 이름을 지정 하 고 다음을 수행는 `Exit Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="f33d9-109">에 값을 할당은 `Function` 프로시저 이름을 지정 하 고 다음을 수행는 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="f33d9-110">컨트롤을 전달 하는 경우 `Exit Function` 또는 `End Function` 및 프로시저 이름에 값을 할당 하지 않은, 프로시저의 반환 데이터 형식이 기본 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="f33d9-111">자세한 내용은 "동작"의 참조 [Function 문의](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="f33d9-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-112">By default, this message is a warning.</span></span> <span data-ttu-id="f33d9-113">경고를 숨기 거 나 경고를 오류로 처리에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f33d9-114">**오류 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="f33d9-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f33d9-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f33d9-115">To correct this error</span></span>  
  
-   <span data-ttu-id="f33d9-116">제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="f33d9-117">항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="f33d9-118">이렇게 하면, 앞의 마지막 문이 `End Function` 있어야는 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f33d9-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f33d9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f33d9-119">See Also</span></span>  
 <span data-ttu-id="f33d9-120">[Function 프로시저](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f33d9-120">[Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="f33d9-121"> [Function 문](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f33d9-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="f33d9-122"> [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f33d9-122"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
