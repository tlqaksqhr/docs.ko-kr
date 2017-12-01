---
title: "NoSQL 데이터베이스를 사용 하 여 지 속성 인프라"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | NoSQL 데이터베이스를 사용 하 여 지 속성 인프라"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e4b63511069b89cc5761ce7ed64f09e9035a56a3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a>NoSQL 데이터베이스를 사용 하 여 지 속성 인프라

데이터 계층의 인프라에 대 한 NoSQL 데이터베이스를 사용할 때 일반적으로 사용 하지 않는 엔터티 프레임 워크 코어와 같은 ORM 합니다. 대신 Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, 또는 Azure 저장소 테이블와 같은 NoSQL 엔진에 의해 제공 되는 API를 사용 합니다.

그러나 특히 문서 관련 데이터베이스 Azure Cosmos DB, CouchDB, 또는 RavenDB와 같은 NoSQL 데이터베이스를 사용 하는 경우 DDD 집계를 사용 하 여 모델을 디자인 하는 방식을 비슷합니다 부분적으로 하는 방법 것 EF 코어에서의 id에 관해서는 집계 루트, 자식 엔터티 클래스 및 값 개체 클래스입니다. 그러나 데이터베이스 선택 디자인에 영향을 줍니다 궁극적으로.

문서 관련 데이터베이스를 사용 하면 JSON 또는 다른 형식으로 직렬화 하는 단일 문서로 집계를 구현 합니다. 그러나 데이터베이스의 사용은는 도메인 모델 코드 관점에서 투명 합니다. NoSQL 데이터베이스를 사용할 때 계속 사용 하는 엔터티 클래스 및 집계 루트 클래스 하지만 때 때문에 EF 코어를 사용할 때 보다 더 많은 융통성는 지 속성은 관계형 합니다.

차이점은 해당 모델을 유지 하는 방법입니다. POCO 엔터티 클래스에 따라 도메인 모델을 구현한 경우 인프라 지 속성, 알 수 없는 것 수 모양을 NoSQL 관계형 에서도 다른 지 속성 인프라를 이동할 수 있습니다. 그러나 목표 수는 없습니다. 항상 서로 다른 데이터베이스에 대 한 제약 조건을 밀어넣습니다 있습니다 다시은 동일한 모델에 대 한 수 관계형 또는 NoSQL 데이터베이스입니다. 지 속성 모델을 변경 하지 않는 것 간단한, 하므로 트랜잭션 및 지 속성 작업 매우 달라 집니다.

예를 들어 문서 관련 데이터베이스에 두어도 되는 집계 루트에 여러 개의 자식 컬렉션 속성. 관계형 데이터베이스에 여러 개의 자식 컬렉션 속성을 쿼리할 되므로 누르게, EF에서 게 UNION 모든 SQL 문을 다시 가져오는 합니다. 관계형 데이터베이스 또는 NoSQL 데이터베이스에 대해 동일한 도메인 모델은 간단 하 고 시도 하지 마십시오. 실제로 데이터는 각 특정 데이터베이스에 사용 하려는 방법에 대 한 이해가 사용 하 여 모델을 디자인 해야 합니다.

NoSQL 데이터베이스를 사용 하는 경우 이점은 이므로 엔터티는 더 정규화 되지 않은 테이블 매핑을 설정 하지 마십시오. 도메인 모델은 관계형 데이터베이스를 사용할 때 보다 좀 더 융통적 될 수 있습니다.

때 NoSQL 이동 집계를 기반으로 도메인 모델 디자인 및 집계를 디자인 하려면 유사 하기 때문에 문서 관련 데이터베이스는 관계형 데이터베이스를 사용 하 여 보다 쉽게 수 있습니다 문서 관련 데이터베이스에서 문서를 직렬화 합니다. 그런 다음 해당 집계에 필요한 모든 정보가 해당 "모음"에 포함할 수 있습니다.

예를 들어, 다음 JSON 코드 문서 관련 데이터베이스를 사용할 때의 순서 집계 샘플 구현입니다. 아래 EF 코어를 사용 하지 않고 eShopOnContainers 샘플에서 구현한 순서 집계 비슷합니다.

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

A C를 사용 하는 경우\# Azure Cosmos DB SDK 집계와 같은 사용 하는 집계를 구현 하는 모델은 c 유사\# EF 코어 사용 되는 POCO 클래스입니다. 다음 코드 에서처럼는 응용 프로그램 및 인프라 계층에서 사용 하는 방법에 차이가:

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH DOCUMENTDB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).
// This can be saved as JSON as is without converting into rows/columns.
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

OrderItem orderItem2 = new OrderItem
{
    Id = 20170012,
    ProductId = "123457",
    ProductName = ".NET Mug",
    UnitPrice = 15,
    Units = 1,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);

// *** End of Domain Model Code ***
//...
// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, order);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

도메인 모델과 함께 작동 하는 방법은 인프라는 EF 때 도메인 모델 계층에서 사용할 것 방식과 유사 하 게 될 수 있음을 확인할 수 있습니다. 여전히 동일한 집계 루트 메서드를 사용 하 여 일관성, 고정, 및 집계 내에서 유효성 검사를 합니다.

그러나 때 유지 모델 NoSQL 데이터베이스, 코드 및 EF 핵심 코드에 비해 크게 API 변경 또는 다른 관계형 데이터베이스와 관련 된 코드입니다.

#### <a name="additional-resources"></a>추가 리소스

-   **DocumentDB에 데이터를 모델링**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)

-   **Vaughn Vernon. 이상적인 도메인 기반 디자인 집계 저장소? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)

-   **지 속성을 알 수 없는.NET에 대 한 이벤트 저장소.** GitHub 리포지토리 합니다.
    [*https://github.com/NEventStore/NEventStore*](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
[이전] [다음] (microservice-application-layer-web-api-design.md) (infrastructure-persistence-layer-implemenation-entity-framework-core.md)
