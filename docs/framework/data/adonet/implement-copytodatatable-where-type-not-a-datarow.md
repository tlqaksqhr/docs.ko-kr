---
title: "방법: CopyToDataTable 구현&lt;T&gt; 제네릭 형식 T가 DataRow 아닙니다"
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
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1ca633d257b9eafcab646295667eb37ad41434a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-copytodatatablelttgt-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="98032-102">방법: CopyToDataTable 구현&lt;T&gt; 제네릭 형식 T가 DataRow 아닙니다</span><span class="sxs-lookup"><span data-stu-id="98032-102">How to: Implement CopyToDataTable&lt;T&gt; Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="98032-103">대개 <xref:System.Data.DataTable> 개체는 데이터 바인딩에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98032-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="98032-104"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 쿼리 결과를 받아서 나중에 데이터 바인딩에 사용할 수 있도록 데이터를 <xref:System.Data.DataTable>에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="98032-105">하지만 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 제네릭 매개 변수 <xref:System.Collections.Generic.IEnumerable%601>가 `T` 형식인 <xref:System.Data.DataRow> 소스에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="98032-106">이 제한은 유용하지만 이로 인해 일련의 스칼라 형식, 익명 형식을 프로젝션하는 쿼리 또는 테이블 조인을 수행하는 쿼리에서 테이블을 만들지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98032-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="98032-107">이 항목에서는 `CopyToDataTable<T>` 형식 이외의 제네릭 매개 변수 `T` 형식을 사용할 수 있는 두 가지 사용자 지정 <xref:System.Data.DataRow> 확장을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="98032-108"><xref:System.Data.DataTable> 소스에서 <xref:System.Collections.Generic.IEnumerable%601>을 만드는 로직은 `ObjectShredder<T>` 클래스에 있으며, 이 클래스는 두 오버로드 `CopyToDataTable<T>` 확장 메서드로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="98032-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="98032-109">`Shred` 클래스의 `ObjectShredder<T>` 메서드는 채워진 <xref:System.Data.DataTable>을 반환하며 세 개의 입력 매개 변수로 <xref:System.Collections.Generic.IEnumerable%601> 소스, <xref:System.Data.DataTable> 및 <xref:System.Data.LoadOption> 열거형을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="98032-110">반환된 <xref:System.Data.DataTable>의 초기 스키마는 형식 `T`의 스키마에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="98032-111">기존 테이블이 입력으로 제공되는 경우 해당 스키마는 형식 `T`의 스키마와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="98032-112">형식 `T`의 각 public 속성 및 필드는 반환된 테이블에서 <xref:System.Data.DataColumn>으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="98032-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="98032-113">소스 시퀀스에 `T`에서 파생된 형식이 포함되는 경우 추가 public 속성 또는 필드를 사용할 수 있도록 반환된 테이블 스키마가 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="98032-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="98032-114">사용자 지정에 대 한 예제 `CopyToDataTable<T>` 메서드 참조 [쿼리는에서 DataTable 만들기](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="98032-115">사용자 지정 CopyToDataTable 구현 하려면\<T > 응용 프로그램에서 메서드</span><span class="sxs-lookup"><span data-stu-id="98032-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1.  <span data-ttu-id="98032-116">`ObjectShredder<T>` 소스에서 <xref:System.Data.DataTable>을 만드는 <xref:System.Collections.Generic.IEnumerable%601> 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  
  
2.  <span data-ttu-id="98032-117">클래스에서 사용자 지정 `CopyToDataTable<T>` 확장 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-117">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3.  <span data-ttu-id="98032-118">응용 프로그램에 `ObjectShredder<T>` 클래스 및 `CopyToDataTable<T>` 확장 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98032-118">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="98032-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98032-119">See Also</span></span>  
 [<span data-ttu-id="98032-120">쿼리에서 DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="98032-120">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 [<span data-ttu-id="98032-121">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="98032-121">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
