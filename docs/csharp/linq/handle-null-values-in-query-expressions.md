---
title: "쿼리 식의 Null 값 처리"
description: "쿼리 식의 Null 값을 처리하는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f4f189504c57c9c01268b10bc96ad3c9af49ddbd
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="699ed-104">쿼리 식의 Null 값 처리</span><span class="sxs-lookup"><span data-stu-id="699ed-104">Handle null values in query expressions</span></span>

<span data-ttu-id="699ed-105">이 예제에서는 소스 컬렉션에서 가능한 null 값을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="699ed-106"><xref:System.Collections.Generic.IEnumerable%601> 등의 개체 컬렉션에는 값이 [null](../language-reference/keywords/null.md)인 요소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="699ed-107">소스 컬렉션이 null이거나 값이 null인 요소를 포함하고 사용 중인 쿼리가 null 값을 처리하지 않는 경우 쿼리를 실행하면 <xref:System.NullReferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="699ed-108">예제</span><span class="sxs-lookup"><span data-stu-id="699ed-108">Example</span></span>

 <span data-ttu-id="699ed-109">다음 예제와 같이 null 참조 예외를 피하도록 방어적으로 코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 <span data-ttu-id="699ed-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="699ed-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span></span>  
  
 <span data-ttu-id="699ed-111">이전 예제에서 `where` 절은 범주 시퀀스에서 모든 null 요소를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-111">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="699ed-112">이 방법은 join 절의 null 확인과 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-112">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="699ed-113">`Products.CategoryID`가 `Nullable<int>`의 축약형인 `int?` 형식이므로 이 예제에서는 null이 있는 조건식이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-113">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="699ed-114">예제</span><span class="sxs-lookup"><span data-stu-id="699ed-114">Example</span></span>

 <span data-ttu-id="699ed-115">join 절에서 비교 키 중 하나만 nullable 값 형식인 경우에는 쿼리 식에서 다른 키를 nullable 형식으로 캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-115">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="699ed-116">다음 예제에서는 `EmployeeID`가 `int?` 형식의 값이 포함된 열이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="699ed-116">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 <span data-ttu-id="699ed-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="699ed-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699ed-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="699ed-118">See also</span></span>  
 <span data-ttu-id="699ed-119"><xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="699ed-119"><xref:System.Nullable%601></span></span>   
 <span data-ttu-id="699ed-120">[LINQ 쿼리 식](index.md) </span><span class="sxs-lookup"><span data-stu-id="699ed-120">[LINQ query expressions](index.md) </span></span>  
 [<span data-ttu-id="699ed-121">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="699ed-121">Nullable types</span></span>](../programming-guide/nullable-types/index.md)

