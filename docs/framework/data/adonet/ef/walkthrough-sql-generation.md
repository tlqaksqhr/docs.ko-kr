---
title: "연습: SQL 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c38aaa-9927-4f3c-ab0f-81636cce57a3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8c19c459bf3b62b7e1d7e2917e09717c246e728c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-sql-generation"></a><span data-ttu-id="acbd3-102">연습: SQL 생성</span><span class="sxs-lookup"><span data-stu-id="acbd3-102">Walkthrough: SQL Generation</span></span>
<span data-ttu-id="acbd3-103">이 항목에서는에서 SQL 생성이 생기는 [샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616)합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-103">This topic illustrates how SQL generation occurs in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616).</span></span> <span data-ttu-id="acbd3-104">다음 Entity SQL 쿼리는 샘플 공급자에 포함된 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-104">The following Entity SQL query uses the model that is included with the sample provider:</span></span>  
  
```  
SELECT  j1.ProductId, j1.ProductName, j1.CategoryName, j2.ShipCountry, j2.ProductId  
FROM (  SELECT P.ProductName, P.ProductId, P.Category.CategoryName  
        FROM NorthwindEntities.Products AS P) as j1  
INNER JOIN (SELECT OD.ProductId, OD.Order.ShipCountry as ShipCountry  
            FROM NorthwindEntities.OrderDetails AS OD) as j2  
            ON j1.ProductId == j2.ProductId   
```  
  
 <span data-ttu-id="acbd3-105">이 쿼리는 공급자에 전달되는 다음 출력 명령 트리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-105">The query produces the following output command tree that is passed to the provider:</span></span>  
  
```  
DbQueryCommandTree  
|_Parameters  
|_Query : Collection{Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]}  
  |_Project  
    |_Input : 'Join4'  
    | |_InnerJoin  
    |   |_Left : 'Join1'  
    |   | |_LeftOuterJoin  
    |   |   |_Left : 'Extent1'  
    |   |   | |_Scan : dbo.Products  
    |   |   |_Right : 'Extent2'  
    |   |   | |_Scan : dbo.Categories  
    |   |   |_JoinCondition  
    |   |     |_  
    |   |       |_Var(Extent1).CategoryID  
    |   |       |_=  
    |   |       |_Var(Extent2).CategoryID  
    |   |_Right : 'Join3'  
    |   | |_LeftOuterJoin  
    |   |   |_Left : 'Extent3'  
    |   |   | |_Scan : dbo.OrderDetails  
    |   |   |_Right : 'Join2'  
    |   |   | |_LeftOuterJoin  
    |   |   |   |_Left : 'Extent4'  
    |   |   |   | |_Scan : dbo.Orders  
    |   |   |   |_Right : 'Extent5'  
    |   |   |   | |_Scan : dbo.InternationalOrders  
    |   |   |   |_JoinCondition  
    |   |   |     |_  
    |   |   |       |_Var(Extent4).OrderID  
    |   |   |       |_=  
    |   |   |       |_Var(Extent5).OrderID  
    |   |   |_JoinCondition  
    |   |     |_  
    |   |       |_Var(Extent3).OrderID  
    |   |       |_=  
    |   |       |_Var(Join2).Extent4.OrderID  
    |   |_JoinCondition  
    |     |_  
    |       |_Var(Join1).Extent1.ProductID  
    |       |_=  
    |       |_Var(Join3).Extent3.ProductID  
    |_Projection  
      |_NewInstance : Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]  
        |_Column : 'C1'  
        | |_1  
        |_Column : 'ProductID'  
        | |_Var(Join4).Join1.Extent1.ProductID  
        |_Column : 'ProductName'  
        | |_Var(Join4).Join1.Extent1.ProductName  
        |_Column : 'CategoryName'  
        | |_Var(Join4).Join1.Extent2.CategoryName  
        |_Column : 'ShipCountry'  
        | |_Var(Join4).Join3.Join2.Extent4.ShipCountry  
        |_Column : 'ProductID1'  
          |_Var(Join4).Join3.Extent3.ProductID  
```  
  
 <span data-ttu-id="acbd3-106">이 항목에서는 이 출력 명령 트리를 다음 SQL 문으로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-106">This topic describes how to translate this output command tree into the following SQL statements.</span></span>  
  
