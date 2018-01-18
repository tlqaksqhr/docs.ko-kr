---
title: "N 계층 응용 프로그램에서 데이터 검색 및 CUD 작업(LINQ to SQL)"
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
ms.assetid: c3133d53-83ed-4a4d-af8b-82edcf3831db
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6cdf1a859595c82b8eea60311c3c96353849e3dc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a><span data-ttu-id="e88c6-102">N 계층 응용 프로그램에서 데이터 검색 및 CUD 작업(LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="e88c6-102">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>
<span data-ttu-id="e88c6-103">Customers 또는 Orders와 같은 엔터티 개체를 네트워크상의 클라이언트로 serialize하면 해당 엔터티가 원래 데이터 컨텍스트에서 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-103">When you serialize entity objects such as Customers or Orders to a client over a network, those entities are detached from their data context.</span></span> <span data-ttu-id="e88c6-104">데이터 컨텍스트에서는 분리된 엔터티 개체에 대해서는 변경 내용이나 다른 개체와의 관계를 더 이상 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-104">The data context no longer tracks their changes or their associations with other objects.</span></span> <span data-ttu-id="e88c6-105">이러한 특징은 클라이언트에서 데이터를 읽기만 하는 경우에는 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-105">This is not an issue as long as the clients are only reading the data.</span></span> <span data-ttu-id="e88c6-106">또한 클라이언트가 데이터베이스에 새 행을 추가할 수 있게 하는 것도 비교적 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-106">It is also relatively simple to enable clients to add new rows to a database.</span></span> <span data-ttu-id="e88c6-107">그러나 응용 프로그램에서 클라이언트가 데이터를 업데이트하거나 삭제해야 하는 경우에는 <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>를 호출하기 전에 새 데이터 컨텍스트에 엔터티를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-107">However, if your application requires that clients be able to update or delete data, then you must attach the entities to a new data context before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e88c6-108">또한 원래 값을 기준으로 낙관적 동시성 검사를 사용하는 경우에는 어떤 방법으로든 데이터베이스에 원래 엔터티와 수정된 엔터티를 모두 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-108">In addition, if you are using an optimistic concurrency check with original values, then you will also need a way to provide the database both the original entity and the entity as modified.</span></span> <span data-ttu-id="e88c6-109">`Attach` 메서드는 분리된 엔터티를 새 데이터 컨텍스트에 연결하기 위해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-109">The `Attach` methods are provided to enable you to put entities into a new data context after they have been detached.</span></span>  
  
 <span data-ttu-id="e88c6-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 엔터티 대신 프록시 개체를 serialize하는 경우에도 데이터베이스에 데이터를 전송하려면 DAL(데이터 액세스 계층)에서 엔터티를 만들어 새 <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-110">Even if you are serializing proxy objects in place of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entities, you still have to construct an entity on the data access layer (DAL), and attach it to a new <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>, in order to submit the data to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e88c6-111">은 엔터티가 serialize되는 방법은 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-111"> is completely indifferent about how entities are serialized.</span></span> <span data-ttu-id="e88c6-112">사용 하는 방법에 대 한 자세한 내용은 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Windows Communication Foundation (WCF)를 사용 하 여 직렬화 할 수 있는 클래스를 생성 하려면 SQLMetal 도구, 참조 및 [하는 방법: 엔터티를 직렬화 가능 하 게](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-112">For more information about how to use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] and SQLMetal tools to generate classes that are serializable by using Windows Communication Foundation (WCF), see [How to: Make Entities Serializable](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e88c6-113">`Attach` 메서드는 새 엔터티 또는 deserialize된 엔터티에 대해서만 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-113">Only call the `Attach` methods on new or deserialized entities.</span></span> <span data-ttu-id="e88c6-114">엔터티는 serialization을 통해서만 원래 데이터 컨텍스트로부터 분리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-114">The only way for an entity to be detached from its original data context is for it to be serialized.</span></span> <span data-ttu-id="e88c6-115">이전 데이터 컨텍스트에서 지연 로더가 있는 분리되지 않은 엔터티를 새 데이터 컨텍스트에 연결하려고 하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-115">If you try to attach an undetached entity to a new data context, and that entity still has deferred loaders from its previous data context, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] will thrown an exception.</span></span> <span data-ttu-id="e88c6-116">서로 다른 두 데이터 컨텍스트의 지연 로더가 있는 엔터티에 대해 삽입, 업데이트 및 삭제 작업을 수행하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-116">An entity with deferred loaders from two different data contexts could cause unwanted results when you perform insert, update, and delete operations on that entity.</span></span> <span data-ttu-id="e88c6-117">지연 된 로더에 대 한 자세한 내용은 참조 [지연 된 실행과 즉시 로드 비교](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-117">For more information about deferred loaders, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="retrieving-data"></a><span data-ttu-id="e88c6-118">데이터 검색</span><span class="sxs-lookup"><span data-stu-id="e88c6-118">Retrieving Data</span></span>  
  
### <a name="client-method-call"></a><span data-ttu-id="e88c6-119">클라이언트 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="e88c6-119">Client Method Call</span></span>  
 <span data-ttu-id="e88c6-120">다음 예제에서는 Windows Forms 클라이언트에서 DAL에 대해 호출하는 샘플 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-120">The following examples show a sample method call to the DAL from a Windows Forms client.</span></span> <span data-ttu-id="e88c6-121">이 예제에서 DAL은 Windows 서비스 라이브러리로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-121">In this example, the DAL is implemented as a Windows Service Library:</span></span>  
  
```vb  
Private Function GetProdsByCat_Click(ByVal sender As Object, ByVal e _  
    As EventArgs)  
  
    ' Create the WCF client proxy.  
    Dim proxy As New NorthwindServiceReference.Service1Client  
  
    ' Call the method on the service.  
    Dim products As NorthwindServiceReference.Product() = _  
        proxy.GetProductsByCategory(1)  
  
    ' If the database uses original values for concurrency checks,  
    ' the client needs to store them and pass them back to the  
    ' middle tier along with the new values when updating data.  
  
    For Each v As NorthwindClient1.NorthwindServiceReference.Product _  
        In products  
        ' Persist to a List(Of Product) declared at class scope.  
        ' Additional change-tracking logic is the responsibility  
        ' of the presentation tier and/or middle tier.  
        originalProducts.Add(v)  
    Next  
  
    ' (Not shown) Bind the products list to a control  
    ' and/or perform whatever processing is necessary.  
End Function  
```  
  
```csharp  
private void GetProdsByCat_Click(object sender, EventArgs e)  
{  
    // Create the WCF client proxy.  
    NorthwindServiceReference.Service1Client proxy =   
    new NorthwindClient.NorthwindServiceReference.Service1Client();  
  
    // Call the method on the service.  
    NorthwindServiceReference.Product[] products =   
    proxy.GetProductsByCategory(1);  
  
    // If the database uses original values for concurrency checks,   
    // the client needs to store them and pass them back to the   
    // middle tier along with the new values when updating data.  
    foreach (var v in products)  
    {  
        // Persist to a list<Product> declared at class scope.  
        // Additional change-tracking logic is the responsibility  
        // of the presentation tier and/or middle tier.  
        originalProducts.Add(v);  
    }  
  
    // (Not shown) Bind the products list to a control  
    // and/or perform whatever processing is necessary.  
    }  
```  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="e88c6-122">중간 계층 구현</span><span class="sxs-lookup"><span data-stu-id="e88c6-122">Middle Tier Implementation</span></span>  
 <span data-ttu-id="e88c6-123">다음 예제에서는 중간 계층에서 구현하는 인터페이스 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-123">The following example shows an implementation of the interface method on the middle tier.</span></span> <span data-ttu-id="e88c6-124">다음 두 가지 주요 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="e88c6-124">The following are the two main points to note:</span></span>  
  
-   <span data-ttu-id="e88c6-125"><xref:System.Data.Linq.DataContext>는 메서드 범위에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-125">The <xref:System.Data.Linq.DataContext> is declared at method scope.</span></span>  
  
-   <span data-ttu-id="e88c6-126">메서드는 실제 결과의 <xref:System.Collections.IEnumerable> 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-126">The method returns an <xref:System.Collections.IEnumerable> collection of the actual results.</span></span> <span data-ttu-id="e88c6-127">serializer는 쿼리를 실행하여 클라이언트/프레젠테이션 계층에 결과를 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-127">The serializer will execute the query to send the results back to the client/presentation tier.</span></span> <span data-ttu-id="e88c6-128">중간 계층에서 쿼리 결과에 로컬로 액세스하려면 쿼리 변수에 대해 `ToList` 또는 `ToArray`를 호출하여 메서드를 강제로 실행한 후</span><span class="sxs-lookup"><span data-stu-id="e88c6-128">To access the query results locally on the middle tier, you can force execution by calling `ToList` or `ToArray` on the query variable.</span></span> <span data-ttu-id="e88c6-129">해당 목록 또는 배열을 `IEnumerable`로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-129">You can then return that list or array as an `IEnumerable`.</span></span>  
  
```vb  
Public Function GetProductsByCategory(ByVal categoryID As Integer) _  
    As IEnumerable(Of Product)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    Dim productQuery = _  
    From prod In db.Products _  
    Where prod.CategoryID = categoryID _  
    Select prod  
  
    Return productQuery.AsEnumerable()  
  
End Function  
```  
  
```csharp  
public IEnumerable<Product> GetProductsByCategory(int categoryID)  
{  
    NorthwindClasses1DataContext db =   
    new NorthwindClasses1DataContext(connectionString);  
  
    IEnumerable<Product> productQuery =  
    from prod in db.Products  
    where prod.CategoryID == categoryID  
    select prod;  
  
    return productQuery.AsEnumerable();   
}  
```  
  
 <span data-ttu-id="e88c6-130">데이터 컨텍스트 인스턴스는 하나의 "작업 단위" 동안 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-130">An instance of a data context should have a lifetime of one "unit of work."</span></span> <span data-ttu-id="e88c6-131">느슨하게 결합된 환경의 경우 작업 단위는 `SubmitChanges`에 대한 호출 하나가 포함된 낙관적 트랜잭션과 같이 일반적으로 크기가 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-131">In a loosely-coupled environment, a unit of work is typically small, perhaps one optimistic transaction, including a single call to `SubmitChanges`.</span></span> <span data-ttu-id="e88c6-132">이 때문에 데이터 컨텍스트는 메서드 범위에서 만들어지고 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-132">Therefore, the data context is created and disposed at method scope.</span></span> <span data-ttu-id="e88c6-133">작업 단위에 비즈니스 규칙 논리에 대한 호출이 포함된 경우에는 해당 작업 전체 동안 `DataContext` 인스턴스를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-133">If the unit of work includes calls to business rules logic, then generally you will want to keep the `DataContext` instance for that whole operation.</span></span> <span data-ttu-id="e88c6-134">어떤 경우든 `DataContext` 인스턴스는 임의 개수의 트랜잭션에서 장기간 유지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-134">In any case, `DataContext` instances are not intended to be kept alive for long periods of time across arbitrary numbers of transactions.</span></span>  
  
 <span data-ttu-id="e88c6-135">이 메서드는 Product 개체를 반환하고, 각 Product에 연결된 Order_Detail 개체의 컬렉션은 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-135">This method will return Product objects but not the collection of Order_Detail objects that are associated with each Product.</span></span> <span data-ttu-id="e88c6-136"><xref:System.Data.Linq.DataLoadOptions> 개체를 사용하면 이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-136">Use the <xref:System.Data.Linq.DataLoadOptions> object to change this default behavior.</span></span> <span data-ttu-id="e88c6-137">자세한 내용은 참조 [하는 방법: 제어 훨씬 관련 데이터 검색 방법](../../../../../../docs/framework/data/adonet/sql/linq/how-to-control-how-much-related-data-is-retrieved.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-137">For more information, see [How to: Control How Much Related Data Is Retrieved](../../../../../../docs/framework/data/adonet/sql/linq/how-to-control-how-much-related-data-is-retrieved.md).</span></span>  
  
## <a name="inserting-data"></a><span data-ttu-id="e88c6-138">데이터 삽입</span><span class="sxs-lookup"><span data-stu-id="e88c6-138">Inserting Data</span></span>  
 <span data-ttu-id="e88c6-139">새 개체를 삽입할 경우 프레젠테이션 계층에서는 중간 계층 인터페이스에서 관련 메서드를 호출하여 삽입할 새 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-139">To insert a new object, the presentation tier just calls the relevant method on the middle tier interface, and passes in the new object to insert.</span></span> <span data-ttu-id="e88c6-140">경우에 따라서는 클라이언트가 일부 값만 전달하고 중간 계층에서 개체를 직접 만들도록 하는 것이 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-140">In some cases, it may be more efficient for the client to pass in only some values and have the middle tier construct the full object.</span></span>  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="e88c6-141">중간 계층 구현</span><span class="sxs-lookup"><span data-stu-id="e88c6-141">Middle Tier Implementation</span></span>  
 <span data-ttu-id="e88c6-142"><xref:System.Data.Linq.DataContext>가 호출되면 중간 계층에서는 새 <xref:System.Data.Linq.DataContext>를 만들고 <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> 메서드를 사용하여 개체를 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>에 연결한 후 개체를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-142">On the middle tier, a new <xref:System.Data.Linq.DataContext> is created, the object is attached to the <xref:System.Data.Linq.DataContext> by using the <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> method, and the object is inserted when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="e88c6-143">예외, 콜백 및 오류 조건은 다른 모든 웹 서비스 시나리오에서와 동일한 방법으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-143">Exceptions, callbacks, and error conditions can be handled just as in any other Web service scenario.</span></span>  
  
```vb  
' No call to Attach is necessary for inserts.  
Public Sub InsertOrder(ByVal o As Order)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    db.Orders.InsertOnSubmit(o)  
  
    ' Exception handling not shown.  
    db.SubmitChanges()  
  
End Sub  
```  
  
```csharp  
// No call to Attach is necessary for inserts.  
    public void InsertOrder(Order o)  
    {  
        NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
        db.Orders.InsertOnSubmit(o);  
  
        // Exception handling not shown.  
        db.SubmitChanges();  
    }  
```  
  
## <a name="deleting-data"></a><span data-ttu-id="e88c6-144">데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="e88c6-144">Deleting Data</span></span>  
 <span data-ttu-id="e88c6-145">데이터베이스에서 기존 개체를 삭제할 경우 프레젠테이션 계층에서는 중간 계층 인터페이스에서 관련 메서드를 호출하고, 삭제할 개체의 원래 값이 포함된 복사본을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-145">To delete an existing object from the database, the presentation tier calls the relevant method on the middle tier interface, and passes in its copy that includes original values of the object to be deleted.</span></span>  
  
 <span data-ttu-id="e88c6-146">삭제 작업에는 낙관적 동시성 검사가 사용되기 때문에 삭제할 개체를 새 데이터 컨텍스트에 먼저 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-146">Delete operations involve optimistic concurrency checks, and the object to be deleted must first be attached to the new data context.</span></span> <span data-ttu-id="e88c6-147">이 예제에서는 `Boolean` 매개 변수를 `false`로 설정하여 개체에 타임스탬프(RowVersion)가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-147">In this example, the `Boolean` parameter is set to `false` to indicate that the object does not have a timestamp (RowVersion).</span></span> <span data-ttu-id="e88c6-148">그러나 데이터베이스 테이블에서 각 레코드에 대해 타임스탬프를 생성하는 경우 클라이언트측에서는 동시성 검사가 훨씬 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-148">If your database table does generate timestamps for each record, then concurrency checks are much simpler, especially for the client.</span></span> <span data-ttu-id="e88c6-149">즉, 원래 개체 또는 수정된 개체 중 하나를 전달하고 `Boolean` 매개 변수를 `true`로 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-149">Just pass in either the original or modified object and set the `Boolean` parameter to `true`.</span></span> <span data-ttu-id="e88c6-150">그러나 어떤 경우든 중간 계층에서는 일반적으로 <xref:System.Data.Linq.ChangeConflictException>을 catch해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-150">In any case, on the middle tier it is typically necessary to catch the <xref:System.Data.Linq.ChangeConflictException>.</span></span> <span data-ttu-id="e88c6-151">낙관적 동시성 충돌을 처리 하는 방법에 대 한 자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-151">For more information about how to handle optimistic concurrency conflicts, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="e88c6-152">연결된 테이블에 외래 키 제약 조건이 있는 엔터티를 삭제할 경우에는 해당 <xref:System.Data.Linq.EntitySet%601> 컬렉션에 있는 모든 개체를 먼저 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-152">When deleting entities that have foreign key constraints on associated tables, you must first delete all the objects in its <xref:System.Data.Linq.EntitySet%601> collections.</span></span>  
  
```vb  
' Attach is necessary for deletes.  
Public Sub DeleteOrder(ByVal order As Order)  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
  
    db.Orders.Attach(order, False)  
    ' This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order)  
  
    Try  
        ' ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict)  
  
    Catch ex As ChangeConflictException  
        ' Get conflict information, and take actions  
        ' that are appropriate for your application.  
        ' See MSDN Article "How to: Manage Change  
        ' Conflicts (LINQ to SQL).  
  
    End Try  
End Sub  
```  
  
```csharp  
// Attach is necessary for deletes.  
public void DeleteOrder(Order order)  
{  
    NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
  
    db.Orders.Attach(order, false);  
    // This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order);  
    try  
    {  
        // ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict);  
    }  
    catch (ChangeConflictException e)  
    {  
       // Get conflict information, and take actions  
       // that are appropriate for your application.  
       // See MSDN Article How to: Manage Change Conflicts (LINQ to SQL).  
    }  
}  
```  
  
## <a name="updating-data"></a><span data-ttu-id="e88c6-153">데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="e88c6-153">Updating Data</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e88c6-154">은 낙관적 동시성이 사용되는 다음과 같은 시나리오에서 업데이트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-154"> supports updates in these scenarios involving optimistic concurrency:</span></span>  
  
-   <span data-ttu-id="e88c6-155">타임스탬프 또는 RowVersion 번호를 기반으로 하는 낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="e88c6-155">Optimistic concurrency based on timestamps or RowVersion numbers.</span></span>  
  
-   <span data-ttu-id="e88c6-156">엔터티 속성 하위 집합의 원래 값을 기반으로 하는 낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="e88c6-156">Optimistic concurrency based on original values of a subset of entity properties.</span></span>  
  
-   <span data-ttu-id="e88c6-157">원래 엔터티와 수정된 엔터티 모두를 기반으로 하는 낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="e88c6-157">Optimistic concurrency based on the complete original and modified entities.</span></span>  
  
 <span data-ttu-id="e88c6-158">Customer 및 Customer와 연결된 Order 개체의 컬렉션과 같이 엔터티와 해당 관계에 대해 업데이트나 삭제 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-158">You can also perform updates or deletes on an entity together with its relations, for example a Customer and a collection of its associated Order objects.</span></span> <span data-ttu-id="e88c6-159">클라이언트에서 엔터티 개체의 그래프와 해당 자식(`EntitySet`) 컬렉션을 수정할 경우 낙관적 동시성 검사에 원래 값이 필요하면 클라이언트에서는 각 엔터티와 <xref:System.Data.Linq.EntitySet%601> 개체의 원래 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-159">When you make modifications on the client to a graph of entity objects and their child (`EntitySet`) collections, and the optimistic concurrency checks require original values, the client must provide those original values for each entity and <xref:System.Data.Linq.EntitySet%601> object.</span></span> <span data-ttu-id="e88c6-160">클라이언트에서 한 번의 메서드 호출로 관련된 업데이트, 삭제 및 삽입을 수행하려면 각 엔터티에 대해 수행할 작업 유형을 메서드 안에 지정할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-160">If you want to enable clients to make a set of related updates, deletes, and insertions in a single method call, you must provide the client a way to indicate what type of operation to perform on each entity.</span></span> <span data-ttu-id="e88c6-161">그런 다음 <xref:System.Data.Linq.ITable.Attach%2A>를 호출하기 전에 중간 계층에서 적절한 <xref:System.Data.Linq.ITable.InsertOnSubmit%2A> 메서드를 호출한 후 각 엔터티에 대해 <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A>, <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> 또는 `Attach`(삽입의 경우 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>가 필요하지 않음)을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-161">On the middle tier, you then must call the appropriate <xref:System.Data.Linq.ITable.Attach%2A> method and then <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A>, or <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (without `Attach`, for insertions) for each entity before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="e88c6-162">업데이트를 시도하기 전에 원래 값을 가져오기 위한 방법으로 데이터베이스에서 데이터를 검색하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e88c6-162">Do not retrieve data from the database as a way to obtain original values before you try updates.</span></span>  
  
 <span data-ttu-id="e88c6-163">낙관적 동시성에 대 한 자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-163">For more information about optimistic concurrency, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span> <span data-ttu-id="e88c6-164">낙관적 동시성을 해결 하는 방법에 대 한 자세한 정보에 대 한 변경 충돌, 참조 [하는 방법: 관리 변경 충돌](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-164">For detailed information about resolving optimistic concurrency change conflicts, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
 <span data-ttu-id="e88c6-165">다음 예제에서는 각 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-165">The following examples demonstrate each scenario:</span></span>  
  
### <a name="optimistic-concurrency-with-timestamps"></a><span data-ttu-id="e88c6-166">타임스탬프를 사용하는 낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="e88c6-166">Optimistic concurrency with timestamps</span></span>  
  
```vb  
' Assume that "customer" has been sent by client.  
' Attach with "true" to say this is a modified entity  
' and it can be checked for optimistic concurrency  
' because it has a column that is marked with the  
' "RowVersion" attribute.  
  
db.Customers.Attach(customer, True)  
  
Try  
    ' Optional: Specify a ConflictMode value  
    ' in call to SubmitChanges.  
    db.SubmitChanges()  
Catch ex As ChangeConflictException  
    ' Handle conflict based on options provided.  
    ' See MSDN article "How to: Manage Change  
    ' Conflicts (LINQ to SQL)".  
End Try  
```  
  
```csharp  
// Assume that "customer" has been sent by client.  
// Attach with "true" to say this is a modified entity  
// and it can be checked for optimistic concurrency because  
//  it has a column that is marked with "RowVersion" attribute  
db.Customers.Attach(customer, true)  
try  
{  
    // Optional: Specify a ConflictMode value  
    // in call to SubmitChanges.  
    db.SubmitChanges();  
}  
catch(ChangeConflictException e)  
{  
    // Handle conflict based on options provided  
    // See MSDN article How to: Manage Change Conflicts (LINQ to SQL).  
}  
```  
  
### <a name="with-subset-of-original-values"></a><span data-ttu-id="e88c6-167">원래 값의 하위 집합을 사용하는 낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="e88c6-167">With Subset of Original Values</span></span>  
 <span data-ttu-id="e88c6-168">이 경우 클라이언트는 serialize된 개체 전체 및 수정될 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-168">In this approach, the client returns the complete serialized object, together with the values to be modified.</span></span>  
  
```vb  
Public Sub UpdateProductInventory(ByVal p As Product, ByVal _  
    unitsInStock As Short?, ByVal unitsOnOrder As Short?)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        ' p is the original unmodified product  
        ' that was obtained from the database.  
        ' The client kept a copy and returns it now.  
        db.Products.Attach(p, False)  
  
        ' Now that the original values are in the data context,  
        ' apply the changes.  
        p.UnitsInStock = unitsInStock  
        p.UnitsOnOrder = unitsOnOrder  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle conflict based on options provided.  
            ' See MSDN article "How to: Manage Change Conflicts  
            ' (LINQ to SQL)".  
        End Try  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInventory(Product p, short? unitsInStock, short? unitsOnOrder)  
{  
    using (NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString))  
    {  
        // p is the original unmodified product  
        // that was obtained from the database.  
        // The client kept a copy and returns it now.  
        db.Products.Attach(p, false);  
  
        // Now that the original values are in the data context, apply the changes.  
        p.UnitsInStock = unitsInStock;  
        p.UnitsOnOrder = unitsOnOrder;  
        try  
        {  
             // Optional: Specify a ConflictMode value  
             // in call to SubmitChanges.  
             db.SubmitChanges();  
        }  
        catch (ChangeConflictException e)  
        {  
            // Handle conflict based on provided options.  
            // See MSDN article How to: Manage Change Conflicts  
            // (LINQ to SQL).  
        }  
    }  
}  
```  
  
### <a name="with-complete-entities"></a><span data-ttu-id="e88c6-169">전체 엔터티를 사용하는 낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="e88c6-169">With Complete Entities</span></span>  
  
```vb  
Public Sub UpdateProductInfo(ByVal newProd As Product, ByVal _  
    originalProd As Product)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        db.Products.Attach(newProd, originalProd)  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle potential change conflicgt in whatever way  
            ' is appropriate for your application.  
            ' For more information, see the MSDN article  
            ' "How to: Manage Change Conflicts (LINQ to  
            ' SQL)".  
        End Try  
  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInfo(Product newProd, Product originalProd)  
{  
     using (NorthwindClasses1DataContext db = new  
        NorthwindClasses1DataContext(connectionString))  
     {  
         db.Products.Attach(newProd, originalProd);  
         try  
         {  
               // Optional: Specify a ConflictMode value  
               // in call to SubmitChanges.  
               db.SubmitChanges();  
         }  
        catch (ChangeConflictException e)  
        {  
            // Handle potential change conflict in whatever way  
            // is appropriate for your application.  
            // For more information, see the MSDN article  
            // How to: Manage Change Conflicts (LINQ to SQL)/  
        }   
    }  
}  
```  
  
 <span data-ttu-id="e88c6-170">컬렉션을 업데이트하려면 <xref:System.Data.Linq.ITable.AttachAll%2A> 대신 `Attach`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-170">To update a collection, call <xref:System.Data.Linq.ITable.AttachAll%2A> instead of `Attach`.</span></span>  
  
### <a name="expected-entity-members"></a><span data-ttu-id="e88c6-171">필요한 엔터티 멤버</span><span class="sxs-lookup"><span data-stu-id="e88c6-171">Expected Entity Members</span></span>  
 <span data-ttu-id="e88c6-172">앞에서 설명한 것처럼 `Attach` 메서드를 호출하기 전에 엔터티 개체의 일부 멤버만 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-172">As stated previously, only certain members of the entity object are required to be set before you call the `Attach` methods.</span></span> <span data-ttu-id="e88c6-173">설정해야 하는 엔터티 멤버는 다음과 같은 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-173">Entity members that are required to be set must fulfill the following criteria:</span></span>  
  
-   <span data-ttu-id="e88c6-174">엔터티 ID의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-174">Be part of the entity’s identity.</span></span>  
  
-   <span data-ttu-id="e88c6-175">수정될 멤버여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-175">Be expected to be modified.</span></span>  
  
-   <span data-ttu-id="e88c6-176">타임스탬프이거나 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성이 `Never` 이외의 값으로 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-176">Be a timestamp or have its <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> attribute set to something besides `Never`.</span></span>  
  
 <span data-ttu-id="e88c6-177">테이블에 낙관적 동시성 검사를 위한 타임스탬프 또는 버전 번호가 사용되는 경우 <xref:System.Data.Linq.ITable.Attach%2A>를 호출하기 전에 이러한 멤버를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-177">If a table uses a timestamp or version number for an optimistic concurrency check, you must set those members before you call <xref:System.Data.Linq.ITable.Attach%2A>.</span></span> <span data-ttu-id="e88c6-178">해당 Column 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 속성이 true로 설정된 멤버는 낙관적 동시성 검사에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-178">A member is dedicated for optimistic concurrency checking when the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property is set to true on that Column attribute.</span></span> <span data-ttu-id="e88c6-179">데이터베이스에 있는 버전 번호 또는 타임스탬프 값이 동일해야 요청된 업데이트가 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-179">Any requested updates will be submitted only if the version number or timestamp values are the same on the database.</span></span>  
  
 <span data-ttu-id="e88c6-180"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>가 `Never`로 설정되지 않은 멤버도 낙관적 동시성 검사에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-180">A member is also used in the optimistic concurrency check as long as the member does not have <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> set to `Never`.</span></span> <span data-ttu-id="e88c6-181">다른 값이 지정되지 않은 경우 기본값은 `Always`입니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-181">The default value is `Always` if no other value is specified.</span></span>  
  
 <span data-ttu-id="e88c6-182">이러한 필수 멤버가 하나라도 없으면 <xref:System.Data.Linq.ChangeConflictException>를 호출했을 때 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>("행이 없거나 변경되었습니다.")이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-182">If any one of these required members is missing, a <xref:System.Data.Linq.ChangeConflictException> is thrown during <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Row not found or changed").</span></span>  
  
### <a name="state"></a><span data-ttu-id="e88c6-183">상태</span><span class="sxs-lookup"><span data-stu-id="e88c6-183">State</span></span>  
 <span data-ttu-id="e88c6-184">엔터티 개체를 <xref:System.Data.Linq.DataContext> 인스턴스에 연결하면 개체가 `PossiblyModified` 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-184">After an entity object is attached to the <xref:System.Data.Linq.DataContext> instance, the object is considered to be in the `PossiblyModified` state.</span></span> <span data-ttu-id="e88c6-185">다음과 같은 세 가지 방법을 사용하여 연결된 개체를 강제로 `Modified` 상태로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-185">There are three ways to force an attached object to be considered `Modified`.</span></span>  
  
1.  <span data-ttu-id="e88c6-186">개체를 수정되지 않은 상태로 연결한 다음 필드를 직접 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-186">Attach it as unmodified, and then directly modify the fields.</span></span>  
  
2.  <span data-ttu-id="e88c6-187">개체의 현재 인스턴스와 원래 인스턴스를 사용하는 <xref:System.Data.Linq.Table%601.Attach%2A> 오버로드와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-187">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes current and original object instances.</span></span> <span data-ttu-id="e88c6-188">이렇게 하면 이전 값과 새 값이 변경 추적기에 제공되므로 변경된 필드를 자동으로 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-188">This supplies the change tracker with old and new values so that it will automatically know which fields have changed.</span></span>  
  
3.  <span data-ttu-id="e88c6-189">true로 설정된 두 번째 부울 매개 변수를 사용하는 <xref:System.Data.Linq.Table%601.Attach%2A> 오버로드와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-189">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes a second Boolean parameter (set to true).</span></span> <span data-ttu-id="e88c6-190">이렇게 하면 원래 값을 제공하지 않고도 수정된 개체를 변경 추적기에서 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-190">This will tell the change tracker to consider the object modified without having to supply any original values.</span></span> <span data-ttu-id="e88c6-191">이 방법을 사용하려면 개체에 버전/타임스탬프 필드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-191">In this approach, the object must have a version/timestamp field.</span></span>  
  
 <span data-ttu-id="e88c6-192">자세한 내용은 참조 [개체 상태 및 변경 내용 추적](../../../../../../docs/framework/data/adonet/sql/linq/object-states-and-change-tracking.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-192">For more information, see [Object States and Change-Tracking](../../../../../../docs/framework/data/adonet/sql/linq/object-states-and-change-tracking.md).</span></span>  
  
 <span data-ttu-id="e88c6-193">연결하려는 개체와 ID가 동일한 엔터티 개체가 ID 캐시에 이미 있으면 <xref:System.Data.Linq.DuplicateKeyException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-193">If an entity object already occurs in the ID Cache with the same identity as the object being attached, a <xref:System.Data.Linq.DuplicateKeyException> is thrown.</span></span>  
  
 <span data-ttu-id="e88c6-194">개체의 `IEnumerable` 집합과 연결하면 기존 키가 있을 경우 <xref:System.Data.Linq.DuplicateKeyException>이 throw되고</span><span class="sxs-lookup"><span data-stu-id="e88c6-194">When you attach with an `IEnumerable` set of objects, a <xref:System.Data.Linq.DuplicateKeyException> is thrown when an already existing key is present.</span></span> <span data-ttu-id="e88c6-195">나머지 개체는 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88c6-195">Remaining objects are not attached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88c6-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e88c6-196">See Also</span></span>  
 [<span data-ttu-id="e88c6-197">LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e88c6-197">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [<span data-ttu-id="e88c6-198">배경 정보</span><span class="sxs-lookup"><span data-stu-id="e88c6-198">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
