---
title: 엔터티 활동
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 81f8b1852b939d7ceb8b9afae4435ca12239b880
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="entity-activities"></a><span data-ttu-id="96c83-102">엔터티 활동</span><span class="sxs-lookup"><span data-stu-id="96c83-102">Entity Activities</span></span>
<span data-ttu-id="96c83-103">이 샘플에서는 Windows Workflow Foundation와 ADO.NET Entity Framework를 사용 하 여 데이터 액세스를 단순화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-103">This sample shows how to use the ADO.NET Entity Framework with Windows Workflow Foundation to simplify data access.</span></span>  
  
 <span data-ttu-id="96c83-104">ADO.NET Entity Framework를 사용하면 개발자가 고객, 주문서, 주문 세부 사항 및 이러한 엔터티 사이의 관계 같은 도메인별 개체, 속성 및 관계의 형태로 데이터를 다룰 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-104">The ADO.NET Entity Framework enables developers to work with data in the form of domain-specific objects, properties and relationships such as Customers, Orders, Order Details and the relationships between these entities.</span></span> <span data-ttu-id="96c83-105">이를 위해 ADO.NET Entity Framework에서는 관계형 저장소 스키마에 대해 직접 프로그래밍하는 대신 개념적 응용 프로그램 모델에 대해 프로그래밍할 수 있는 추상화 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-105">The ADO.NET Entity Framework does this by providing a level of abstraction that enables programming against a conceptual application model instead of programming directly against a relational storage schema.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="96c83-106"> ADO.NET Entity Framework 참조 [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549)합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-106"> the ADO.NET Entity Framework see [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="96c83-107">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="96c83-107">Sample details</span></span>  
 <span data-ttu-id="96c83-108">이 샘플에는 `Northwind` 데이터베이스가 사용되며 `Northwind` 데이터베이스를 만들고 제거하기 위한 스크립트(Setup.cmd 및 Cleanup.cmd)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-108">This sample uses the `Northwind` database and includes scripts for creating and removing the `Northwind` database (Setup.cmd and Cleanup.cmd).</span></span> <span data-ttu-id="96c83-109">이 샘플의 프로젝트에는 `Northwind` 데이터베이스를 기반으로 하는 엔터티 데이터 모델이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-109">The projects in this sample include an Entity Data Model based on the `Northwind` database.</span></span> <span data-ttu-id="96c83-110">프로젝트에 포함되어 있는 `Northwind.edmx` 파일을 열면 모델을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-110">You can find the model by opening the `Northwind.edmx` file that is included in the project.</span></span> <span data-ttu-id="96c83-111">이는 ADO.NET Entity Framework를 사용하여 액세스할 수 있는 개체의 모양을 정의하는 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-111">This is the model that defines the shape of the objects that can be accessed using the ADO.NET Entity Framework.</span></span>  
  
 <span data-ttu-id="96c83-112">이 샘플에 포함되어 있는 활동은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-112">The following activities are included in this sample:</span></span>  
  
