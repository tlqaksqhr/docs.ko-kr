---
title: "제네릭 Field 및 SetField 메서드(LINQ to DataSet)"
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
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6281f2fdd00f210f09c97861d2ea723d259af004
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a><span data-ttu-id="43cbd-102">제네릭 Field 및 SetField 메서드(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="43cbd-102">Generic Field and SetField Methods (LINQ to DataSet)</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="43cbd-103">은 열 값에 액세스할 수 있도록 확장 메서드인 <xref:System.Data.DataRow> 및 <xref:System.Data.DataRowExtensions.Field%2A> 메서드를 <xref:System.Data.DataRowExtensions.SetField%2A> 클래스에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-103"> provides extension methods to the <xref:System.Data.DataRow> class for accessing column values: the <xref:System.Data.DataRowExtensions.Field%2A> method and the <xref:System.Data.DataRowExtensions.SetField%2A> method.</span></span> <span data-ttu-id="43cbd-104">개발자는 이러한 메서드를 사용하여 열 값에 쉽게 액세스할 수 있으며, 특히 null 값과 관련된 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-104">These methods provide easier access to column values for developers, especially regarding null values.</span></span> <span data-ttu-id="43cbd-105"><xref:System.Data.DataSet>은 <xref:System.DBNull.Value>를 사용하여 null 값을 나타내는 반면 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]에서는 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]에서 도입된 nullable 형식 지원을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-105">The <xref:System.Data.DataSet> uses <xref:System.DBNull.Value> to represent null values, whereas [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] uses the nullable type support introduced in the [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span> <span data-ttu-id="43cbd-106"><xref:System.Data.DataRow>의 기존 열 접근자를 사용하려면 반환 개체를 적절한 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-106">Using the pre-existing column accessor in <xref:System.Data.DataRow> requires you to cast the return object to the appropriate type.</span></span> <span data-ttu-id="43cbd-107">반환된 <xref:System.Data.DataRow>가 암시적으로 다른 형식으로 캐스팅되면 <xref:System.DBNull.Value>이 throw되므로 <xref:System.InvalidCastException>의 특정 필드가 null일 가능성이 있는 경우 명시적으로 null 값을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-107">If a particular field in a <xref:System.Data.DataRow> can be null, you must explicitly check for a null value because returning <xref:System.DBNull.Value> and implicitly casting it to another type throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="43cbd-108">다음 예제에서 <xref:System.Data.DataRow.IsNull%2A> 메서드를 사용하여 null 값을 확인하지 않으면 인덱서에서 <xref:System.DBNull.Value>를 반환하면서 <xref:System.String>으로 캐스팅할 때 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-108">In the following example, if the <xref:System.Data.DataRow.IsNull%2A> method was not used to check for a null value, an exception would be thrown if the indexer returned <xref:System.DBNull.Value> and tried to cast it to a <xref:System.String>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 <span data-ttu-id="43cbd-109"><xref:System.Data.DataRowExtensions.Field%2A> 메서드는 <xref:System.Data.DataRow>의 열 값에 대한 액세스를 제공하고 <xref:System.Data.DataRowExtensions.SetField%2A>는 <xref:System.Data.DataRow>의 열 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-109">The <xref:System.Data.DataRowExtensions.Field%2A> method provides access to the column values of a <xref:System.Data.DataRow> and the <xref:System.Data.DataRowExtensions.SetField%2A> sets column values in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="43cbd-110">이전 예제에서와 마찬가지로 <xref:System.Data.DataRowExtensions.Field%2A> 메서드와 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드에서 nullable 형식이 처리되므로 명시적으로 null 값을 검사하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-110">Both the <xref:System.Data.DataRowExtensions.Field%2A> method and <xref:System.Data.DataRowExtensions.SetField%2A> method handle nullable types, so you do not have to explicitly check for null values as in the previous example.</span></span> <span data-ttu-id="43cbd-111">또한 두 메서드 모두 제네릭 메서드이므로 반환 형식을 캐스팅하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-111">Both methods are generic methods, also, so you do not have to cast the return type.</span></span>  
  
 <span data-ttu-id="43cbd-112">다음 예제에서는 <xref:System.Data.DataRowExtensions.Field%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-112">The following example uses the <xref:System.Data.DataRowExtensions.Field%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 <span data-ttu-id="43cbd-113">`T` 메서드 및 <xref:System.Data.DataRowExtensions.Field%2A> 메서드의 제네릭 매개 변수 <xref:System.Data.DataRowExtensions.SetField%2A>에 지정된 데이터 형식은 내부 값의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-113">Note that the data type specified in the generic parameter `T` of the <xref:System.Data.DataRowExtensions.Field%2A> method and the <xref:System.Data.DataRowExtensions.SetField%2A> method must match the type of the underlying value.</span></span> <span data-ttu-id="43cbd-114">그렇지 않으면 <xref:System.InvalidCastException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-114">Otherwise, an <xref:System.InvalidCastException> exception will be thrown.</span></span> <span data-ttu-id="43cbd-115">지정된 열 이름도 <xref:System.Data.DataSet>의 열 이름과 일치해야 하며, 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-115">The specified column name must also match the name of a column in the <xref:System.Data.DataSet>, or an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="43cbd-116">두 경우 모두 쿼리가 실행되는 런타임에 데이터 열거형에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-116">In both cases, the exception is thrown at run time during the enumeration of the data when the query is executed.</span></span>  
  
 <span data-ttu-id="43cbd-117"><xref:System.Data.DataRowExtensions.SetField%2A> 메서드 자체에서는 형식 변환이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-117">The <xref:System.Data.DataRowExtensions.SetField%2A> method itself does not perform any type conversions.</span></span> <span data-ttu-id="43cbd-118">그렇다고 해서 형식 변환이 발생하지 않는다는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-118">This does not mean, however, that a type conversion will not occur.</span></span> <span data-ttu-id="43cbd-119"><xref:System.Data.DataRowExtensions.SetField%2A> 메서드는 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] 클래스의 <xref:System.Data.DataRow> 동작을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-119">The <xref:System.Data.DataRowExtensions.SetField%2A> method exposes the [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] behavior of the <xref:System.Data.DataRow> class.</span></span> <span data-ttu-id="43cbd-120"><xref:System.Data.DataRow> 개체에서 형식 변환을 수행하면 변환된 값은 <xref:System.Data.DataRow> 개체에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cbd-120">A type conversion could be performed by the <xref:System.Data.DataRow> object and the converted value would then be saved to the <xref:System.Data.DataRow> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43cbd-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43cbd-121">See Also</span></span>  
 <xref:System.Data.DataRowExtensions>
