---
title: 부울 연산자(F#)
description: 'F # 프로그래밍 언어에서 사용할 수 있는 부울 연산자에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563430"
---
# <a name="boolean-operators"></a><span data-ttu-id="d4c2d-103">부울 연산자</span><span class="sxs-lookup"><span data-stu-id="d4c2d-103">Boolean Operators</span></span>

<span data-ttu-id="d4c2d-104">이 항목에는 F # 언어의 부울 연산자에 대 한 지원을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4c2d-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="d4c2d-105">부울 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="d4c2d-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="d4c2d-106">다음 표에 F # 언어에서 사용할 수 있는 부울 연산자 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4c2d-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="d4c2d-107">이러한 연산자에서 지원 되는 유일한 유형은 `bool` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d4c2d-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="d4c2d-108">연산자</span><span class="sxs-lookup"><span data-stu-id="d4c2d-108">Operator</span></span>|<span data-ttu-id="d4c2d-109">설명</span><span class="sxs-lookup"><span data-stu-id="d4c2d-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="d4c2d-110">부울 부정</span><span class="sxs-lookup"><span data-stu-id="d4c2d-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="d4c2d-111">부울 OR</span><span class="sxs-lookup"><span data-stu-id="d4c2d-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="d4c2d-112">부울 AND</span><span class="sxs-lookup"><span data-stu-id="d4c2d-112">Boolean AND</span></span>|

<span data-ttu-id="d4c2d-113">AND와 OR 부울 연산자 수행 *(short-circuit)*, 식의 전체 결과 확인 하는 데 필요한 경우에 연산자의 오른쪽에 있는 식 평가, 즉 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4c2d-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="d4c2d-114">두 번째 식의 `&&` 연산자는 첫 번째 식으로 계산 하는 경우에 계산 됩니다 `true`;의 두 번째 식의 `||` 연산자는 첫 번째 식으로 계산 하는 경우에 계산 됩니다 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4c2d-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c2d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4c2d-115">See Also</span></span>
[<span data-ttu-id="d4c2d-116">비트 연산자</span><span class="sxs-lookup"><span data-stu-id="d4c2d-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="d4c2d-117">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="d4c2d-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="d4c2d-118">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="d4c2d-118">Symbol and Operator Reference</span></span>](index.md)
