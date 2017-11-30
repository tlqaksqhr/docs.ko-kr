---
title: "CQRS 마이크로 서비스에서 읽기/쿼리를 구현합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | CQRS 마이크로 서비스에서 읽기/쿼리를 구현합니다."
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>CQRS 마이크로 서비스에서 읽기/쿼리를 구현합니다.

읽기/쿼리용 eShopOnContainers 참조 응용 프로그램에서 주문 마이크로 서비스 DDD 모델 및 트랜잭션 영역에서 독립적으로 쿼리를 구현합니다. 이 작업은 쿼리에 대 한 및 트랜잭션에 대 한 요구는 매우 다른 때문에 수행 되었습니다. 쓰기는 도메인 논리를 준수 해야 하는 트랜잭션을 실행 합니다. 반면에 idempotent 쿼리와 도메인 규칙에서 분리 됩니다.

그림 9-3에 나와 있는 것 처럼 방법을 간단 합니다. API 인터페이스 (예: 마이크로 ORM Dapper와 같은) 모든 인프라를 사용 하 고 UI 응용 프로그램의 요구에 따라 동적 Viewmodel 반환 Web API 컨트롤러에 의해 구현 됩니다.

![](./media/image3.png)

**그림 9-3**합니다. CQRS 마이크로 서비스에서 쿼리에 대 한 가장 간단한 방법

쿼리에 대 한 가능한 가장 단순한 방법입니다. 쿼리 정의 데이터베이스를 쿼리 하 고 각 쿼리에 대 한 구축 동적 ViewModel를 반환 합니다. 쿼리 idempotent 이므로 쿼리를 실행 하면 실패 한 횟수에 관계 없이 데이터 변경 되지 않습니다. 따라서 집계 및 기타 패턴 같은 트랜잭션 측면에서 사용 된 모든 DDD 패턴에 의해 제한 될 필요가 없습니다 되며,이 쿼리가 트랜잭션 영역에서 서로 다른 때문입니다. UI는 데이터에 대 한 데이터베이스를 쿼리 하 고 정적으로 되도록 필요 없는 동적 ViewModel 멤버의 형식이 정의 (Viewmodel는에 대 한 클래스 없음)를 제외 하 고 자체 SQL 문에서 반환 됩니다.