```  
SELECT   
1 AS [C1],   
[Extent1].[ProductID] AS [ProductID],   
[Extent1].[ProductName] AS [ProductName],   
[Extent2].[CategoryName] AS [CategoryName],   
[Join3].[ShipCountry] AS [ShipCountry],   
[Join3].[ProductID] AS [ProductID1]  
FROM   [dbo].[Products] AS [Extent1]  
LEFT OUTER JOIN [dbo].[Categories] AS [Extent2] ON [Extent1].[CategoryID] = [Extent2].[CategoryID]  
INNER JOIN    
(SELECT [Extent3].[OrderID] AS [OrderID1], [Extent3].[ProductID] AS [ProductID], [Extent3].[UnitPrice] AS [UnitPrice], [Extent3].[Quantity] AS [Quantity], [Extent3].[Discount] AS [Discount], [Join2].[OrderID2], [Join2].[CustomerID], [Join2].[EmployeeID], [Join2].[OrderDate], [Join2].[RequiredDate], [Join2].[ShippedDate], [Join2].[Freight], [Join2].[ShipName], [Join2].[ShipAddress], [Join2].[ShipCity], [Join2].[ShipRegion], [Join2].[ShipPostalCode], [Join2].[ShipCountry], [Join2].[OrderID3], [Join2].[CustomsDescription], [Join2].[ExciseTax]  
FROM  [dbo].[OrderDetails] AS [Extent3]  
LEFT OUTER JOIN    
      (SELECT [Extent4].[OrderID] AS [OrderID2], [Extent4].[CustomerID] AS [CustomerID], [Extent4].[EmployeeID] AS [EmployeeID], [Extent4].[OrderDate] AS [OrderDate], [Extent4].[RequiredDate] AS [RequiredDate], [Extent4].[ShippedDate] AS [ShippedDate], [Extent4].[Freight] AS [Freight], [Extent4].[ShipName] AS [ShipName], [Extent4].[ShipAddress] AS [ShipAddress], [Extent4].[ShipCity] AS [ShipCity], [Extent4].[ShipRegion] AS [ShipRegion], [Extent4].[ShipPostalCode] AS [ShipPostalCode], [Extent4].[ShipCountry] AS [ShipCountry], [Extent5].[OrderID] AS [OrderID3], [Extent5].[CustomsDescription] AS [CustomsDescription], [Extent5].[ExciseTax] AS [ExciseTax]  
FROM  [dbo].[Orders] AS [Extent4]  
LEFT OUTER JOIN [dbo].[InternationalOrders] AS [Extent5] ON [Extent4].[OrderID] = [Extent5].[OrderID]   
      ) AS [Join2] ON [Extent3].[OrderID] = [Join2].[OrderID2]   
   ) AS [Join3] ON [Extent1].[ProductID] = [Join3].[ProductID]  
```  
  
