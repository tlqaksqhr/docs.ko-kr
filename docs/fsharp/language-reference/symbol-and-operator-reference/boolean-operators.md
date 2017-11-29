---
title: "부울 연산자(F#)"
description: "F # 프로그래밍 언어에서 사용할 수 있는 부울 연산자에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a><span data-ttu-id="31470-104">부울 연산자</span><span class="sxs-lookup"><span data-stu-id="31470-104">Boolean Operators</span></span>

<span data-ttu-id="31470-105">이 항목에는 F # 언어의 부울 연산자에 대 한 지원을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31470-105">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="31470-106">부울 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="31470-106">Summary of Boolean Operators</span></span>
<span data-ttu-id="31470-107">다음 표에 F # 언어에서 사용할 수 있는 부울 연산자 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31470-107">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="31470-108">이러한 연산자에서 지원 되는 유일한 유형은 `bool` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="31470-108">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="31470-109">연산자</span><span class="sxs-lookup"><span data-stu-id="31470-109">Operator</span></span>|<span data-ttu-id="31470-110">설명</span><span class="sxs-lookup"><span data-stu-id="31470-110">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="31470-111">부울 부정</span><span class="sxs-lookup"><span data-stu-id="31470-111">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="31470-112">부울 OR</span><span class="sxs-lookup"><span data-stu-id="31470-112">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="31470-113">부울 AND</span><span class="sxs-lookup"><span data-stu-id="31470-113">Boolean AND</span></span>|

<span data-ttu-id="31470-114">AND와 OR 부울 연산자 수행 *(short-circuit)*, 식의 전체 결과 확인 하는 데 필요한 경우에 연산자의 오른쪽에 있는 식 평가, 즉 합니다.</span><span class="sxs-lookup"><span data-stu-id="31470-114">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="31470-115">두 번째 식의 `&&` 연산자는 첫 번째 식으로 계산 하는 경우에 계산 됩니다 `true`;의 두 번째 식의 `||` 연산자는 첫 번째 식으로 계산 하는 경우에 계산 됩니다 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="31470-115">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="31470-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31470-116">See Also</span></span>
[<span data-ttu-id="31470-117">비트 연산자</span><span class="sxs-lookup"><span data-stu-id="31470-117">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="31470-118">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="31470-118">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="31470-119">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="31470-119">Symbol and Operator Reference</span></span>](index.md)
