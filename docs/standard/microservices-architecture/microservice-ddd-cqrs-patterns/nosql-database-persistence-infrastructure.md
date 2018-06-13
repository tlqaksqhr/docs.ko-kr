---
title: NoSQL 데이터베이스를 지속성 인프라로 사용
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | NoSQL 데이터베이스를 지속성 인프라로 사용
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 2618e8c068ec538f5bfed2f8243d1c594478fcb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578965"
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="bb135-103">NoSQL 데이터베이스를 지속성 인프라로 사용</span><span class="sxs-lookup"><span data-stu-id="bb135-103">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="bb135-104">인프라 데이터 계층에 대해 NoSQL 데이터베이스를 사용하는 경우 일반적으로 Entity Framework Core와 같은 ORM을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-104">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="bb135-105">대신 Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB 또는 Azure Storage Tables와 같은 NoSQL 엔진에 의해 제공되는 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-105">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="bb135-106">그러나 NoSQL 데이터베이스, 특히 Azure Cosmos DB, CouchDB 또는 RavenDB와 같은 문서 기반 데이터베이스를 사용하는 경우 DDD 집계를 사용하여 모델을 디자인하는 방식은 집계 루트, 자식 엔터티 클래스 및 값 개체 클래스의 식별과 관련하여 EF Core에서 수행하는 방법과 부분적으로 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-106">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="bb135-107">그러나 궁극적으로 데이터베이스 선택은 디자인에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-107">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="bb135-108">문서 기반 데이터베이스를 사용하면 JSON 또는 다른 형식으로 직렬화되는 단일 문서로 집계를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-108">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="bb135-109">그러나 데이터베이스의 사용은 도메인 모델 코드 관점에서 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-109">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="bb135-110">NoSQL 데이터베이스를 사용할 때 계속해서 엔터티 클래스 및 집계 루트 클래스를 사용하지만 지속성은 관계형이 아니기 때문에 EF Core를 사용할 때 보다 더 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-110">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="bb135-111">차이점은 해당 모델을 유지하는 방법에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-111">The difference is in how you persist that model.</span></span> <span data-ttu-id="bb135-112">POCO 엔터티 클래스에 따라 도메인 모델을 구현한 경우 인프라 지속성에 상관 없이 다른 지속성 인프라로 이동할 수 있는 것처럼 보일 수 있습니다(관계형에서 NoSQL로도).</span><span class="sxs-lookup"><span data-stu-id="bb135-112">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="bb135-113">그러나 목표가 될 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-113">However, that should not be your goal.</span></span> <span data-ttu-id="bb135-114">서로 다른 데이터베이스에는 사용자를 다시 푸시하는 제약 조건이 항상 있으므로 관계형 또는 NoSQL 데이터베이스에 대해 동일한 모델을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-114">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="bb135-115">트랜잭션 및 지속성 작업은 매우 달라지므로 지속성 모델을 변경하는 것은 간단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-115">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="bb135-116">예를 들어 문서 기반 데이터베이스에서 집계 루트에 여러 개의 자식 컬렉션 속성을 포함하는 것은 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-116">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="bb135-117">관계형 데이터베이스에서 여러 개의 자식 컬렉션 속성을 쿼리하는 것은 EF에서 UNION ALL SQL 문을 다시 가져오므로 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-117">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="bb135-118">관계형 데이터베이스 또는 NoSQL 데이터베이스에 대해 동일한 도메인 모델을 갖는 것은 간단하지 않으며 시도해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-118">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="bb135-119">데이터가 각 특정 데이터베이스에서 사용되는 방법에 대한 이해와 함께 모델을 디자인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-119">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="bb135-120">NoSQL 데이터베이스를 사용하는 경우 이점은 엔터티가 더욱 비정규화되므로 테이블 매핑을 설정하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-120">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="bb135-121">도메인 모델은 관계형 데이터베이스를 사용할 때보다 좀 더 유연할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-121">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="bb135-122">집계를 기반으로 도메인 모델을 디자인할 때 NoSQL 및 문서 기반 데이터베이스로 이동하는 것은 디자인하는 집계가 문서 기반 데이터베이스의 직렬화된 문서와 유사하므로 관계형 데이터베이스를 사용하는 것보다 더욱 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-122">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="bb135-123">그런 다음, 해당 집계에 필요할 수 있는 모든 정보를 해당 "모음"에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-123">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="bb135-124">예를 들어 다음 JSON 코드는 문서 기반 데이터베이스를 사용할 때 순서 집계의 샘플 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-124">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="bb135-125">eShopOnContainers 샘플에서 구현한 순서 집계와 비슷하지만 아래 EF Core를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-125">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a><span data-ttu-id="bb135-126">Azure Cosmos DB 및 네이티브 Cosmos DB API 소개</span><span class="sxs-lookup"><span data-stu-id="bb135-126">Introduction to Azure Cosmos DB and the native Cosmos DB API</span></span>