## <a name="first-phase-of-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="acbd3-107">SQL 생성의 첫 번째 단계: 식 트리 방문</span><span class="sxs-lookup"><span data-stu-id="acbd3-107">First Phase of SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="acbd3-108">다음 그림에서는 방문자의 비어 있는 초기 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-108">The following figure illustrates the initial empty state of the visitor.</span></span>  <span data-ttu-id="acbd3-109">이 항목 전반에서는 연습에 대한 설명과 관련된 속성만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-109">Throughout this topic, only the properties relevant to the walkthrough explanation are shown.</span></span>  
  
 <span data-ttu-id="acbd3-110">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span><span class="sxs-lookup"><span data-stu-id="acbd3-110">![Diagram](../../../../../docs/framework/data/adonet/ef/media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span></span>  
  
 <span data-ttu-id="acbd3-111">Project 노드를 방문하면 VisitInputExpression이 입력(Join4)을 통해 호출되어 VisitJoinExpression 메서드에 의한 Join4의 방문을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-111">When the Project  node is visited, VisitInputExpression is called over its input (Join4), which triggers the visit of Join4 by the method VisitJoinExpression.</span></span> <span data-ttu-id="acbd3-112">Join4가 맨 위의 조인이기 때문에 IsParentAJoin은 false를 반환하고 새 SqlSelectStatement(SelectStatement0)가 만들어져 SELECT 문 스택에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-112">Because this is a topmost join, IsParentAJoin returns false and a new SqlSelectStatement (SelectStatement0) is created and pushed on the SELECT statement stack.</span></span> <span data-ttu-id="acbd3-113">또한 새 범위(scope0)가 기호 테이블에 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-113">Also, a new scope (scope0) is entered in the symbol table.</span></span> <span data-ttu-id="acbd3-114">조인의 첫 번째(왼쪽) 입력을 방문하기 전에 'true'가 IsParentAJoin 스택에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-114">Before the first (left) input of the join is visited, 'true' is pushed on the IsParentAJoin stack.</span></span> <span data-ttu-id="acbd3-115">Join4의 왼쪽 입력인 Join1을 방문하기 직전의 방문자의 상태가 다음 그림에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-115">Right before Join1, which is the left input of Join4, is visited, the state of the visitor is as shown in the next figure.</span></span>  
  
 <span data-ttu-id="acbd3-116">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span><span class="sxs-lookup"><span data-stu-id="acbd3-116">![Diagram](../../../../../docs/framework/data/adonet/ef/media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span></span>  
  
 <span data-ttu-id="acbd3-117">조인 방문 메서드가 Join4를 통해 호출되면 IsParentAJoin이 true이므로 현재 SELECT 문인 SelectStatement0를 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-117">When the join visit method is invoked over Join4, IsParentAJoin is true, thus it reuses the current select statement SelectStatement0.</span></span> <span data-ttu-id="acbd3-118">새 범위(scope1)가 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-118">A new scope is entered (scope1).</span></span> <span data-ttu-id="acbd3-119">왼쪽 자식인 Extent1을 방문하기 전에 또 다른 true가 IsParentAJoin 스택에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-119">Before visiting its left child, Extent1, another true is pushed on the IsParentAJoin stack.</span></span>  
  
 <span data-ttu-id="acbd3-120">Extent1을 방문하면 IsParentAJoin이 true를 반환하기 때문에 "[dbo].[Products]"가 포함된 SqlBuilder가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-120">When Extent1 is visited, because IsParentAJoin returns true, it returns a SqlBuilder containing "[dbo].[Products]".</span></span> <span data-ttu-id="acbd3-121">Join4를 방문하는 메서드로 제어가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-121">The control returns to the method visiting Join4.</span></span> <span data-ttu-id="acbd3-122">항목이 IsParentAJoin에서 제공되며, ProcessJoinInputResult가 호출되어 방문하는 Extent1의 결과를 SelectStatement0의 FROM 절에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-122">An entry is popped from IsParentAJoin, and ProcessJoinInputResult is called, which appends the result of visiting Extent1 to the From clause of SelectStatement0.</span></span> <span data-ttu-id="acbd3-123">입력 바인딩 이름 "Extent1"에 대한 새로운 기호 symbol_Extent1이 만들어져 SelectStatement0의 FromExtents에 추가되며, "As" 및 symbol_Extent1도 FROM 절에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-123">A new from symbol, symbol_Extent1, for the input binding name "Extent1" is created, added to the FromExtents of SelectStatement0, and also "As" and  symbol_Extent1 are appended to the from clause.</span></span> <span data-ttu-id="acbd3-124">"Extent1"에 대한 AllExtentNames에 값이 0인 새 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-124">A new entry is added to AllExtentNames for "Extent1" with the value of 0.</span></span> <span data-ttu-id="acbd3-125">"Extent1"을 symbol_Extent1 기호와 연결하기 위해 기호 테이블의 현재 범위에 새 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-125">A new entry is added to the current scope in the symbol table to associate "Extent1" with its symbol symbol_Extent1.</span></span> <span data-ttu-id="acbd3-126">또한 symbol_Extent1이 SqlSelectStatement의 AllJoinExtents에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-126">Symbol_Extent1 is also added to the AllJoinExtents of the SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="acbd3-127">Join1의 오른쪽 입력을 방문하기 전에 "LEFT OUTER JOIN"이 SelectStatement0의 FROM 절에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-127">Before the right input of Join1 is visited, "LEFT OUTER JOIN" is added to the From clause of SelectStatement0.</span></span> <span data-ttu-id="acbd3-128">오른쪽 입력이 Scan 식이기 때문에 true가 다시 IsParentAJoin 스택에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-128">Because the right input is a Scan expression, true is again pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="acbd3-129">오른쪽 입력을 방문하기 전의 상태가 다음 그림에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-129">The state before visiting the right input as shown in the next figure.</span></span>  
  
 <span data-ttu-id="acbd3-130">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span><span class="sxs-lookup"><span data-stu-id="acbd3-130">![Diagram](../../../../../docs/framework/data/adonet/ef/media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span></span>  
  
 <span data-ttu-id="acbd3-131">오른쪽 입력은 왼쪽 입력과 동일한 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-131">The right input is processed in the same way as the left input.</span></span> <span data-ttu-id="acbd3-132">오른쪽 입력을 방문한 후의 상태가 다음 그림에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-132">The state after visiting the right input is shown in the next figure.</span></span>  
  
 <span data-ttu-id="acbd3-133">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span><span class="sxs-lookup"><span data-stu-id="acbd3-133">![Diagram](../../../../../docs/framework/data/adonet/ef/media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span></span>  
  
 <span data-ttu-id="acbd3-134">다음으로, "false"가 IsParentAJoin 스택에 제공되고 조인 조건 Var(Extent1).CategoryID == Var(Extent2).CategoryID가 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-134">Next "false" is pushed on the IsParentAJoin stack and the join condition Var(Extent1).CategoryID == Var(Extent2).CategoryID is processed.</span></span> <span data-ttu-id="acbd3-135">기호 테이블에서 조회한 후 Var(Extenent1)이 <symbol_Extent1>로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-135">Var(Extenent1) is resolved to <symbol_Extent1> after a look up in the symbol table.</span></span> <span data-ttu-id="acbd3-136">인스턴스가 단순한 기호로 Var(Extent1) 처리 한 결과로으로 확인 되므로 합니다. CategoryID과 함께 SqlBuilder \<symbol1 >. " CategoryID "가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-136">Because the instance is resolved to a simple Symbol, as a result of processing Var(Extent1).CategoryID, a SqlBuilder with \<symbol1>."CategoryID" is returned.</span></span> <span data-ttu-id="acbd3-137">마찬가지로 비교의 다른 쪽이 처리되며, 조인 조건을 방문한 결과가 SelectStatement1의 FROM 절에 추가되고 "false" 값이 IsParentAJoin 스택에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-137">Similarly the other side of the comparison is processed, and the result of visiting the join condition is appended to the FROM clause of SelectStatement1 and the value "false" is popped from the IsParentAJoin stack.</span></span>  
  
 <span data-ttu-id="acbd3-138">이를 통해 Join1이 완전히 처리되었으며 범위가 기호 테이블에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-138">With this, Join1 has completely been processed, and a scope is popped from the symbol table.</span></span>  
  
 <span data-ttu-id="acbd3-139">Join1의 부모인 Join4의 처리로 제어가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-139">Control returns to processing Join4, the parent of Join1.</span></span> <span data-ttu-id="acbd3-140">자식이 SELECT 문을 다시 사용했기 때문에 Join1 익스텐트가 단일 조인 기호 <joinSymbol_Join1>로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-140">Because the child reused the Select statement, the Join1 extents are replaced with a single Join symbol <joinSymbol_Join1>.</span></span> <span data-ttu-id="acbd3-141">또한 Join1을 <joinSymbol_Join1>과 연결하기 위해 기호 테이블에 새 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-141">Also a new entry is added to the symbol table to associate Join1 with <joinSymbol_Join1>.</span></span>  
  
 <span data-ttu-id="acbd3-142">처리할 다음 노드는 Join4의 두 번째 자식인 Join3입니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-142">The next node to be processed is Join3, the second child of Join4.</span></span> <span data-ttu-id="acbd3-143">Join3이 오른쪽 자식이므로 "false"가 IsParentAJoin 스택에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-143">As it is a right child, "false" is pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="acbd3-144">이 시점에서 방문자의 상태가 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-144">The state of the visitor at this point is illustrated in the next figure.</span></span>  
  
 <span data-ttu-id="acbd3-145">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span><span class="sxs-lookup"><span data-stu-id="acbd3-145">![Diagram](../../../../../docs/framework/data/adonet/ef/media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span></span>  
  
 <span data-ttu-id="acbd3-146">Join3에 대해 IsParentAJoin은 false를 반환하고 새 SqlSelectStatement(SelectStatement1)를 시작하여 스택에 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-146">For Join3, IsParentAJoin returns false and needs to start a new SqlSelectStatement (SelectStatement1) and push it on the stack.</span></span> <span data-ttu-id="acbd3-147">이전의 조인을 처리할 때와 마찬가지로 처리가 계속되며 새 범위가 스택에 제공되고 자식이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-147">Processing continues as it did with the previous the previous joins, a new scope is pushed on the stack and the children are processed.</span></span> <span data-ttu-id="acbd3-148">왼쪽 자식이 익스텐트(Extent3)이고 오른쪽 자식이 조인(Join2)이며, 이 오른쪽 자식 역시 새 SqlSelectStatement(SelectStatement2)를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-148">The left child is an Extent (Extent3) and the right child is a join (Join2) which also needs to start a new SqlSelectStatement: SelectStatement2.</span></span> <span data-ttu-id="acbd3-149">Join2의 자식도 익스텐트이며 SelectStatement2로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-149">The children on Join2 are Extents as well and are aggregated into SelectStatement2.</span></span>  
  
 <span data-ttu-id="acbd3-150">Join2를 방문한 직후, 사후 처리(ProcessJoinInputResult)가 수행되기 전의 방문자의 상태가 다음 그림에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-150">The state of the visitor right after Join2 is visited, but before its post-processing (ProcessJoinInputResult) is done is shown in the next figure:</span></span>  
  
 <span data-ttu-id="acbd3-151">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span><span class="sxs-lookup"><span data-stu-id="acbd3-151">![Diagram](../../../../../docs/framework/data/adonet/ef/media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span></span>  
  
 <span data-ttu-id="acbd3-152">위의 그림에서 SelectStatement2는 스택에서 제공되었지만 아직 부모에 의해 사후 처리되지 않았기 때문에 자유 부동으로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-152">In the previous figure, SelectStatement2 is shown as free floating because it was popped out of the stack, but not yet post processed by the parent.</span></span> <span data-ttu-id="acbd3-153">SelectStatement2는 부모의 FROM 부분에 추가되어야 하지만 SELECT 절이 없으면 완전한 SQL 문이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-153">It needs to be added to the FROM part of the parent, but it is not a complete SQL statement without a SELECT clause.</span></span> <span data-ttu-id="acbd3-154">따라서 이 시점에서 기본 열(입력에 의해 생성된 모든 열)이 AddDefaultColumns 메서드에 의해 선택 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-154">So, at this point, the default columns (all the columns produced by its inputs) are added to the select list by the method AddDefaultColumns.</span></span> <span data-ttu-id="acbd3-155">AddDefaultColumns는 FromExtents에서 기호를 반복하여 각 기호에 대해 범위로 가져온 모든 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-155">AddDefaultColumns iterates over the symbols in FromExtents and for each symbol adds all the columns brought in scope.</span></span> <span data-ttu-id="acbd3-156">단순한 기호의 경우 기호 형식을 확인하여 추가할 모든 속성을 검색하고,</span><span class="sxs-lookup"><span data-stu-id="acbd3-156">For a simple symbol, it looks at the symbol type to retrieve all its properties to be added.</span></span> <span data-ttu-id="acbd3-157">AllColumnNames 사전을 열 이름으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-157">It also populates the AllColumnNames dictionary with the column names.</span></span> <span data-ttu-id="acbd3-158">완성된 SelectStatement2가 SelectStatement1의 FROM 절에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-158">The completed SelectStatement2 is appended to the FROM clause of SelectStatement1.</span></span>  
  
 <span data-ttu-id="acbd3-159">다음으로, Join2를 나타내는 새 조인 기호가 만들어집니다. 이 기호는 중첩 조인으로 표시되어 SelectStatement1의 AllJoinExtents에 추가되며 기호 테이블에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-159">Next, a new join symbol is created to represent Join2, it is marked as a nested join and added to the AllJoinExtents of SelectStatement1 and added to the symbol table.</span></span>  <span data-ttu-id="acbd3-160">이제 Join3의 조인 조건인 Var(Extent3).OrderID =  Var(Join2).Extent4.OrderID가 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-160">Now the join condition of Join3, Var(Extent3).OrderID =  Var(Join2).Extent4.OrderID, needs to be processed.</span></span> <span data-ttu-id="acbd3-161">왼쪽 편의 처리는 Join1의 조인 조건과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-161">Processing of the left hand side is similar to the join condition of Join1.</span></span> <span data-ttu-id="acbd3-162">그러나 오른쪽 편인 "Var(Join2).Extent4.OrderID"의 경우 조인 평면화가 필요하기 때문에 다르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-162">However, the processing of the right and side "Var(Join2).Extent4.OrderID" is different because join flattening is required.</span></span>  
  
 <span data-ttu-id="acbd3-163">다음 그림에는 DbPropertyExpression "Var(Join2).Extent4.OrderID"가 처리되기 직전의 방문자의 상태가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-163">The next figure shows the state of the visitor right before the DbPropertyExpression "Var(Join2).Extent4.OrderID" is processed.</span></span>  
  
 <span data-ttu-id="acbd3-164">"Var(Join2).Extent4.OrderID"를 방문하는 방식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-164">Consider how "Var(Join2).Extent4.OrderID" is visited.</span></span> <span data-ttu-id="acbd3-165">먼저, 인스턴스 속성 "Var(Join2).Extent4"를 방문합니다. 이 속성은 또 다른 DbPropertyExpression이며 먼저 해당 인스턴스 "Var(Join2)"를 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-165">First, the instance property "Var(Join2).Extent4" is visited, which is another DbPropertyExpression and first visits its instance "Var(Join2)".</span></span> <span data-ttu-id="acbd3-166">기호 테이블의 맨 위 범위에서 "Join2"가 <joinSymbol_join2>로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-166">In the top most scope in the symbol table, "Join2" resolves to <joinSymbol_join2>.</span></span> <span data-ttu-id="acbd3-167">"Var(Join2).Extent4"를 처리하는 DbPropertyExpression의 방문 메서드에서 인스턴스 방문과 평면화가 필요할 때 조인 기호가 반환되었음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-167">In the visit method for DbPropertyExpression processing "Var(Join2).Extent4" notice that a join symbol was returned when visiting the instance and flattening is required.</span></span>  
  
 <span data-ttu-id="acbd3-168">중첩 조인이므로 조인 기호의 NameToExtent 사전에서 "Extent4" 속성을 조회하여 <symbol_Extent4>로 확인하고 새 기호 쌍(<joinSymbol_join2>, <symbol_Extent4>)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-168">Since it is a nested join, we look up the property "Extent4" in the NameToExtent dictionary of the join symbol, resolve it to <symbol_Extent4> and return a new SymbolPair(<joinSymbol_join2>, <symbol_Extent4>).</span></span> <span data-ttu-id="acbd3-169">기호 쌍이 "Var(Join2).Extent4.OrderID"의 인스턴스 처리에서 반환되므로 "OrderID" 속성이 해당 기호 쌍(<symbol_Extent4>)의 ColumnPart에서 확인됩니다. 여기에는 해당 익스텐트의 열 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-169">Since a symbol pair is returned from the processing of the instance of "Var(Join2).Extent4.OrderID",  the property "OrderID" is resolved from the ColumnPart of that symbol pair (<symbol_Extent4>), which has a list of the columns of the extent it represents.</span></span> <span data-ttu-id="acbd3-170">따라서 "Var(Join2).Extent4.OrderID"는 { <joinSymbol_Join2>, ".", <symbol_OrderID>}로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-170">So, "Var(Join2).Extent4.OrderID" is resolved to { <joinSymbol_Join2>, ".", <symbol_OrderID>}.</span></span>  
  
 <span data-ttu-id="acbd3-171">Join4의 조인 조건은 유사하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-171">The join condition of Join4 is similarly processed.</span></span> <span data-ttu-id="acbd3-172">맨 위의 프로젝트를 처리한 VisitInputExpression 메서드에 제어가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-172">The control returns to the VisitInputExpression method that processed the top most project.</span></span> <span data-ttu-id="acbd3-173">반환된 SelectStatement0의 FromExtents를 살펴보면, 입력이 조인으로 식별되며 원래 익스텐트를 제거하고 조인 기호만 포함된 새 익스텐트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-173">Looking at the FromExtents of the returned SelectStatement0, the input is identified as a join, and removes the original extents and replaces them with a new extent with just the Join symbol.</span></span> <span data-ttu-id="acbd3-174">기호 테이블도 업데이트되고 그 다음으로 Project의 Projection 부분이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-174">The symbol table is also updated and next the projection part of the Project is processed.</span></span> <span data-ttu-id="acbd3-175">속성 확인과 조인 익스텐트 평면화는 앞에서 설명한 바와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-175">The resolving of the properties and the flattening of the join extents is as described earlier.</span></span>  
  
 <span data-ttu-id="acbd3-176">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span><span class="sxs-lookup"><span data-stu-id="acbd3-176">![Diagram](../../../../../docs/framework/data/adonet/ef/media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span></span>  
  
 <span data-ttu-id="acbd3-177">마지막으로 다음 SqlSelectStatement가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-177">Finally, the following SqlSelectStatement is produced:</span></span>  
  
```  
SELECT:   
  "1", " AS ", "[C1]",  
  <symbol_Extent1>, ".", "[ProductID]", " AS ", "[ProductID]",   
  <symbol_Extent1>, ".", "[ProductName]", " AS ", "[ProductName]",  
  <symbol_Extent2>, ".", "[CategoryName]", " AS ", "[CategoryName]",  
  <joinSymbol_Join3>, ".", <symbol_ShipCountry>, " AS ", "[ShipCountry]",   
  <joinSymbol_Join3>, ".", <symbol_ProductID>, " AS ", "[ProductID1]"  
FROM: "[dbo].[Products]", " AS ", <symbol_Extent1>,   
        "LEFT OUTER JOIN ""[dbo].[Categories]", " AS ", <symbol_Extent2>, " ON ", <symbol_Extent1>, ".", "[CategoryID]", " = ", <symbol_Extent2>, ".", "[CategoryID]",   
        "INNER JOIN ",   
        " (", SELECT:   
           <symbol_Extent3>, ".", "[OrderID]", " AS ", <symbol_OrderID>, ",   
              <symbol_Extent3>, ".", "[ProductID]", " AS ", <symbol_ProductID>, ...,  
         <joinSymbol_Join2>, ".", <symbol_OrderID_2>, ", ",   
           <joinSymbol_Join2>, ".", <symbol_CustomerID>, ....,    
        <joinSymbol_Join2>, ".", <symbol_OrderID_3>,   
<joinSymbol_Join2>, ".", <symbol_CustomsDescription>,   
<joinSymbol_Join2>, ".", <symbol_ExciseTax>  
FROM: "[dbo].[OrderDetails]", " AS ", <symbol_Extent3>,   
"LEFT OUTER JOIN ",   
" (", SELECT:   
<symbol_Extent4>, ".", "[OrderID]", " AS ", <symbol_OrderID_2>,   
<symbol_Extent4>, ".", "[CustomerID]", " AS ", <symbol_CustomerID>, ...  
<symbol_Extent5>, ".", "[OrderID]", " AS ", <symbol_OrderID_3>,  
<symbol_Extent5>, ".", "[CustomsDescription]", " AS ", <symbol_CustomsDescription>,  
<symbol_Extent5>, ".", "[ExciseTax]", " AS ", <symbol_ExciseTax>  
FROM: "[dbo].[Orders]", " AS ", <symbol_Extent4>,  
"LEFT OUTER JOIN ", , "[dbo].[InternationalOrders]", " AS ", <symbol_Extent5>,   
" ON ", <symbol_Extent4>, ".", "[OrderID]", " = ", , <symbol_Extent5>, ".", "[OrderID]"  
" )", " AS ", <joinSymbol_Join2>, " ON ", , , <symbol_Extent3>, ".", "[OrderID]", " = ", , <joinSymbol_Join2>, ".", <symbol_OrderID_2>  
" )", " AS ", <joinSymbol_Join3>, " ON ", , , <symbol_Extent1>, ".", "[ProductID]", " = ", , <joinSymbol_Join3>, ".", <symbol_ProductID>  
```  
  
### <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="acbd3-178">SQL 생성의 두 번째 단계: 문자열 명령 생성</span><span class="sxs-lookup"><span data-stu-id="acbd3-178">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="acbd3-179">두 번째 단계에서는 기호의 실제 이름을 생성합니다. 이 경우에는 충돌을 해결해야 하므로 "OrderID"라는 열을 나타내는 기호만 중점적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-179">The second phase produces actual names for the symbols, and we only focus on the symbols representing columns named "OrderID", as in this case a conflict needs to be resolved.</span></span> <span data-ttu-id="acbd3-180">이러한 기호가 SqlSelectStatement에서 강조 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-180">These are highlighted in the SqlSelectStatement.</span></span> <span data-ttu-id="acbd3-181">그림에서 사용된 접미사는 이러한 기호가 서로 다른 인스턴스임을 강조하기 위한 것이며, 새로운 이름을 나타내는 것은 아닙니다. 이 단계에서는 최종 이름(원래 이름과 다를 수 있음)이 아직 할당되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-181">Note that the suffixes used in the figure are only to emphasize that these are different instances, not to represent any new names, as at this stage their final names (possibly different form the original names) have not been assigned yet.</span></span>  
  
 <span data-ttu-id="acbd3-182">이름을 바꿔야 하는 발견된 첫 번째 기호는 <symbol_OrderID>입니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-182">The first symbol found that needs to be renamed is <symbol_OrderID>.</span></span> <span data-ttu-id="acbd3-183">새 이름이 "OrderID1"로 할당됩니다. 1은 "OrderID"에 마지막으로 사용된 접미사로 표시되며 기호는 이름 바꾸기가 필요하지 않은 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-183">Its new name is assigned as "OrderID1", 1 is marked as the last used suffix for "OrderID" and the symbol is marked as not needing renaming.</span></span> <span data-ttu-id="acbd3-184">다음으로, 처음 사용한 <symbol_OrderID_2>가 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-184">Next, the first usage of <symbol_OrderID_2> is found.</span></span> <span data-ttu-id="acbd3-185">이 항목은 사용 가능한 다음 접미사("OrderID2")를 사용하도록 이름이 바뀌며, 또한 다음에 사용될 때 이름이 바뀌지 않도록 이름 바꾸기가 필요하지 않은 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-185">It is renamed to use the next available suffix ("OrderID2") and again marked as not needing renaming, so that next time it is used it does not get renamed.</span></span> <span data-ttu-id="acbd3-186"><symbol_OrderID_3>에 대해서도 동일한 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-186">This is done for <symbol_OrderID_3> too.</span></span>  
  
 <span data-ttu-id="acbd3-187">두 번째 단계가 끝날 때 최종 SQL 문이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="acbd3-187">At the end of the second phase, the final SQL statement is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acbd3-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acbd3-188">See Also</span></span>  
 [<span data-ttu-id="acbd3-189">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="acbd3-189">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
