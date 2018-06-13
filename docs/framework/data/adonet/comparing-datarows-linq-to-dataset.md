---
title: DataRow 비교(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 79fc91092badfd871a1409e2ee602272f3eae100
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756282"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="c2fce-102">DataRow 비교(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="c2fce-102">Comparing DataRows (LINQ to DataSet)</span></span>
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]<span data-ttu-id="c2fce-103">에는 소스 요소가 같은지 여부를 확인하는 다양한 집합 연산자가 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-103"> defines various set operators to compare source elements to see if they are equal.</span></span> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]<span data-ttu-id="c2fce-104">에서는 다음과 같은 집합 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-104"> provides the following set operators:</span></span>  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="c2fce-105">이러한 연산자는 각 요소 컬렉션에 대해 <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> 및 <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> 메서드를 호출하여 소스 요소를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="c2fce-106"><xref:System.Data.DataRow>의 경우 이러한 연산자는 참조 비교를 수행합니다. 참조 비교는 일반적으로 표 형식의 데이터에 대한 집합 연산에는 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="c2fce-107">집합 연산에서는 일반적으로 요소 값이 같은지 여부와 요소 값이 요소 참조가 아닌지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="c2fce-108">따라서 <xref:System.Data.DataRowComparer> 클래스가 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="c2fce-109">이 클래스는 행 값을 비교하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="c2fce-110"><xref:System.Data.DataRowComparer> 클래스에는 <xref:System.Data.DataRow>에 대한 값 비교 구현이 있으므로 이 클래스는 <xref:System.Linq.Enumerable.Distinct%2A>와 같은 집합 연산에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="c2fce-111">이 클래스는 직접 인스턴스화할 수 없기 때문에 <xref:System.Data.DataRowComparer.Default%2A> 속성을 사용하여 <xref:System.Data.DataRowComparer%601>의 인스턴스를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="c2fce-112">그런 다음 <xref:System.Data.DataRowComparer%601.Equals%2A> 메서드를 호출하면서 비교할 두 <xref:System.Data.DataRow> 개체를 입력 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="c2fce-113"><xref:System.Data.DataRowComparer%601.Equals%2A> 메서드에서는 두 `true` 개체에 있는 정렬된 열 값 집합이 같으면 <xref:System.Data.DataRow>를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2fce-114">예제</span><span class="sxs-lookup"><span data-stu-id="c2fce-114">Example</span></span>  
 <span data-ttu-id="c2fce-115">이 예제에서는 `Intersect`를 사용하여 두 테이블에 있는 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="c2fce-116">예제</span><span class="sxs-lookup"><span data-stu-id="c2fce-116">Example</span></span>  
 <span data-ttu-id="c2fce-117">다음 예제에서는 두 행을 비교한 다음 두 행의 해시 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2fce-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="c2fce-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2fce-118">See Also</span></span>  
 <xref:System.Data.DataRowComparer>  
 [<span data-ttu-id="c2fce-119">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="c2fce-119">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="c2fce-120">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="c2fce-120">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
