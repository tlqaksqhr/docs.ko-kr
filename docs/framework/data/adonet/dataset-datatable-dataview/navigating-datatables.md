---
title: "DataTable 탐색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de3d0125adc6f18ebebf13ff3cf2fa5119ec17df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="navigating-datatables"></a><span data-ttu-id="a87ed-102">DataTable 탐색</span><span class="sxs-lookup"><span data-stu-id="a87ed-102">Navigating DataTables</span></span>
<span data-ttu-id="a87ed-103"><xref:System.Data.DataTableReader>는 하나 이상의 <xref:System.Data.DataTable> 개체 내용을 하나 이상의 앞으로만 이동 가능한 읽기 전용 결과 집합 형태로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a87ed-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="a87ed-104"><xref:System.Data.DataTableReader> 메서드를 사용하여 <xref:System.Data.DataSet.CreateDataReader%2A>를 만들 경우에는 여러 개의 결과 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a87ed-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="a87ed-105">결과 집합이 둘 이상이면 <xref:System.Data.DataTableReader.NextResult%2A> 메서드는 커서를 다음 결과 집합으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a87ed-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="a87ed-106">이것은 앞으로만 이동 가능한 프로세스이며,</span><span class="sxs-lookup"><span data-stu-id="a87ed-106">This is a forward-only process.</span></span> <span data-ttu-id="a87ed-107">이전 결과 집합으로 돌아갈 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a87ed-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a87ed-108">예</span><span class="sxs-lookup"><span data-stu-id="a87ed-108">Example</span></span>  
 <span data-ttu-id="a87ed-109">다음 예제에서는 `TestConstructor` 메서드에서는 두 개의 <xref:System.Data.DataTable> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a87ed-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="a87ed-110">이 생성자에 대 한 설명 하기 위해는 <xref:System.Data.DataTableReader> 클래스, 예제에서는 새 **DataTableReader** 두를 포함 하는 배열에 따라 **Datatable**, 간단한 작업을 수행 하 고 콘솔 창에는 처음 몇 개의 열에서 콘텐츠를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="a87ed-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a87ed-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a87ed-111">See Also</span></span>  
 [<span data-ttu-id="a87ed-112">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="a87ed-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="a87ed-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="a87ed-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
