---
title: "연습: 관계 간 쿼리(Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: a7da43e3-769f-4e07-bcd6-552b8bde66f4
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 05ae619a4d3a31c83a740572eae13fe7ef883a40
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-querying-across-relationships-visual-basic"></a><span data-ttu-id="dfb73-102">연습: 관계 간 쿼리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfb73-102">Walkthrough: Querying Across Relationships (Visual Basic)</span></span>
<span data-ttu-id="dfb73-103">이 연습에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *연결* 데이터베이스에서 외래 키 관계를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="dfb73-104">이 연습은 Visual Basic 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-104">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dfb73-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dfb73-105">Prerequisites</span></span>  
 <span data-ttu-id="dfb73-106">완료 해야 [연습: 간단한 개체 모델 및 쿼리 (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-106">You must have completed [Walkthrough: Simple Object Model and Query (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md).</span></span> <span data-ttu-id="dfb73-107">이 연습은 c:\linqtest에 있는 northwnd.mdf 파일을 비롯하여 해당 연습의 단순 개체 모델 및 쿼리를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="dfb73-108">개요</span><span class="sxs-lookup"><span data-stu-id="dfb73-108">Overview</span></span>  
 <span data-ttu-id="dfb73-109">이 연습은 다음과 같은 세 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-109">This walkthrough consists of three main tasks:</span></span>  
  
-   <span data-ttu-id="dfb73-110">Northwind 샘플 데이터베이스의 Orders 테이블을 나타내는 엔터티 클래스 추가</span><span class="sxs-lookup"><span data-stu-id="dfb73-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
-   <span data-ttu-id="dfb73-111">`Customer` 및 `Customer` 클래스 간의 관계를 향상시키기 위해 `Order` 클래스에 주석 추가</span><span class="sxs-lookup"><span data-stu-id="dfb73-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
-   <span data-ttu-id="dfb73-112">`Order` 클래스를 사용하여 `Customer` 정보를 가져오는 과정을 테스트하는 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="dfb73-112">Creating and running a query to test the process of obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="dfb73-113">테이블 간 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="dfb73-113">Mapping Relationships across Tables</span></span>  
 <span data-ttu-id="dfb73-114">`Customer` 클래스 정의 후에 `Order`가 외래 키로 `Orders.Customer`에 관련된다는 것을 나타내는 다음 코드가 포함된 `Customers.CustomerID` 엔터티 클래스 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Orders.Customer` relates as a foreign key to `Customers.CustomerID`.</span></span>  
  
#### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="dfb73-115">Order 엔터티 클래스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="dfb73-115">To add the Order entity class</span></span>  
  
-   <span data-ttu-id="dfb73-116">`Customer` 클래스 뒤에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="dfb73-117">Customer 클래스에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="dfb73-117">Annotating the Customer Class</span></span>  
 <span data-ttu-id="dfb73-118">이 단계에서는 `Customer` 클래스에 대한 관계를 나타내기 위해 `Order` 클래스에 주석을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="dfb73-119">어느 방향으로든 관계를 정의하여 링크를 충분히 만들 수 있으므로 이 추가 작업이 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="dfb73-120">그러나 이 주석을 추가하면 어느 방향으로나 개체를 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
#### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="dfb73-121">Customer 클래스에 주석을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="dfb73-121">To annotate the Customer class</span></span>  
  
-   <span data-ttu-id="dfb73-122">`Customer` 클래스에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="dfb73-123">Customer 및 Order 관계에서 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="dfb73-123">Creating and Running a Query across the Customer-Order Relationship</span></span>  
 <span data-ttu-id="dfb73-124">이제 `Order` 개체에서 `Customer` 개체를 직접 액세스하거나 그 반대 방향으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="dfb73-125">명시적 필요가 *조인* customers와 orders 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="dfb73-126">Customer 개체를 사용하여 Order 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="dfb73-126">To access Order objects by using Customer objects</span></span>  
  
1.  <span data-ttu-id="dfb73-127">다음 코드를 `Sub Main` 메서드에 입력하거나 붙여넣어 이 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-127">Modify the `Sub Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-vb[DLinqWalk2VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#3)]  
  
2.  <span data-ttu-id="dfb73-128">F5 키를 눌러 응용 프로그램을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-128">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="dfb73-129">두 이름이 메시지 상자에 표시되며 콘솔 창에는 생성된 SQL 코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-129">Two names appear in the message box, and the Console window shows the generated SQL code.</span></span>  
  
3.  <span data-ttu-id="dfb73-130">메시지 상자를 닫아 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-130">Close the message box to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="dfb73-131">강력한 형식의 데이터베이스 뷰 만들기</span><span class="sxs-lookup"><span data-stu-id="dfb73-131">Creating a Strongly Typed View of Your Database</span></span>  
 <span data-ttu-id="dfb73-132">강력한 형식의 데이터베이스 뷰로 작업을 시작하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="dfb73-133"><xref:System.Data.Linq.DataContext> 개체를 강력한 형식으로 설정하면 <xref:System.Data.Linq.DataContext.GetTable%2A> 호출이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="dfb73-134">강력한 형식의 <xref:System.Data.Linq.DataContext> 개체를 사용할 경우 모든 쿼리에서 강력한 형식의 테이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="dfb73-135">다음 단계에서는 `Customers`를 데이터베이스의 Customers 테이블에 매핑되는 강력한 형식의 테이블로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
#### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="dfb73-136">DataContext 개체를 강력한 형식으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="dfb73-136">To strongly type the DataContext object</span></span>  
  
1.  <span data-ttu-id="dfb73-137">`Customer` 클래스 선언 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-vb[DLinqWalk2VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#4)]  
  
2.  <span data-ttu-id="dfb73-138">다음과 같이 강력한 형식의 `Sub Main`를 사용하도록 <xref:System.Data.Linq.DataContext>을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-138">Modify `Sub Main` to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-vb[DLinqWalk2VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#5)]  
  
3.  <span data-ttu-id="dfb73-139">F5 키를 눌러 응용 프로그램을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="dfb73-140">콘솔 창 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4.  <span data-ttu-id="dfb73-141">콘솔 창에서 Enter 키를 눌러 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-141">Press Enter in the Console window to close the application.</span></span>  
  
5.  <span data-ttu-id="dfb73-142">에 **파일** 메뉴를 클릭 하 여 **모두 저장** 이 응용 프로그램을 저장 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="dfb73-142">On the **File** menu, click **Save All** if you want to save this application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dfb73-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dfb73-143">Next Steps</span></span>  
 <span data-ttu-id="dfb73-144">다음 연습 ([연습: 데이터 조작 (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)) 데이터를 조작 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-144">The next walkthrough ([Walkthrough: Manipulating Data (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="dfb73-145">다음 연습에서는 이미 완료한 이 시리즈의 연습 두 개를 저장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb73-145">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb73-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfb73-146">See Also</span></span>  
 [<span data-ttu-id="dfb73-147">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="dfb73-147">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