코드 쿼리 측에 대 한 필요한 단순한 방법 이므로, (ORM와 같은 마이크로 사용 하 여 코드와 같은 [Dapper](https://github.com/StackExchange/Dapper))를 구현할 수 있습니다 [동일한 웹 API 프로젝트 내](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs)합니다. 그림 9-4이를 보여 줍니다. 에 정의 된 쿼리는 **Ordering.API** eShopOnContainers 솔루션 내의 마이크로 서비스 프로젝트입니다.

![](./media/image4.png)

**그림 9-4**합니다. EShopOnContainers에 Ordering 마이크로 서비스에 대 한 쿼리

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>클라이언트 앱의 경우와 별개의 도메인 모델 제약 조건에 대 한 특히 Viewmodel를 사용 하 여

클라이언트 응용 프로그램에서 필요한 데이터를 가져올 쿼리가 수행 된 이후 쿼리가 반환한 데이터를 기반으로 하는 클라이언트에 대 한 반환 되는 형식은 구체적으로 만들 수 있습니다. 이러한 모델 또는 데이터 전송 개체 (Dto) Viewmodel 라고 합니다.

반환된 된 데이터 (ViewModel)는 데이터베이스 또는 트랜잭션 영역에 대 한 도메인 모델에 정의 된 여러 집계 간에 여러 엔터티 또는 테이블 데이터를 결합 한 결과 수 있습니다. 이 경우 만들어지기 때문에 쿼리 도메인 모델에 관계 없이, 집계 경계 및 제약 조건 완전히 무시 되 고 모든 테이블과 해야 하는 열을 쿼리할 수 있습니다. 이 방법은 만들기 또는 업데이트 쿼리 개발자를 위한 뛰어난 유연성과 생산성을 제공 합니다.

Viewmodel 클래스에 정의 된 정적 형식이 될 수 있습니다. 또는 만들 수 있습니다 (정렬 마이크로 서비스에서 구현 되는)으로 수행 하는 쿼리에 따라 동적으로 개발자가 매우 민첩 변수인 합니다.

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>마이크로 ORM로 Dapper를 사용 하 여 쿼리를 수행 

쿼리를 위한 모든 마이크로 ORM, Entity Framework Core 또는 심지어 일반 ADO.NET을 사용할 수 있습니다. 샘플 응용 프로그램에서에 인기 있는 마이크로 ORM의 좋은 예로 eShopOnContainers 정렬 마이크로 서비스에 대 한 Dapper를 선택합니다. 일반 SQL 쿼리는 매우 적은 프레임 워크 이기 때문에 뛰어난 성능으로 실행할 수 있습니다. Dapper를 사용 하 여 액세스할 수 있으며 여러 테이블을 조인 하는 SQL 쿼리를 작성할 수 있습니다.

Dapper (Sam Saffron에서 만든 원래) 오픈 소스 프로젝트 이며에서 사용 하는 빌딩 블록의 일부인 [스택 오버플로](https://stackoverflow.com/)합니다. Dapper를 사용 하려면 하기만 하면 통해를 설치 하는 [Dapper NuGet 패키지](https://www.nuget.org/packages/Dapper)다음 그림에 표시 된 것 처럼 합니다.

![](./media/image5.png)

사용 하 여 추가 해야 문의 코드는 Dapper 확장 메서드에 액세스할 수 있도록 합니다.

Dapper를 사용 하 여 코드에서 System.Data.SqlClient 네임 스페이스에서 사용할 수 있는 SqlClient 클래스 직접 사용 합니다. QueryAsync 메서드 및 SqlClient 클래스를 확장 하는 다른 확장 메서드를 통해 간단 하 고 성능이 뛰어난 방식으로 쿼리를 간단히 실행할 수 있습니다.

## <a name="dynamic-and-static-viewmodels"></a>동적 및 정적 Viewmodel

대부분의 쿼리가 반환한 Viewmodel으로 구현 된 정렬 마이크로 서비스에서 다음 코드에 나와 있는 것 처럼 *동적*합니다. 즉, 반환 되는 특성의 하위 집합은 쿼리 자체에 따라 결정 되도록 합니다. 쿼리 또는 조인에 새 열을 추가 하는 경우 해당 데이터 반환 된 ViewModel에 동적으로 추가 됩니다. 이 방법에 대 한 응답으로이 디자인 방법은 보다 유연 하 고 변경 내용의 허용 하는 기본 데이터 모델에 대 한 업데이트는 쿼리를 수정 하 필요성이 줄어듭니다.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
@"SELECT o.[Id] as ordernumber,
o.[OrderDate] as [date],os.[Name] as [status],
SUM(oi.units*oi.unitprice) as total
FROM [ordering].[Orders] o
LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
  }
}
```

중요 한 점은 동적 형식을 사용 하 여 반환 된 데이터 컬렉션을 동적으로 어셈블됩니다 ViewModel으로 보여 줍니다.

대부분의 쿼리에서 간단 하 고 생산성을 코딩 하는 한 DTO 또는 ViewModel 클래스를 미리 정의할 필요가 없습니다. 그러나 Viewmodel 계약으로 좀 더 제한 된 정의 갖도록 하려는 경우 (예: 미리 정의 된 Dto) Viewmodel을 미리 정의할 수 있습니다.

#### <a name="additional-resources"></a>추가 리소스

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julie Lerman 합니다. 데이터 요소-Dapper, Entity Framework 및 하이브리드 앱 (Mag. MSDN 문서)**

    *https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*


>[!div class="step-by-step"]
[이전] (eshoponcontainers-cqrs-ddd-microservice.md) [다음] (ddd-지향-microservice.md)
