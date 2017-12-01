---
title: "값 개체를 구현합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 값 개체를 구현합니다."
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c20bc80d2ddb864a3a0172beb211974426a278a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-value-objects"></a>값 개체를 구현합니다.

에 설명한 대로 이전 섹션에서 엔터티 및 집계 하는 방법에 대 한 id는 엔터티에 대 한 기본입니다. 그러나 많은 개체 및 데이터 항목에에서 있는 id와 id 값 개체와 같은 추적 하지 않아도 되는 시스템입니다.

값 개체를 다른 엔터티를 참조할 수 있습니다. 예를 들어, 다른 한 지점에서 가져오는 방법에 설명 하는 경로 생성 하는 응용 프로그램에서에서 해당 경로 값 개체 것입니다. 특정 경로에 있는 점의 스냅숏으로 것 하지만이 제안 된 경로 id에 있지만 City도 등과 같은 엔터티를 내부적으로 참조 될 수 있습니다.

그림 9-13 순서 집계 내에서 주소 값 개체를 보여 줍니다.

![](./media/image14.png)

**그림 9-13**합니다. 값 개체 순서 집계 내에서 주소

그림 9-13에 표시 된 대로 엔터티는 여러 특성을 일반적으로 구성 됩니다. 예를 들어 주문 id가 있는 엔터티로 모델링 및 내부적으로 OrderId, OrderDate, OrderItems 등과 같은 특성의 집합으로 구성 수 있습니다. 하지만 복잡 한 값이 되는 주소에는 country, 거리, city, 구성 등의 모델링 하 고 개체를 값으로 처리 해야 합니다.

## <a name="important-characteristics-of-value-objects"></a>값 개체의 중요 한 특징

값 개체에 대 한 두 가지 주요 특성 가지가 있습니다.

-   Id를 갖게 됩니다.

-   변경할 수는 없습니다.

첫 번째 특성에서 이미 설명한 합니다. 불변성이 중요 한 요구 사항입니다. 값 개체의 값을 개체가 생성 되 면 변경 하지 않아야 합니다. 따라서 개체가 생성 될 때 필요한 값을 제공 해야 하지만 개체의 수명 동안 변경 하도록 허용 하지 않아야 합니다.

값 개체를 사용 하 여 변경할 수 없는 특성 덕분에 성능에 대 한 특정 트릭을 수행할 수 있습니다. 특히 시스템에서 같은 값을가지고 있으며이 중 대다수가 있는 수천 값의 개체 인스턴스, 합니다. 변경할 수 없는 특성; 다시 사용할 수 있습니다. 요소의 값은 동일 하 고 id가 없습니다 한 이후 사용이 가능 개체가 될 수 있습니다. 이 유형의 최적화 느리게 실행 되는 소프트웨어 및 뛰어난 성능으로는 소프트웨어 간의 차이 만들 경우에 따라 수 있습니다. 물론, 이러한 모든 경우의 응용 프로그램 환경에 배포 컨텍스트에 따라 달라 집니다.

## <a name="value-object-implementation-in-c"></a>C에서 값 개체 구현\#

구현 측면에서 같음 (값 개체를 id에 따라 다 해야) 이후 모든 특성 및 다른 기본 특성에 대 한 비교와 같은 기본 유틸리티 메서드를 가진 값 개체 기본 클래스를 사용할 수 있습니다. 다음 예제에서는 eShopOnContainers에서 정렬 마이크로 서비스에 사용 된 값 개체 기본 클래스를 보여 줍니다.

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }
    // Other utilility methods
}
```

다음 예제에 표시 된 주소 값 개체와 마찬가지로 실제 값 개체를 구현 하는 경우이 클래스를 사용할 수 있습니다.

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address(string street, string city, string state,
        string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a>EF Core를 사용 하 여 값 개체를 유지 하는 경우 identity 특성 숨기기

때 EF 코어를 사용 하 여 현재 버전 (EF 코어 1.1)에 사용할 수 없다는 제한이 [복합 형식을](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) EF에 정의 된 대로 6.x 합니다. 따라서 EF 엔터티를 값 개체를 저장 해야 합니다. 그러나 id의 일부인 값 개체 모델에서 중요 하지 않습니다 명확히 있으므로 해당 ID를 숨길 수 있습니다. ID를 숨기려면 섀도 속성으로 ID를 사용 하는 것입니다. 모델의 ID를 숨기 거 대 한 해당 구성을 인프라 수준에서 설치 되 면 이후 도메인 모델에 대 한 투명 하 게 됩니다 및 인프라 구현 나중에 변경할 수 없습니다.

EShopOnContainers, EF 핵심 인프라에 필요한 숨겨진된 ID는 Fluent API를 사용 하 여 인프라 프로젝트에 DbContext 수준에 있는 다음과 같은 방식으로 구현 됩니다.

```csharp
// Fluent API within the OrderingContext:DbContext in the
// Ordering.Infrastructure project

void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

따라서 ID는 도메인 모델의 관점에서 숨겨지는지를 나중에 값 개체 인프라 구현할 수도 복합 형식 또는 다른 방법으로.

## <a name="additional-resources"></a>추가 리소스

-   **Martin Fowler. ValueObject 패턴**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Eric Evans. 도메인 기반 디자인: 소프트웨어 핵심에서 복잡성을 다루는 합니다.** (예약; 값 개체에 설명) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Vaughn Vernon. 도메인 기반 디자인을 구현 합니다.** (예약; 값 개체에 설명) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **그림자 속성이**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)

-   **복합 형식 및/또는 값 개체**합니다. EF 코어 GitHub 리포지토리 (문제 탭)의 설명을 [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)

-   **ValueObject.cs 합니다.** EShopOnContainers 기준 값 개체 클래스입니다.
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   **클래스를 해결 합니다.** EShopOnContainers의 샘플 값의 개체 클래스입니다.
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
[이전] [다음] (열거형-클래스-over-enum-types.md) (seedwork-domain-model-base-classes-interfaces.md)