-   <span data-ttu-id="96c83-113">`EntitySQLQuery`: `EntitySQLQuery` 활동을 사용하면 Entity SQL 쿼리 문자열을 기반으로 데이터베이스에서 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-113">`EntitySQLQuery`: The `EntitySQLQuery` activity allows you to retrieve objects from the database based on an Entity SQL query string.</span></span> <span data-ttu-id="96c83-114">Entity SQL은 SQL과 유사하며 저장소로부터 독립적인 언어입니다. 이를 사용하면 모델이나 도메인의 일부인 엔터티와 개념적 모델을 기반으로 쿼리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-114">Entity SQL is a store independent language that is similar to SQL and it allows you to specify queries based on the conceptual model and the entities that are a part of the model or domain.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="96c83-115"> Entity SQL 언어 참조 [Entity SQL 언어](http://go.microsoft.com/fwlink/?LinkId=165646)합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-115"> Entity SQL Language, see [Entity SQL Language](http://go.microsoft.com/fwlink/?LinkId=165646).</span></span>  
  
-   <span data-ttu-id="96c83-116">`EntityLinqQuery`: 이 활동을 사용하면 LINQ 쿼리나 조건자를 기반으로 데이터베이스에서 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-116">`EntityLinqQuery`: This activity allows you to retrieve objects from the database based on a LINQ query or predicate.</span></span>  
  
-   <span data-ttu-id="96c83-117">`EntityAdd`: `EntityAdd` 활동을 사용하면 엔터티 또는 엔터티 컬렉션을 데이터베이스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-117">`EntityAdd`: The `EntityAdd` activity allows you to add an entity or a collection of entities to the database.</span></span>  
  
-   <span data-ttu-id="96c83-118">`EntityDelete`: `EntityDelete` 활동을 사용하면 엔터티 또는 엔터티 컬렉션을 데이터베이스에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-118">`EntityDelete`: The `EntityDelete` activity allows you to delete an entity or a collection of entities from the database.</span></span>  
  
-   <span data-ttu-id="96c83-119">`ObjectContextScope`: 위에서 언급한 활동들은 이를 포함하는 `ObjectContextScope` 활동 인스턴스 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-119">`ObjectContextScope`: The previously mentioned activities can only be used within a containing `ObjectContextScope` activity instance.</span></span> <span data-ttu-id="96c83-120">`ObjectContextScope` 활동은 데이터베이스에 대한 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-120">The `ObjectContextScope` activity sets up the connection to the database.</span></span> <span data-ttu-id="96c83-121">여기에는 구성 파일 설정을 통해 검색하거나 전달된 연결 문자열이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-121">It requires a connection string (that is either passed in or retrieved using a configuration file setting).</span></span> <span data-ttu-id="96c83-122">`ObjectContextScope` 활동을 사용하면 엔터티에 대한 관련 작업 그룹을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-122">The `ObjectContextScope` activity makes it easy to perform a group of related operations on entities.</span></span> <span data-ttu-id="96c83-123">이 범위에는 활성 연결이 유지되므로 이는 비지속성 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-123">Because this scope maintains an active connection, it is a No Persist scope.</span></span> <span data-ttu-id="96c83-124">또한 `ObjectContextScope` 활동을 끝낼 때는 해당 범위 내에서 엔터티 활동을 사용하여 검색한 개체에 대한 모든 변경 내용이 데이터베이스에 자동으로 다시 전달되며, 개체를 데이터베이스에 다시 저장하기 위해 명시적인 작업이나 후속 작업을 추가로 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-124">In addition, when the `ObjectContextScope` activity exits, any changes that are made to objects retrieved using Entity Activities within that scope automatically get persisted back to the database, and no explicit or subsequent action is required to save objects back to the database.</span></span>  
  
## <a name="using-the-entity-activities"></a><span data-ttu-id="96c83-125">엔터티 활동 사용</span><span class="sxs-lookup"><span data-stu-id="96c83-125">Using the entity activities</span></span>  
 <span data-ttu-id="96c83-126">다음 코드 조각에서는 이 샘플에 나와 있는 엔터티 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-126">The following code snippets demonstrate how to use the entity activities presented in this sample.</span></span>  
  
### <a name="entitysql"></a><span data-ttu-id="96c83-127">EntitySql</span><span class="sxs-lookup"><span data-stu-id="96c83-127">EntitySql</span></span>  
 <span data-ttu-id="96c83-128">아래 코드 조각에서는 런던의 모든 고객을 이름으로 정렬하여 쿼리하는 방법과 고객 목록을 반복 진행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-128">The code snippet below shows how to query all customers in London sorted by name and how to iterate through the list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a><span data-ttu-id="96c83-129">EntityLinqQuery</span><span class="sxs-lookup"><span data-stu-id="96c83-129">EntityLinqQuery</span></span>  
 <span data-ttu-id="96c83-130">아래 코드 조각에서는 런던의 모든 고객을 쿼리하는 방법과 쿼리 결과로 얻은 고객 목록을 반복 진행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-130">The code snippet below shows how to query all customers in London and how to iterate through the resulting list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a><span data-ttu-id="96c83-131">EntityAdd</span><span class="sxs-lookup"><span data-stu-id="96c83-131">EntityAdd</span></span>  
 <span data-ttu-id="96c83-132">아래 코드 조각에서는 기존 Order에 OrderDetail 레코드를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-132">The code snippet below shows how to add an OrderDetail record to an existing Order.</span></span>  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a><span data-ttu-id="96c83-133">EntityDelete</span><span class="sxs-lookup"><span data-stu-id="96c83-133">EntityDelete</span></span>  
 <span data-ttu-id="96c83-134">아래 코드 조각에서는 주문이 있는 경우 Order의 기존 OrderDetail 레코드를 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-134">The code snippet below shows how to delete an existing OrderDetail record in an Order (if it exists).</span></span>  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="96c83-135">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="96c83-135">To use this sample</span></span>  
 <span data-ttu-id="96c83-136">이 샘플을 실행하려면 먼저 로컬 SQL Server Express 인스턴스에 `Northwind` 데이터베이스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-136">You must create the `Northwind` database in your local SQL server Express instance before running this sample.</span></span>  
  
#### <a name="to-set-up-the-northwind-database"></a><span data-ttu-id="96c83-137">Northwind 데이터베이스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="96c83-137">To set up the Northwind database</span></span>  
  
1.  <span data-ttu-id="96c83-138">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-138">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="96c83-139">새 명령 프롬프트 창에서 EntityActivities\CS 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-139">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="96c83-140">형식 `setup.cmd` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-140">Type `setup.cmd` and press ENTER.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="96c83-141">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="96c83-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="96c83-142">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 EntityActivities.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-142">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EntityActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="96c83-143">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-143">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="96c83-144">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-144">To run the solution, press CTRL+F5.</span></span>  
  
 <span data-ttu-id="96c83-145">이 샘플을 실행한 다음 `Northwind` 데이터베이스를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-145">After running this sample, you may want to remove the `Northwind` database.</span></span>  
  
#### <a name="to-uninstall-the-northwind-database"></a><span data-ttu-id="96c83-146">Northwind 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="96c83-146">To uninstall the Northwind database</span></span>  
  
1.  <span data-ttu-id="96c83-147">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-147">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="96c83-148">새 명령 프롬프트 창에서 EntityActivities\CS 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-148">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="96c83-149">형식 `cleanup.cmd` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-149">Type `cleanup.cmd` and press ENTER.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96c83-150">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="96c83-151">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="96c83-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="96c83-152">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="96c83-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="96c83-153">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c83-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`