<span data-ttu-id="bb135-127">[Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction)는 중요 응용 프로그램에 대한 Microsoft의 전 세계적으로 분산된 데이터베이스 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-127">[Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) is Microsoft's globally distributed database service for mission-critical applications.</span></span> <span data-ttu-id="bb135-128">Azure Cosmos DB는 [업계 최고의 SLA](https://azure.microsoft.com/support/legal/sla/cosmos-db/)로 지원되는 [턴키 방식으로 전역 배포](https://docs.microsoft.com/en-us/azure/cosmos-db/distribute-data-globally), 전 세계적인 [처리량 및 저장소의 탄력적인 확장](https://docs.microsoft.com/en-us/azure/cosmos-db/partition-data), 한 자릿수 밀리초 대기 시간(99번째 백분위수), [5개의 잘 정의된 일관성 수준](https://docs.microsoft.com/en-us/azure/cosmos-db/consistency-levels) 및 보장되는 높은 가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-128">Azure Cosmos DB provides [turn-key global distribution](https://docs.microsoft.com/en-us/azure/cosmos-db/distribute-data-globally), [elastic scaling of throughput and storage](https://docs.microsoft.com/en-us/azure/cosmos-db/partition-data) worldwide, single-digit millisecond latencies at the 99th percentile, [five well-defined consistency levels](https://docs.microsoft.com/en-us/azure/cosmos-db/consistency-levels), and guaranteed high availability, all backed by [industry-leading SLAs](https://azure.microsoft.com/support/legal/sla/cosmos-db/).</span></span> <span data-ttu-id="bb135-129">Azure Cosmos DB는 스키마 및 인덱스 관리를 처리할 필요 없이 [데이터를 자동으로 인덱싱합니다](http://www.vldb.org/pvldb/vol8/p1668-shukla.pdf).</span><span class="sxs-lookup"><span data-stu-id="bb135-129">Azure Cosmos DB [automatically indexes data](http://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) without requiring you to deal with schema and index management.</span></span> <span data-ttu-id="bb135-130">다중 모델이며 문서, 키-값, 그래프 및 열 형식 데이터 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-130">It is multi-model and supports document, key-value, graph, and columnar data models.</span></span>

<span data-ttu-id="bb135-131">![](./media/image19.1.png) 그림 9-19.</span><span class="sxs-lookup"><span data-stu-id="bb135-131">![](./media/image19.1.png) Figure 9-19.</span></span> <span data-ttu-id="bb135-132">Azure Cosmos DB 전역 배포</span><span class="sxs-lookup"><span data-stu-id="bb135-132">Azure Cosmos DB global distribution</span></span>

<span data-ttu-id="bb135-133">C\# 모델을 사용하여 Azure Cosmos DB API에서 사용될 집계를 구현하는 경우 집계는 EF Core와 함께 사용되는 C\# POCO 클래스와 유사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-133">When you use a C\# model to implement the aggregate to be used by the Azure Cosmos DB API, the aggregate can be similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="bb135-134">차이점은 다음 코드에서처럼 응용 프로그램 및 인프라 계층에서 사용하는 방법에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-134">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).

Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);

OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);
// *** End of Domain Model Code ***

// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, orderAggregate);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="bb135-135">도메인 모델을 사용하는 방법은 인프라가 EF인 경우 도메인 모델 계층에서 사용하는 방법과 유사할 수 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-135">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="bb135-136">여전히 동일한 집계 루트 메서드를 사용하여 집계 내에서 일관성, 고정 및 유효성 검사를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-136">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="bb135-137">그러나 NoSQL 데이터베이스로 모델을 유지하는 경우 코드 및 API는 EF Core 코드 또는 관계형 데이터베이스와 관련된 다른 코드에 비해 크게 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-137">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

