---
title: 데이터 집합 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: 3c48b430b1a087a79db37398b2c68014b8077c55
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="creating-a-dataset"></a><span data-ttu-id="2cd01-102">데이터 집합 만들기</span><span class="sxs-lookup"><span data-stu-id="2cd01-102">Creating a DataSet</span></span>
<span data-ttu-id="2cd01-103"><xref:System.Data.DataSet>의 인스턴스는 <xref:System.Data.DataSet> 생성자를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="2cd01-104">선택적으로 이름 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-104">Optionally specify a name argument.</span></span> <span data-ttu-id="2cd01-105"><xref:System.Data.DataSet>의 이름을 지정하지 않으면 해당 이름은 "NewDataSet"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="2cd01-106">기존 <xref:System.Data.DataSet>을 기반으로 새 <xref:System.Data.DataSet>을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2cd01-107">새 <xref:System.Data.DataSet>은 기존 <xref:System.Data.DataSet>과 동일한 복사본이거나, 관계 구조 또는 스키마는 복사하지만 기존 <xref:System.Data.DataSet>의 데이터는 포함하지 않는 <xref:System.Data.DataSet>의 복제이거나, 또는 <xref:System.Data.DataSet> 메서드를 사용하여 기존 <xref:System.Data.DataSet>의 수정된 행만 포함하는 <xref:System.Data.DataSet.GetChanges%2A>의 하위 집합일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="2cd01-108">자세한 내용은 참조 [데이터 집합 콘텐츠 복사](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-108">For more information, see [Copying DataSet Contents](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="2cd01-109">다음 코드 예제에서는 <xref:System.Data.DataSet>의 인스턴스를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cd01-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cd01-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cd01-110">See Also</span></span>  
 [<span data-ttu-id="2cd01-111">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="2cd01-111">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="2cd01-112">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="2cd01-112">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="2cd01-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="2cd01-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
