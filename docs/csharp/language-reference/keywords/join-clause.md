---
title: "join 절(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- join
- join_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- join clause [C#]
- join keyword [C#]
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3368ba14101eda38ed8e3ee2bdc81bcab74a9b82
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="join-clause-c-reference"></a><span data-ttu-id="dc92f-102">join 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dc92f-102">join clause (C# Reference)</span></span>
<span data-ttu-id="dc92f-103">`join` 절은 개체 모델에서 직접적인 관계가 없는 서로 다른 소스 시퀀스의 요소를 연결하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-103">The `join` clause is useful for associating elements from different source sequences that have no direct relationship in the object model.</span></span> <span data-ttu-id="dc92f-104">각 소스의 요소가 같은지 비교할 수 있는 일부 값을 공유하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-104">The only requirement is that the elements in each source share some value that can be compared for equality.</span></span> <span data-ttu-id="dc92f-105">예를 들어 식품 유통업체에는 특정 제품의 공급업체 목록과 구매자 목록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-105">For example, a food distributor might have a list of suppliers of a certain product, and a list of buyers.</span></span> <span data-ttu-id="dc92f-106">예를 들어 `join` 절은 모두 동일한 지역에 있는, 해당 제품의 공급업체 및 구매자 목록을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-106">A `join` clause can be used, for example, to create a list of the suppliers and buyers of that product who are all in the same specified region.</span></span>  
  
 <span data-ttu-id="dc92f-107">`join` 절은 두 개의 소스 시퀀스를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-107">A `join` clause takes two source sequences as input.</span></span> <span data-ttu-id="dc92f-108">각 시퀀스의 요소는 다른 시퀀스의 속성과 비교할 수 있는 속성이거나 해당 속성을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-108">The elements in each sequence must either be or contain a property that can be compared to a corresponding property in the other sequence.</span></span> <span data-ttu-id="dc92f-109">`join` 절은 특수한 `equals` 키워드를 사용하여 지정된 키가 같은지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-109">The `join` clause compares the specified keys for equality by using the special `equals` keyword.</span></span> <span data-ttu-id="dc92f-110">`join` 절로 수행된 모든 조인은 동등 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-110">All joins performed by the `join` clause are equijoins.</span></span> <span data-ttu-id="dc92f-111">`join` 절의 출력 형태는 수행하는 조인의 특정 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-111">The shape of the output of a `join` clause depends on the specific type of join you are performing.</span></span> <span data-ttu-id="dc92f-112">다음은 세 가지 가장 일반적인 조인 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-112">The following are three most common join types:</span></span>  
  
-   <span data-ttu-id="dc92f-113">내부 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-113">Inner join</span></span>  
  
-   <span data-ttu-id="dc92f-114">그룹 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-114">Group join</span></span>  
  
-   <span data-ttu-id="dc92f-115">왼쪽 우선 외부 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-115">Left outer join</span></span>  
  
## <a name="inner-join"></a><span data-ttu-id="dc92f-116">내부 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-116">Inner Join</span></span>  
 <span data-ttu-id="dc92f-117">다음 예제에서는 간단한 내부 동등 조인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-117">The following example shows a simple inner equijoin.</span></span> <span data-ttu-id="dc92f-118">이 쿼리는 "제품 이름/범주" 쌍의 기본 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-118">This query produces a flat sequence of "product name / category" pairs.</span></span> <span data-ttu-id="dc92f-119">동일한 범주 문자열이 여러 요소에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-119">The same category string will appear in multiple elements.</span></span> <span data-ttu-id="dc92f-120">`categories`의 요소에 일치하는 `products`가 없는 경우 해당 범주는 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-120">If an element from `categories` has no matching `products`, that category will not appear in the results.</span></span>  
  
 <span data-ttu-id="dc92f-121">[!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dc92f-121">[!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_1.cs)]</span></span>  
  
 <span data-ttu-id="dc92f-122">자세한 내용은 [방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc92f-122">For more information, see [How to: Perform Inner Joins](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).</span></span>  
  
## <a name="group-join"></a><span data-ttu-id="dc92f-123">그룹 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-123">Group Join</span></span>  
 <span data-ttu-id="dc92f-124">`into` 식을 포함한 `join` 절을 그룹 조인이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-124">A `join` clause with an `into` expression is called a group join.</span></span>  
  
 <span data-ttu-id="dc92f-125">[!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="dc92f-125">[!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_2.cs)]</span></span>  
  
 <span data-ttu-id="dc92f-126">그룹 조인은 왼쪽 소스 시퀀스의 요소를 오른쪽 소스 시퀀스에서 일치하는 하나 이상의 요소와 연결하는 계층적 결과 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-126">A group join produces a hierarchical result sequence, which associates elements in the left source sequence with one or more matching elements in the right side source sequence.</span></span> <span data-ttu-id="dc92f-127">관계적인 측면에서 그룹 조인에는 해당 항목이 없으며, 그룹 조인은 기본적으로 개체 배열의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-127">A group join has no equivalent in relational terms; it is essentially a sequence of object arrays.</span></span>  
  
 <span data-ttu-id="dc92f-128">왼쪽 소스의 요소와 일치하는 오른쪽 소스 시퀀스의 요소가 없을 경우 `join` 절은 해당 항목에 대해 빈 배열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-128">If no elements from the right source sequence are found to match an element in the left source, the `join` clause will produce an empty array for that item.</span></span> <span data-ttu-id="dc92f-129">따라서 결과 시퀀스가 그룹으로 구성된다는 점을 제외하면 그룹 조인은 기본적으로 내부 동등 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-129">Therefore, the group join is still basically an inner-equijoin except that the result sequence is organized into groups.</span></span>  
  
 <span data-ttu-id="dc92f-130">그룹 조인의 결과를 선택하는 경우 항목에 액세스할 수 있지만 항목이 일치되는 키를 식별할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-130">If you just select the results of a group join, you can access the items, but you cannot identify the key that they match on.</span></span> <span data-ttu-id="dc92f-131">따라서 이전 예제와 같이 키 이름도 포함하는 새로운 유형으로 그룹 조인의 결과를 선택하는 것이 일반적으로 더 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-131">Therefore, it is generally more useful to select the results of the group join into a new type that also has the key name, as shown in the previous example.</span></span>  
  
 <span data-ttu-id="dc92f-132">또한 그룹 조인의 결과를 또 다른 하위 쿼리의 생성기로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-132">You can also, of course, use the result of a group join as the generator of another subquery:</span></span>  
  
 <span data-ttu-id="dc92f-133">[!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="dc92f-133">[!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_3.cs)]</span></span>  
  
 <span data-ttu-id="dc92f-134">자세한 내용은 [방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc92f-134">For more information, see [How to: Perform Grouped Joins](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md).</span></span>  
  
## <a name="left-outer-join"></a><span data-ttu-id="dc92f-135">왼쪽 우선 외부 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-135">Left Outer Join</span></span>  
 <span data-ttu-id="dc92f-136">왼쪽 우선 외부 조인에서는 오른쪽 시퀀스에 일치하는 요소가 없는 경우에도 왼쪽 소스 시퀀스의 모든 요소가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-136">In a left outer join, all the elements in the left source sequence are returned, even if no matching elements are in the right sequence.</span></span> <span data-ttu-id="dc92f-137">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서 왼쪽 우선 외부 조인을 수행하려면 그룹 조인과 함께 `DefaultIfEmpty` 메서드를 사용하여 왼쪽 요소에 일치하는 요소가 없을 경우 생성할 기본 오른쪽 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-137">To perform a left outer join in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], use the `DefaultIfEmpty` method in combination with a group join to specify a default right-side element to produce if a left-side element has no matches.</span></span> <span data-ttu-id="dc92f-138">`null`을 모든 참조 형식의 기본값으로 사용하거나 사용자 정의 기본 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-138">You can use `null` as the default value for any reference type, or you can specify a user-defined default type.</span></span> <span data-ttu-id="dc92f-139">다음 예제에서는 사용자 정의 기본 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-139">In the following example, a user-defined default type is shown:</span></span>  
  
 <span data-ttu-id="dc92f-140">[!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="dc92f-140">[!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_4.cs)]</span></span>  
  
 <span data-ttu-id="dc92f-141">자세한 내용은 [방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc92f-141">For more information, see [How to: Perform Left Outer Joins](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md).</span></span>  
  
## <a name="the-equals-operator"></a><span data-ttu-id="dc92f-142">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="dc92f-142">The equals operator</span></span>  
 <span data-ttu-id="dc92f-143">`join` 절은 동등 조인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-143">A `join` clause performs an equijoin.</span></span> <span data-ttu-id="dc92f-144">즉, 일치 항목만을 기준으로 두 키가 같은지 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-144">In other words, you can only base matches on the equality of two keys.</span></span> <span data-ttu-id="dc92f-145">"보다 큼"이나 "같지 않음"과 같은 다른 유형의 비교는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-145">Other types of comparisons such as "greater than" or "not equals" are not supported.</span></span> <span data-ttu-id="dc92f-146">모든 조인이 동등 조인인지 확인하기 위해 `join` 절은 `==` 연산자 대신 `equals` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-146">To make clear that all joins are equijoins, the `join` clause uses the `equals` keyword instead of the `==` operator.</span></span> <span data-ttu-id="dc92f-147">`equals` 키워드는 `join` 절에서만 사용할 수 있으며 한 가지 중요한 측면에서 `==` 연산자와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-147">The `equals` keyword can only be used in a `join` clause and it differs from the `==` operator in one important way.</span></span> <span data-ttu-id="dc92f-148">`equals`를 사용할 경우 왼쪽 키는 외부 소스 시퀀스를 사용하고 오른쪽 키는 내부 소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-148">With `equals`, the left key consumes the outer source sequence, and the right key consumes the inner source.</span></span> <span data-ttu-id="dc92f-149">외부 소스는 `equals`의 왼쪽 범위에만 있고 내부 소스 시퀀스는 오른쪽 범위에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-149">The outer source is only in scope on the left side of `equals` and the inner source sequence is only in scope on the right side.</span></span>  
  
## <a name="non-equijoins"></a><span data-ttu-id="dc92f-150">비동등 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-150">Non-Equijoins</span></span>  
 <span data-ttu-id="dc92f-151">여러 개의 `from` 절을 사용하여 비동등 조인, 크로스 조인 및 기타 사용자 지정 조인 작업을 수행하면 새 시퀀스를 독립적으로 쿼리에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-151">You can perform non-equijoins, cross joins, and other custom join operations by using multiple `from` clauses to introduce new sequences independently into a query.</span></span> <span data-ttu-id="dc92f-152">자세한 내용은 [방법: 사용자 지정 조인 작업 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc92f-152">For more information, see [How to: Perform Custom Join Operations](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).</span></span>  
  
## <a name="joins-on-object-collections-vs-relational-tables"></a><span data-ttu-id="dc92f-153">개체 컬렉션 및 관계형 테이블에서 조인</span><span class="sxs-lookup"><span data-stu-id="dc92f-153">Joins on object collections vs. relational tables</span></span>  
 <span data-ttu-id="dc92f-154">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식에서 조인 작업은 개체 컬렉션에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-154">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression, join operations are performed on object collections.</span></span> <span data-ttu-id="dc92f-155">개체 컬렉션은 두 개의 관계형 테이블과 정확히 동일한 방식으로 "조인"할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-155">Object collections cannot be "joined" in exactly the same way as two relational tables.</span></span> <span data-ttu-id="dc92f-156">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서는 두 소스 시퀀스가 관계로 연결되지 않는 경우에만 명시적 `join` 절이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-156">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], explicit `join` clauses are only required when two source sequences are not tied by any relationship.</span></span> <span data-ttu-id="dc92f-157">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]로 작업할 때 외래 키 테이블은 기본 테이블의 속성으로 개체 모델에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-157">When working with [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], foreign key tables are represented in the object model as properties of the primary table.</span></span> <span data-ttu-id="dc92f-158">예를 들어 Northwind 데이터베이스에서 Customer 테이블은 Orders 테이블과 외래 키 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-158">For example, in the Northwind database, the Customer table has a foreign key relationship with the Orders table.</span></span> <span data-ttu-id="dc92f-159">테이블을 개체 모델에 매핑하면 Customer 클래스는 해당 Customer와 연결된 Orders 컬렉션을 포함하는 Orders 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-159">When you map the tables to the object model, the Customer class has an Orders property that contains the collection of Orders associated with that Customer.</span></span> <span data-ttu-id="dc92f-160">사실상 조인은 이미 수행된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-160">In effect, the join has already been done for you.</span></span>  
  
 <span data-ttu-id="dc92f-161">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 컨텍스트에서 관련 테이블을 쿼리하는 방법에 대한 자세한 내용은 [방법: 데이터베이스 관계 매핑](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc92f-161">For more information about querying across related tables in the context of [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], see [How to: Map Database Relationships](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md).</span></span>  
  
## <a name="composite-keys"></a><span data-ttu-id="dc92f-162">복합 키</span><span class="sxs-lookup"><span data-stu-id="dc92f-162">Composite Keys</span></span>  
 <span data-ttu-id="dc92f-163">복합 키를 사용하여 여러 값이 같은지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-163">You can test for equality of multiple values by using a composite key.</span></span> <span data-ttu-id="dc92f-164">자세한 내용은 [방법: 복합 키를 사용하여 조인](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc92f-164">For more information, see [How to: Join by Using Composite Keys](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md).</span></span> <span data-ttu-id="dc92f-165">복합 키는 `group` 절에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-165">Composite keys can be also used in a `group` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc92f-166">예제</span><span class="sxs-lookup"><span data-stu-id="dc92f-166">Example</span></span>  
 <span data-ttu-id="dc92f-167">다음 예제에서는 동일한 데이터 소스에서 동일한 일치하는 키를 사용하여 내부 조인, 그룹 조인 및 왼쪽 우선 외부 조인의 결과를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-167">The following example compares the results of an inner join, a group join, and a left outer join on the same data sources by using the same matching keys.</span></span> <span data-ttu-id="dc92f-168">콘솔 디스플레이에 결과를 명확하게 나타내기 위해 이러한 예제에 몇 가지 추가 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-168">Some extra code is added to these examples to clarify the results in the console display.</span></span>  
  
 <span data-ttu-id="dc92f-169">[!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="dc92f-169">[!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_5.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc92f-170">설명</span><span class="sxs-lookup"><span data-stu-id="dc92f-170">Remarks</span></span>  
 <span data-ttu-id="dc92f-171">뒤에 `into`가 오지 않는 `join` 절은 <xref:System.Linq.Enumerable.Join%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-171">A `join` clause that is not followed by `into` is translated into a <xref:System.Linq.Enumerable.Join%2A> method call.</span></span> <span data-ttu-id="dc92f-172">뒤에 `into`가 오는 `join` 절은 <xref:System.Linq.Enumerable.GroupJoin%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc92f-172">A `join` clause that is followed by `into` is translated to a <xref:System.Linq.Enumerable.GroupJoin%2A> method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc92f-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc92f-173">See Also</span></span>  
 <span data-ttu-id="dc92f-174">[쿼리 키워드(LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-174">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="dc92f-175">[LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-175">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="dc92f-176">[조인 작업](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107) </span><span class="sxs-lookup"><span data-stu-id="dc92f-176">[Join Operations](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107) </span></span>  
 <span data-ttu-id="dc92f-177">[group 절](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-177">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="dc92f-178">[방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-178">[How to: Perform Left Outer Joins](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md) </span></span>  
 <span data-ttu-id="dc92f-179">[방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-179">[How to: Perform Inner Joins](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) </span></span>  
 <span data-ttu-id="dc92f-180">[방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-180">[How to: Perform Grouped Joins](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md) </span></span>  
 <span data-ttu-id="dc92f-181">[방법: Join 절 결과를 순서대로 정렬](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-181">[How to: Order the Results of a Join Clause](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 <span data-ttu-id="dc92f-182">[방법: 복합 키를 사용하여 조인](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md) </span><span class="sxs-lookup"><span data-stu-id="dc92f-182">[How to: Join by Using Composite Keys](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md) </span></span>  
 [<span data-ttu-id="dc92f-183">방법: 샘플 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="dc92f-183">How to: Install Sample Databases</span></span>](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)