## <a name="implementing-net-code-targeting-mongodb-and-azure-cosmos-db"></a><span data-ttu-id="bb135-138">MongoDB 및 Azure Cosmos DB를 대상으로 하는 .NET 코드 구현</span><span class="sxs-lookup"><span data-stu-id="bb135-138">Implementing .NET code targeting MongoDB and Azure Cosmos DB</span></span>

### <a name="using-azure-cosmos-db-from-net-containers"></a><span data-ttu-id="bb135-139">.NET 컨테이너에서 Azure Cosmos DB 사용</span><span class="sxs-lookup"><span data-stu-id="bb135-139">Using Azure Cosmos DB from .NET containers</span></span>

<span data-ttu-id="bb135-140">다른 .NET 응용 프로그램에서와 같이 컨테이너에서 실행되는 .NET 코드에서 Azure Cosmos DB 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-140">You can access Azure Cosmos DB databases from .NET code running in containers, like from any other .NET application.</span></span> <span data-ttu-id="bb135-141">예를 들어 eShopOnContainers의 Locations.API 및 Marketing.API 마이크로 서비스는 Azure Cosmos DB 데이터베이스를 사용할 수 있도록 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-141">For instance, the Locations.API and Marketing.API microservices in eShopOnContainers are implemented so they can consume Azure Cosmos DB databases.</span></span>

<span data-ttu-id="bb135-142">그러나 Docker 개발 환경 관점에서 Azure Cosmos DB에 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-142">However, there’s a limitation in Azure Cosmos DB from a Docker development environment point of view.</span></span> <span data-ttu-id="bb135-143">2017년 말을 기준으로, 로컬 개발 컴퓨터(예: PC)에서 실행할 수 있는 온-프레미스 [Azure Cosmos DB 에뮬레이터](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator)가 있는 경우에도 Linux가 아닌 Windows만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-143">Even when there’s a on-premises [Azure Cosmos DB Emulator](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator) able to run in a local development machine (like a PC), as of late 2017, it just supports Windows, not Linux.</span></span> 

<span data-ttu-id="bb135-144">Docker에서 이 에뮬레이터를 실행할 가능성도 있지만 Linux 컨테이너가 아닌 Windows 컨테이너에서만 입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-144">There is also the possibility to run this emulator on Docker, but just on Windows Containers with the , not Linux Containers.</span></span> <span data-ttu-id="bb135-145">현재 Windows의 경우 Docker에 Linux 및 Windows 컨테이너를 동시에 배포할 수 없으므로 응용 프로그램이 Linux 컨테이너로 배포되는 경우 개발 환경에 대한 초기 핸디캡이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-145">That is an initial handicap for the development environment if your application is deployed as Linux containers, since, currently, you cannot deploy Linux and Windows Containers on Docker for Windows at the same time.</span></span> <span data-ttu-id="bb135-146">배포되는 모든 컨테이너는 Linux 또는 Windows용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-146">Either all containers being deployed have to be for Linux or for Windows.</span></span>  

<span data-ttu-id="bb135-147">개발/테스트 솔루션에 대한 이상적이고 더욱 간단한 배포는 개발/테스트 환경이 항상 일치하도록 사용자 지정 컨테이너와 함께 컨테이너로 데이터베이스 시스템을 배포할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-147">The ideal and more straightforward deployment for a dev/test solution is to be able to deploy your database systems as containers along with your custom containers so your dev/test environments are always consistent.</span></span>

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a><span data-ttu-id="bb135-148">로컬 개발/테스트 Linux/Windows 컨테이너와 Azure Cosmos DB에 대해 MongoDB API 사용</span><span class="sxs-lookup"><span data-stu-id="bb135-148">Use MongoDB API for local dev/test Linux/Windows containers plus Azure Cosmos DB</span></span>

<span data-ttu-id="bb135-149">Cosmos DB 데이터베이스는 .NET용 MongoDB API뿐만 아니라 네이티브 MongoDB 유선 프로토콜도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-149">Cosmos DB databases support MongoDB API for .NET as well as the native MongoDB wire protocol.</span></span> <span data-ttu-id="bb135-150">즉, 기존 드라이버를 사용하여 MongoDB용으로 작성된 응용 프로그램은 이제 그림 9-20에 나와 있는 것처럼 Cosmos DB와 통신하고 MongoDB 데이터베이스 대신 Cosmos DB 데이터베이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-150">This means that by using existing drivers, your application written for MongoDB can now communicate with Cosmos DB and use Cosmos DB databases instead of MongoDB databases, as shown in Figure 9-20.</span></span>

