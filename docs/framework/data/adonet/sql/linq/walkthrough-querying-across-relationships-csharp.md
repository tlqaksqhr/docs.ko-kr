---
title: "연습: 관계 간 쿼리(C#)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 61586b8d556a9edccace25b75ceb2696ec675dd3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-querying-across-relationships-c"></a><span data-ttu-id="467eb-102">연습: 관계 간 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="467eb-102">Walkthrough: Querying Across Relationships (C#)</span></span>
<span data-ttu-id="467eb-103">이 연습에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *연결* 데이터베이스에서 외래 키 관계를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="467eb-104">이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-104">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="467eb-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="467eb-105">Prerequisites</span></span>  
 <span data-ttu-id="467eb-106">완료 해야 [연습: 간단한 개체 모델 및 쿼리 (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-106">You must have completed [Walkthrough: Simple Object Model and Query (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md).</span></span> <span data-ttu-id="467eb-107">이 연습은 c:\linqtest5에 있는 northwnd.mdf 파일을 비롯하여 해당 개체 모델 및 쿼리를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest5.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="467eb-108">개요</span><span class="sxs-lookup"><span data-stu-id="467eb-108">Overview</span></span>  
 <span data-ttu-id="467eb-109">이 연습은 다음과 같은 세 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-109">This walkthrough consists of three main tasks:</span></span>  
  
-   <span data-ttu-id="467eb-110">Northwind 샘플 데이터베이스의 Orders 테이블을 나타내는 엔터티 클래스 추가</span><span class="sxs-lookup"><span data-stu-id="467eb-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
-   <span data-ttu-id="467eb-111">`Customer` 및 `Customer` 클래스 간의 관계를 향상시키기 위해 `Order` 클래스에 주석 추가</span><span class="sxs-lookup"><span data-stu-id="467eb-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
-   <span data-ttu-id="467eb-112">`Order` 클래스를 사용하여 `Customer` 정보 가져오기를 테스트하는 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="467eb-112">Creating and running a query to test obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="467eb-113">테이블 간 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="467eb-113">Mapping Relationships Across Tables</span></span>  
 <span data-ttu-id="467eb-114">`Customer` 클래스 정의 후에 `Order`가 외래 키로 `Order.Customer`에 관련된다는 것을 나타내는 다음 코드가 포함된 `Customer.CustomerID` 엔터티 클래스 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Order.Customer` relates as a foreign key to `Customer.CustomerID`.</span></span>  
  
#### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="467eb-115">Order 엔터티 클래스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="467eb-115">To add the Order entity class</span></span>  
  
-   <span data-ttu-id="467eb-116">`Customer` 클래스 뒤에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="467eb-117">Customer 클래스에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="467eb-117">Annotating the Customer Class</span></span>  
 <span data-ttu-id="467eb-118">이 단계에서는 `Customer` 클래스에 대한 관계를 나타내기 위해 `Order` 클래스에 주석을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="467eb-119">어느 방향으로든 관계를 정의하여 링크를 충분히 만들 수 있으므로 이 추가 작업이 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="467eb-120">그러나 이 주석을 추가하면 어느 방향으로나 개체를 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
#### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="467eb-121">Customer 클래스에 주석을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="467eb-121">To annotate the Customer class</span></span>  
  
-   <span data-ttu-id="467eb-122">`Customer` 클래스에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="467eb-123">Customer 및 Order 관계에서 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="467eb-123">Creating and Running a Query Across the Customer-Order Relationship</span></span>  
 <span data-ttu-id="467eb-124">이제 `Order` 개체에서 `Customer` 개체를 직접 액세스하거나 그 반대 방향으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="467eb-125">명시적 필요가 *조인* customers와 orders 합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="467eb-126">Customer 개체를 사용하여 Order 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="467eb-126">To access Order objects by using Customer objects</span></span>  
  
1.  <span data-ttu-id="467eb-127">다음 코드를 `Main` 메서드에 입력하거나 붙여넣어 이 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-127">Modify the `Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2.  <span data-ttu-id="467eb-128">F5 키를 눌러 응용 프로그램을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-128">Press F5 to debug your application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="467eb-129">`db.Log = Console.Out;`을 주석으로 처리하여 콘솔 창에서 SQL 코드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-129">You can eliminate the SQL code in the Console window by commenting out `db.Log = Console.Out;`.</span></span>  
  
3.  <span data-ttu-id="467eb-130">콘솔 창에서 Enter 키를 눌러 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-130">Press Enter in the Console window to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="467eb-131">강력한 형식의 데이터베이스 뷰 만들기</span><span class="sxs-lookup"><span data-stu-id="467eb-131">Creating a Strongly Typed View of Your Database</span></span>  
 <span data-ttu-id="467eb-132">강력한 형식의 데이터베이스 뷰로 작업을 시작하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="467eb-133"><xref:System.Data.Linq.DataContext> 개체를 강력한 형식으로 설정하면 <xref:System.Data.Linq.DataContext.GetTable%2A> 호출이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="467eb-134">강력한 형식의 <xref:System.Data.Linq.DataContext> 개체를 사용할 경우 모든 쿼리에서 강력한 형식의 테이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="467eb-135">다음 단계에서는 `Customers`를 데이터베이스의 Customers 테이블에 매핑되는 강력한 형식의 테이블로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
#### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="467eb-136">DataContext 개체를 강력한 형식으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="467eb-136">To strongly type the DataContext object</span></span>  
  
1.  <span data-ttu-id="467eb-137">`Customer` 클래스 선언 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2.  <span data-ttu-id="467eb-138">다음과 같이 강력한 형식의 `Main`를 사용하도록 <xref:System.Data.Linq.DataContext> 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-138">Modify the `Main` method to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3.  <span data-ttu-id="467eb-139">F5 키를 눌러 응용 프로그램을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="467eb-140">콘솔 창 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4.  <span data-ttu-id="467eb-141">콘솔 창에서 Enter 키를 눌러 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-141">Press Enter in the console window to stop debugging.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="467eb-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="467eb-142">Next Steps</span></span>  
 <span data-ttu-id="467eb-143">다음 연습 ([연습: 데이터 조작 (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)) 데이터를 조작 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-143">The next walkthrough ([Walkthrough: Manipulating Data (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="467eb-144">다음 연습에서는 이미 완료한 이 시리즈의 연습 두 개를 저장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="467eb-144">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467eb-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="467eb-145">See Also</span></span>  
 [<span data-ttu-id="467eb-146">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="467eb-146">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
