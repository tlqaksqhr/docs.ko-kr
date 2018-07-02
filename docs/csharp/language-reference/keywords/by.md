---
title: by 상황별 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: e1748948ce6e036d0a3791940fd900f79f27d51f
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315136"
---
# <a name="by-c-reference"></a><span data-ttu-id="33503-102">by(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="33503-102">by (C# Reference)</span></span>

<span data-ttu-id="33503-103">`by` 상황별 키워드는 쿼리 식의 `group` 절에서 사용되어 반환된 항목의 그룹화 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33503-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="33503-104">자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33503-104">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="33503-105">예</span><span class="sxs-lookup"><span data-stu-id="33503-105">Example</span></span>

<span data-ttu-id="33503-106">다음 예제에서는 `group` 절에 `by` 상황별 키워드를 사용하여 각 학생의 성에서 첫 번째 문자에 따라 학생들을 그룹화하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33503-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="33503-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33503-107">See also</span></span>

[<span data-ttu-id="33503-108">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="33503-108">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