<span data-ttu-id="bb135-151">![](./media/image19.2.png) 그림 9-20.</span><span class="sxs-lookup"><span data-stu-id="bb135-151">![](./media/image19.2.png) Figure 9-20.</span></span> <span data-ttu-id="bb135-152">MongoDB API 및 프로토콜을 사용하여 Azure Cosmos DB에 액세스</span><span class="sxs-lookup"><span data-stu-id="bb135-152">Using MongoDB API and protocol to access Azure Cosmos DB</span></span>

<span data-ttu-id="bb135-153">[MongoDB Docker 이미지](https://hub.docker.com/r/_/mongo/)는 Docker Linux 컨테이너 및 Docker Windows 컨테이너를 지원하는 다중 아치 이미지이므로 Linux 컨테이너를 사용하는 Docker 환경에서 개념의 증명에 매우 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-153">This is a very convenient approach for proof of concepts in Docker environments with Linux containers because the [MongoDB Docker image](https://hub.docker.com/r/_/mongo/) is a multi-arch image that supports Docker Linux containers and Docker Windows containers.</span></span>

<span data-ttu-id="bb135-154">그림 9-21에서 표시된 것처럼 MongoDB API를 사용하여 eShopOnContainers는 로컬 개발 환경에 대해 MongoDB Linux 및 Windows 컨테이너를 지원하지만 [MongoDB 연결 문자열을 Azure Cosmos DB를 가리키도록](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account) 단순히 변경하여 Azure Cosmos DB로 확장 가능한 PaaS 클라우드 솔루션으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-154">As shown in the image 9-21, by using the MongoDB API, eShopOnContainers supports MongoDB Linux and Windows containers for the local development environment but then, you can move to a scalable, PaaS cloud solution as Azure Cosmos DB by simply [changing the MongoDB connection string to point to Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account).</span></span> 

<span data-ttu-id="bb135-155">![](./media/image20-bis.png) 그림 9-21.</span><span class="sxs-lookup"><span data-stu-id="bb135-155">![](./media/image20-bis.png) Figure 9-21.</span></span> <span data-ttu-id="bb135-156">개발 환경 또는 프로덕션용 Azure Cosmos DB에 대해 MongoDB 컨테이너를 사용하는 eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="bb135-156">eShopOnContainers using MongoDB containers for dev-env or Azure Cosmos DB for production</span></span>

<span data-ttu-id="bb135-157">프로덕션 Azure Cosmos DB는 PaaS 및 확장 가능한 서비스로 Azure의 클라우드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-157">The production Azure Cosmos DB would be running in Azure’s cloud as a PaaS and scalable service.</span></span>

<span data-ttu-id="bb135-158">사용자 지정 .NET Core 컨테이너는 로컬 개발 Docker 호스트(Windows 10 컴퓨터에서 Windows용 Docker 사용)에서 실행되거나 Azure AKS 또는 Azure Service Fabric에서 Kubernetes와 같은 프로덕션 환경에 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-158">Your custom .NET Core containers can run on a local development Docker host (that is using Docker for Windows in a Windows 10 machine) or be deployed into a production environment, like Kubernetes in Azure AKS or Azure Service Fabric.</span></span> <span data-ttu-id="bb135-159">이 두 번째 환경에서는 프로덕션에서 데이터를 처리하기 위해 클라우드에서 Azure Cosmos DB를 사용하므로 MongoDB 컨테이너가 아닌 .NET Core 사용자 지정 컨테이너만 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-159">In this second environment, you would deploy only the .NET Core custom containers but not the MongoDB container since you’d be using Azure Cosmos DB in the cloud for handling the data in production.</span></span>

<span data-ttu-id="bb135-160">MongoDB API를 사용하는 명백한 이점은 솔루션이 두 데이터베이스 엔진, MongoDB 또는 Azure Cosmos DB에서 실행될 수 있으므로 다른 환경으로의 마이그레이션이 용이해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-160">A clear benefit of using the MongoDB API is that your solution could run in both database engines, MongoDB or Azure Cosmos DB, so migrations to different environments should be easy.</span></span> <span data-ttu-id="bb135-161">그러나 경우에 따라 특정 데이터베이스 엔진의 기능을 완전히 활용하기 위해 네이티브 API(즉 네이티브 Cosmos DB API)를 사용하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-161">However, sometimes it is worthwhile to use a native API (that is the native Cosmos DB API) in order to take full advantage of the capabilities of a specific database engine.</span></span>

<span data-ttu-id="bb135-162">클라우드에서 단순히 MongoDB와 Cosmos DB 사용 간의 자세한 비교는 [이 페이지에서 Azure Cosmos DB 사용의 이점](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb135-162">For further comparison between simply using MongoDB versus Cosmos DB in the cloud, see the [Benefits of using Azure Cosmos DB in this page](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction).</span></span> 


### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a><span data-ttu-id="bb135-163">프로덕션 응용 프로그램에 대한 접근 방식 분석: MongoDB API와 Cosmos DB API 비교</span><span class="sxs-lookup"><span data-stu-id="bb135-163">Analyze your approach for production applications: MongoDB API vs. Cosmos DB API</span></span>

<span data-ttu-id="bb135-164">eShopOnContainers에서 우선 순위는 근본적으로 Azure Cosmos DB를 함께 사용할 수 있는 NoSQL 데이터베이스를 사용하여 일관성 있는 개발/테스트 환경을 갖는 것이었으므로 MongoDB API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-164">In eShopOnContainers, we’re using MongoDB API because our priority was fundamentally to have a consistent dev/test environment using a NoSQL database that could also work with Azure Cosmos DB.</span></span>

<span data-ttu-id="bb135-165">그러나 MongoDB API를 사용하여 프로덕션 응용 프로그램에 대해 Azure에서 Azure Cosmos DB에 액세스하려는 경우 네이티브 Azure Cosmos DB API를 사용하는 것과 비교하여 MongoDB API를 사용하여 Azure Cosmos DB 데이터베이스에 액세스할 때 기능 및 성능에서의 차이점을 분석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-165">However, if you planning to use MongoDB API to access Azure Cosmos DB in Azure for production applications, you should analyze the differences in capabilities and performance when using MongoDB API to access Azure Cosmos DB databases compared to using the native Azure Cosmos DB API.</span></span> <span data-ttu-id="bb135-166">유사한 경우 MongoDB API를 사용할 수 있으며, 동시에 두 개의 NoSQL 데이터베이스 엔진을 지원하는 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-166">If it is similar you can use MongoDB API, and you get the benefit of supporting two NoSQL database engines at the same time.</span></span> 

<span data-ttu-id="bb135-167">또한 [MongoDB Azure 서비스](https://www.mongodb.com/scale/mongodb-azure-service)와 함께 Azure의 클라우드에서 프로덕션 데이터베이스로 MongoDB 클러스터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-167">You could also use MongoDB clusters as the production database in Azure’s cloud, too, with [MongoDB Azure Service](https://www.mongodb.com/scale/mongodb-azure-service).</span></span> <span data-ttu-id="bb135-168">그러나 Microsoft에서 제공하는 PaaS 서비스가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-168">But that is not a PaaS service provided by Microsoft.</span></span> <span data-ttu-id="bb135-169">이 경우 Azure는 MongoDB에서 오는 해당 솔루션만 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-169">In this case, Azure is just hosting that solution coming from MongoDB.</span></span>

<span data-ttu-id="bb135-170">기본적으로 Linux 컨테이너에 대한 편리한 선택이므로 eShopOnContainers에서 수행한 것처럼 Azure Cosmos DB에 대해 항상 MongoDB API를 사용해서는 안 된다는 고지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-170">Basically, this is just a disclaimer stating that you shouldn’t always use MongoDB API against Azure Cosmos DB, as we did in eShopOnContainers because it was a convenient choice for Linux containers.</span></span> <span data-ttu-id="bb135-171">결정은 프로덕션 응용 프로그램에 대해 수행해야 하는 특정 요구 사항 및 테스트를 기준으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-171">The decision should be based on the specific needs and tests you need to do for your production application.</span></span>  

### <a name="the-code-using-mongodb-api-in-net-core-applications"></a><span data-ttu-id="bb135-172">코드: .NET Core 응용 프로그램에서 MongoDB API 사용</span><span class="sxs-lookup"><span data-stu-id="bb135-172">The code: Using MongoDB API in .NET Core applications</span></span>

<span data-ttu-id="bb135-173">.NET용 MongoDB API는 그림 9-22에 표시된 것처럼 Locations.API와 같이 프로젝트에 추가해야 하는 NuGet 패키지를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-173">MongoDB API for .NET is based on NuGet packages that you need to add to your projects, like the Locations.API shown in Figure 9-22.</span></span>

<span data-ttu-id="bb135-174">![](./media/image21-bis.png) 그림 9-22.</span><span class="sxs-lookup"><span data-stu-id="bb135-174">![](./media/image21-bis.png) Figure 9-22.</span></span> <span data-ttu-id="bb135-175">.NET Core 프로젝트에서 MongoDB API NuGet 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="bb135-175">MongoDB API NuGet packages references in a .NET Core project</span></span>

<span data-ttu-id="bb135-176">다음 섹션에서 코드를 검토하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-176">Let's investigate the code in the following sections.</span></span>

#### <a name="a-model-used-by-mongodb-api"></a><span data-ttu-id="bb135-177">MongoDB API에서 사용하는 모델</span><span class="sxs-lookup"><span data-stu-id="bb135-177">A Model used by MongoDB API</span></span>

<span data-ttu-id="bb135-178">먼저 응용 프로그램의 메모리 공간에 데이터베이스에서 가져온 데이터를 보유하는 모델을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-178">First, you need to define a model that will hold the data coming from the database in your application’s memory space.</span></span> <span data-ttu-id="bb135-179">eShopOnContainers에서 Locations에 대해 사용되는 모델의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-179">Here’s an example of the model used for Locations at eShopOnContainers.</span></span>

```csharp
using MongoDB.Bson;
using MongoDB.Bson.Serialization.Attributes;
using MongoDB.Driver.GeoJsonObjectModel;
using System.Collections.Generic;

public class Locations
{
    [BsonId]
    [BsonRepresentation(BsonType.ObjectId)]
    public string Id { get; set; }
    public int LocationId { get; set; }
    public string Code { get; set; }
    [BsonRepresentation(BsonType.ObjectId)]
    public string Parent_Id { get; set; }
    public string Description { get; set; }
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    public GeoJsonPoint<GeoJson2DGeographicCoordinates> Location 
                                                             { get; private set; }
    public GeoJsonPolygon<GeoJson2DGeographicCoordinates> Polygon 
                                                             { get; private set; }
    public void SetLocation(double lon, double lat) => SetPosition(lon, lat);
    public void SetArea(List<GeoJson2DGeographicCoordinates> coordinatesList) 
                                                    => SetPolygon(coordinatesList);

    private void SetPosition(double lon, double lat)
    {
        Latitude = lat;
        Longitude = lon;
        Location = new GeoJsonPoint<GeoJson2DGeographicCoordinates>(
            new GeoJson2DGeographicCoordinates(lon, lat));
    }

    private void SetPolygon(List<GeoJson2DGeographicCoordinates> coordinatesList)
    {
        Polygon = new GeoJsonPolygon<GeoJson2DGeographicCoordinates>(
                  new GeoJsonPolygonCoordinates<GeoJson2DGeographicCoordinates>(
                  new GeoJsonLinearRingCoordinates<GeoJson2DGeographicCoordinates>(
                                                                 coordinatesList)));
    }
}
```

<span data-ttu-id="bb135-180">MongoDB NuGet 패키지에서 가져온 몇 가지 특성 및 형식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-180">You can see there are a few attributes and types coming from the MongoDB NuGet packages.</span></span>

<span data-ttu-id="bb135-181">NoSQL 데이터베이스는 일반적으로 비관계형 계층적 데이터를 사용하는 데 매우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-181">NoSQL databases are usually very well suited for working with non-relational hierarchical data.</span></span> <span data-ttu-id="bb135-182">이 예제에서는 `GeoJson2DGeographicCoordinates`와 같이 지역 위치에 대해 특별히 만들어진 MongoDB 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-182">In this example, we are using MongoDB types expecially made for geo-locations, like `GeoJson2DGeographicCoordinates`.</span></span>

#### <a name="retrieve-the-database-and-the-collection"></a><span data-ttu-id="bb135-183">데이터베이스 및 컬렉션 검색</span><span class="sxs-lookup"><span data-stu-id="bb135-183">Retrieve the database and the collection</span></span>

<span data-ttu-id="bb135-184">eShopOnContainers에서 다음 코드에서와 같이 데이터베이스 및 MongoCollections를 검색하는 코드를 구현하는 사용자 지정 데이터베이스 컨텍스트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-184">In eShopOnContainers, we have created a custom database context where we implement the code to retrieve the database and the MongoCollections, as in the following code.</span></span>

```csharp
public class LocationsContext
{
    private readonly IMongoDatabase _database = null;

    public LocationsContext(IOptions<LocationSettings> settings)
    {
        var client = new MongoClient(settings.Value.ConnectionString);
        if (client != null)
            _database = client.GetDatabase(settings.Value.Database);
    }

    public IMongoCollection<Locations> Locations
    {
        get
        {
            return _database.GetCollection<Locations>("Locations");
        }
    }       
}
```

#### <a name="retrieve-the-data"></a><span data-ttu-id="bb135-185">데이터 검색</span><span class="sxs-lookup"><span data-stu-id="bb135-185">Retrieve the data</span></span>

<span data-ttu-id="bb135-186">C# 코드에서는 Web API 컨트롤러 또는 사용자 지정 리포지토리 구현과 같이 MongoDB API를 통해 쿼리할 때 다음과 유사한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-186">In C# code, like Web API controllers or custom Repositories implementation, you can write similar code to the following when querying through the MongoDB API.</span></span> <span data-ttu-id="bb135-187">`_context` 개체는 이전 `LocationsContext` 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-187">Note that the `_context` object is an instance of the previous `LocationsContext` class.</span></span>

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a><span data-ttu-id="bb135-188">MongoDB 연결 문자열에 대해 docker-compose.override.yml 파일에서 env-var를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-188">Use an env-var in the docker-compose.override.yml file for the MongoDB connection string</span></span>

<span data-ttu-id="bb135-189">MongoClient 개체를 만들 때 올바른 데이터베이스를 가리키는 정확한 `ConnectionString` 매개 변수인 기본 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-189">When creating a MongoClient object, it needs a fundamental parameter which is precisely the `ConnectionString` parameter pointing to the right database.</span></span> <span data-ttu-id="bb135-190">eShopOnContainers의 경우 연결 문자열은 로컬 MongoDB Docker 컨테이너 또는 "프로덕션" Azure Cosmos DB 데이터베이스를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-190">In the case of eShopOnContainers, the connection string can point to a local MongoDB Docker container or to a “production” Azure Cosmos DB database.</span></span>  <span data-ttu-id="bb135-191">해당 연결 문자열은 다음 yml 코드에서처럼 docker-compose 또는 Visual Studio를 사용하여 배포할 때 사용되는 `docker-compose.override.yml` 파일에서 정의된 환경 변수에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-191">That connection string comes from the environment variables defined in the `docker-compose.override.yml` files used when deploying with docker-compose or Visual Studio, as in the following yml code.</span></span>

```yml
# docker-compose.override.yml
version: '3'
services:
  # Other services
  locations.api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}

```

<span data-ttu-id="bb135-192">`ConnectionString` 환경 변수는 이러한 방식으로 해결됩니다. `ESHOP_AZURE_COSMOSDB` 전역 변수가 Azure Cosmos DB 연결 문자열로 `.env` 파일에서 정의되는 경우 클라우드에서 Azure Cosmos DB 데이터베이스에 액세스하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-192">The `ConnectionString` environment variable is resolved this way: If the `ESHOP_AZURE_COSMOSDB` global variable is defined in the `.env` file with the Azure Cosmos DB connection string, it will use it to access the Azure Cosmos DB database in the cloud.</span></span> 

<span data-ttu-id="bb135-193">다음 코드는 eShopOnContainers에서 구현된 것처럼 Azure Cosmos DB 연결 문자열 전역 환경 변수가 있는 `.env` 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-193">The following code shows the `.env` file with the Azure Cosmos DB connection string global environment variable, as implemented in eShopOnContainers:</span></span>

```yml
# .env file, in eShopOnContainers root folder
# Other Docker environment variables

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost
ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=<YourDockerHostIP>

#ESHOP_AZURE_COSMOSDB=<YourAzureCosmosDBConnData>

#Other environment variables for additional Azure infrastructure assets
#ESHOP_AZURE_REDIS_BASKET_DB=<YourAzureRedisBasketInfo>
#ESHOP_AZURE_STORAGE_CATALOG_URL=<YourAzureStorage_Catalog_BLOB_URL>
#ESHOP_AZURE_SERVICE_BUS=<YourAzureServiceBusInfo>
```

<span data-ttu-id="bb135-194">[Azure Cosmos DB에 MongoDB 응용 프로그램 연결](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account)에 설명된 것처럼 ESHOP_AZURE_COSMOSDB 줄의 주석 처리를 제거하고 Azure Portal에서 가져온 Azure Cosmos DB 연결 문자열로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-194">You should uncomment the ESHOP_AZURE_COSMOSDB line and update it with your Azure Cosmos DB connection string obtained from the Azure portal as explained in [Connect a MongoDB application to Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account).</span></span>

<span data-ttu-id="bb135-195">`ESHOP_AZURE_COSMOSDB` 전역 변수가 비어 있는 경우(`.env` 파일에서 주석으로 처리된 것을 의미함) 컨테이너는 다음 .yml 코드에 표시된 것처럼 `nosql.data`라는 eShopOnContainers에 배포된 로컬 MongoDB 컨테이너를 가리키는 기본 MongoDB 연결 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb135-195">If the `ESHOP_AZURE_COSMOSDB` global variable is empty, meaning that it is commented out in the `.env` file, then the container uses a default MongoDB connection string pointing to the local MongoDB container deployed in eShopOnContainers which is named `nosql.data`, as shown in the following .yml code.</span></span> 

#### <a name="additional-resources"></a><span data-ttu-id="bb135-196">추가 자료</span><span class="sxs-lookup"><span data-stu-id="bb135-196">Additional resources</span></span>

-   <span data-ttu-id="bb135-197">**NoSQL 데이터베이스용 문서 데이터 모델링**
    [*https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data*](https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data)</span><span class="sxs-lookup"><span data-stu-id="bb135-197">**Modeling document data for NoSQL databases**
[*https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data*](https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data)</span></span>

-   <span data-ttu-id="bb135-198">**Vaughn Vernon. 이상적인 도메인 기반 디자인 집계 저장소?**
    [*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="bb135-198">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="bb135-199">**Azure DB Cosmos 소개: MongoDB용 API** 
    [*https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction)</span><span class="sxs-lookup"><span data-stu-id="bb135-199">**Introduction to Azure Cosmos DB: API for MongoDB** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction)</span></span>

-   <span data-ttu-id="bb135-200">**Azure Cosmos DB: .NET 및 Azure Portal에서 MongoDB API 웹앱 빌드** 
    [*https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet *](https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet )</span><span class="sxs-lookup"><span data-stu-id="bb135-200">**Azure Cosmos DB: Build a MongoDB API web app with .NET and the Azure portal** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet *](https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet )</span></span>

-   <span data-ttu-id="bb135-201">**로컬 개발 및 테스트에 Azure Cosmos DB 에뮬레이터 사용** 
    [*https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator*](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator)</span><span class="sxs-lookup"><span data-stu-id="bb135-201">**Use the Azure Cosmos DB Emulator for local development and testing** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator*](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator)</span></span>

-   <span data-ttu-id="bb135-202">**Azure Cosmos DB에 MongoDB 응용 프로그램 연결** 
    [*https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account*](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account)</span><span class="sxs-lookup"><span data-stu-id="bb135-202">**Connect a MongoDB application to Azure Cosmos DB** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account*](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account)</span></span>

-   <span data-ttu-id="bb135-203">**Cosmos DB 에뮬레이터 Docker 이미지(Windows 컨테이너)** 
    [*https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/*](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/)</span><span class="sxs-lookup"><span data-stu-id="bb135-203">**The Cosmos DB Emulator Docker image (Windows Container)** 
[*https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/*](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/)</span></span>

-   <span data-ttu-id="bb135-204">**MongoDB Docker 이미지(Linux 및 Windows 컨테이너)** 
    [*https://hub.docker.com/r/_/mongo/*](https://hub.docker.com/r/_/mongo/)</span><span class="sxs-lookup"><span data-stu-id="bb135-204">**The MongoDB Docker image (Linux and Windows Container)** 
[*https://hub.docker.com/r/_/mongo/*](https://hub.docker.com/r/_/mongo/)</span></span>

-   <span data-ttu-id="bb135-205">**Azure Cosmos DB에서 MongoChef(Studio 3T) 사용: MongoDB 계정용 API** 
    [*https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef)</span><span class="sxs-lookup"><span data-stu-id="bb135-205">**Use MongoChef (Studio 3T) with an Azure Cosmos DB: API for MongoDB account** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="bb135-206">[이전] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [다음] (microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="bb135-206">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
