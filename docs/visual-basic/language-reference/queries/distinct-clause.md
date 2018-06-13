---
title: Distinct 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603979"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="0bc7d-102">Distinct 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bc7d-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="0bc7d-103">후속 쿼리 절에 중복 값을 제거 하 여 현재 범위 변수 값을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0bc7d-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="0bc7d-105">설명</span><span class="sxs-lookup"><span data-stu-id="0bc7d-105">Remarks</span></span>  
 <span data-ttu-id="0bc7d-106">사용할 수는 `Distinct` 절 고유 항목의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="0bc7d-107">`Distinct` 절로 인해 쿼리 중복 되는 쿼리 결과 무시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="0bc7d-108">`Distinct` 절이 모두 반환 하 여 지정 된 필드에 대 한 중복 값에 적용 된 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="0bc7d-109">하지 않으면 `Select` 절이 지정 된 `Distinct` 절에서 식별 된 쿼리의 범위 변수가 적용 됩니다는 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="0bc7d-110">범위 변수는 변경할 수 없는 형식 없는 경우 형식의 모든 멤버에는 기존 쿼리 결과 일치 하는 경우 쿼리가 쿼리 결과 무시만 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bc7d-111">예제</span><span class="sxs-lookup"><span data-stu-id="0bc7d-111">Example</span></span>  
 <span data-ttu-id="0bc7d-112">다음 쿼리 식은 고객 목록을 고객 주문 목록과 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="0bc7d-113">`Distinct` 절이 고유한 고객 이름 목록을 반환 하 고 주문 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc7d-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0bc7d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bc7d-114">See Also</span></span>  
 [<span data-ttu-id="0bc7d-115">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="0bc7d-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="0bc7d-116">쿼리</span><span class="sxs-lookup"><span data-stu-id="0bc7d-116">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="0bc7d-117">From 절</span><span class="sxs-lookup"><span data-stu-id="0bc7d-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="0bc7d-118">Select 절</span><span class="sxs-lookup"><span data-stu-id="0bc7d-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="0bc7d-119">Where 절</span><span class="sxs-lookup"><span data-stu-id="0bc7d-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
