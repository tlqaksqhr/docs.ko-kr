---
title: 식 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 11bacf436daf2a77a9cf46b4883d282143572e27
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756399"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="19bba-102">식 열 만들기</span><span class="sxs-lookup"><span data-stu-id="19bba-102">Creating Expression Columns</span></span>
<span data-ttu-id="19bba-103">테이블에서 같은 행의 다른 열 값이나 여러 행의 열 값에서 계산한 값을 포함할 수 있도록 열에 대한 식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="19bba-104">계산할 식을 정의하려면 대상 열의 <xref:System.Data.DataColumn.Expression%2A> 속성과 <xref:System.Data.DataColumn.ColumnName%2A> 속성을 사용하여 식에서 다른 열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="19bba-105">식 열의 <xref:System.Data.DataColumn.DataType%2A>은 이 식에서 반환되는 값에 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="19bba-106">다음 표에서는 식 열을 사용할 수 있는 몇 가지 방법의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="19bba-107">식 형식</span><span class="sxs-lookup"><span data-stu-id="19bba-107">Expression type</span></span>|<span data-ttu-id="19bba-108">예제</span><span class="sxs-lookup"><span data-stu-id="19bba-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="19bba-109">비교</span><span class="sxs-lookup"><span data-stu-id="19bba-109">Comparison</span></span>|<span data-ttu-id="19bba-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="19bba-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="19bba-111">계산</span><span class="sxs-lookup"><span data-stu-id="19bba-111">Computation</span></span>|<span data-ttu-id="19bba-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="19bba-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="19bba-113">집계</span><span class="sxs-lookup"><span data-stu-id="19bba-113">Aggregation</span></span>|<span data-ttu-id="19bba-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="19bba-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="19bba-115">설정할 수 있습니다는 **식** 기존 속성 **DataColumn** 개체 또는 있습니다 세 번째 인수에 전달 된 속성을 포함할 수는 <xref:System.Data.DataColumn> 다음 예제와 같이 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="19bba-116">식은 다른 식 열을 참조할 수 있습니다. 그러나 두 식이 서로를 참조하는 순환 참조에서는 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="19bba-117">식을 작성 하는 방법에 대 한 규칙에 대 한 참조는 <xref:System.Data.DataColumn.Expression%2A> 의 속성은 **DataColumn** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="19bba-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19bba-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19bba-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="19bba-119">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="19bba-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="19bba-120">DataTable</span><span class="sxs-lookup"><span data-stu-id="19bba-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="19bba-121">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="19bba-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
