---
title: 범위 변수 &lt;변수&gt; 바깥쪽 블록, 이전에 정의한 범위 변수 또는 쿼리 식에서 암시적으로 선언 된 변수에서 변수를 숨깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f02533cf7cb79c34e5bb5a6d445aaef7ab0e86da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593128"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="f4d72-102">범위 변수 &lt;변수&gt; 바깥쪽 블록, 이전에 정의한 범위 변수 또는 쿼리 식에서 암시적으로 선언 된 변수에서 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="f4d72-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="f4d72-103">에 지정 된 범위 변수 이름은 `Select`, `From`, `Aggregate`, 또는 `Let` 절에 이미 지정 된 이전에 쿼리 또는 쿼리를 암시적으로 선언 된 변수의 이름을 범위 변수 이름과 중복 예: 필드 이름 또는 집계 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d72-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="f4d72-104">**오류 ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="f4d72-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4d72-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f4d72-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f4d72-106">모든 범위 변수는 특정 쿼리 범위에 고유한 이름을 가졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d72-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="f4d72-107">쿼리는 중첩된 쿼리 있는 고유한 범위 괄호로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d72-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d72-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4d72-108">See Also</span></span>  
 [<span data-ttu-id="f4d72-109">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="f4d72-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="f4d72-110">From 절</span><span class="sxs-lookup"><span data-stu-id="f4d72-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="f4d72-111">Let 절</span><span class="sxs-lookup"><span data-stu-id="f4d72-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="f4d72-112">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="f4d72-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="f4d72-113">Select 절</span><span class="sxs-lookup"><span data-stu-id="f4d72-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
