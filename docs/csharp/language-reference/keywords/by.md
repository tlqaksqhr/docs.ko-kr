---
title: by(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
caps.latest.revision: 6
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bbbf64eb86c3cca5de659bffce7c5c0639461f85
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="by-c-reference"></a><span data-ttu-id="3950c-102">by(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3950c-102">by (C# Reference)</span></span>
<span data-ttu-id="3950c-103">`by` 상황별 키워드는 쿼리 식의 `group` 절에서 사용되어 반환된 항목의 그룹화 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3950c-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="3950c-104">자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3950c-104">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3950c-105">예제</span><span class="sxs-lookup"><span data-stu-id="3950c-105">Example</span></span>  
 <span data-ttu-id="3950c-106">다음 예제에서는 `group` 절에 `by` 상황별 키워드를 사용하여 각 학생의 성에서 첫 번째 문자에 따라 학생들을 그룹화하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3950c-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/by_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3950c-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3950c-107">See Also</span></span>  
 [<span data-ttu-id="3950c-108">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="3950c-108">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
