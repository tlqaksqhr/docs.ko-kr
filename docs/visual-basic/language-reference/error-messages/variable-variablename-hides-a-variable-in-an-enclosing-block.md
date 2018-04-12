---
title: 변수 &#39; &lt;variablename&gt;&#39; 바깥쪽 블록의 변수를 숨깁니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="fd460-102">변수 &#39; &lt;variablename&gt;&#39; 바깥쪽 블록의 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="fd460-103">블록에 포함 된 변수의 동일한 이름으로 다른 지역 변수에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="fd460-104">**오류 ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="fd460-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd460-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fd460-105">To correct this error</span></span>  
  
-   <span data-ttu-id="fd460-106">블록 내부에서 변수를 이름을 다른 지역 변수와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="fd460-107">예:</span><span class="sxs-lookup"><span data-stu-id="fd460-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="fd460-108">이 오류에 대 한 일반적인 원인의 사용입니다 `Catch e As Exception` 이벤트 처리기 내 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="fd460-109">이 경우 이름을 `Catch` 블록 변수가 `ex` 대신 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="fd460-110">이 오류가 발생 하는 또 다른 일반적인 소스 내에서 선언 된 지역 변수에 액세스 하려고 하는 한 `Try` 별개의 차단 `Catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="fd460-111">이 문제를 해결 하려면 외부 변수를 선언에서 `Try...Catch...Finally` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="fd460-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd460-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd460-112">See Also</span></span>  
 [<span data-ttu-id="fd460-113">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="fd460-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="fd460-114">변수 선언</span><span class="sxs-lookup"><span data-stu-id="fd460-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
