---
title: .NET Core를 사용하여 마이크로 서비스 도메인 모델 구현
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | .NET Core로 마이크로 서비스 도메인 모델 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/09/2017
ms.openlocfilehash: e0c931405b8b7e3b52bdcbd511737b449dc74273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="3e73f-103">.NET Core를 사용하여 마이크로 서비스 도메인 모델 구현</span><span class="sxs-lookup"><span data-stu-id="3e73f-103">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="3e73f-104">이전 섹션에서는 도메인 모델 설계을 위한 기본 설계 원칙과 패턴을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-104">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="3e73f-105">이제.NET Core 및 EF Core(일반 C\# 코드)를 사용하여 도메인 모델을 구현할 수 있는 방법을 탐색할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-105">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="3e73f-106">도메인 모델은 코드를 통해 간단하게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-106">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="3e73f-107">EF Core 모델 요구 사항은 있지만 실제로 EF에 대한 종속성은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-107">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="3e73f-108">EF Core나 도메인 모델의 다른 ORM에 대한 강도 높은 종속성이나 참조는 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-108">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="3e73f-109">사용자 지정 .NET 표준 라이브러리의 도메인 모델 구조</span><span class="sxs-lookup"><span data-stu-id="3e73f-109">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="3e73f-110">eShopOnContainers 참조 응용 프로그램에 사용되는 폴더 조직에서는 응용 프로그램에 대한 DDD 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-110">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="3e73f-111">다른 폴더 구조가 응용 프로그램에 대해 선택한 설계와 더 분명하게 커뮤니케이션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-111">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="3e73f-112">그림 9-10에서 보듯 주문 도메인 모델에는 주문 집계와 구매자 집계 등의 두 가지 집계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-112">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="3e73f-113">단일 도메인 개체로 구성된 집계를 가질 수도 있지만(집계 루트 또는 루트 엔터티) 각 집계는 도메인 엔터티 및 값 개체의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-113">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="3e73f-114">**그림 9-10**.</span><span class="sxs-lookup"><span data-stu-id="3e73f-114">**Figure 9-10**.</span></span> <span data-ttu-id="3e73f-115">eShopOnContainers에서 주문 마이크로 서비스의 도메인 모델</span><span class="sxs-lookup"><span data-stu-id="3e73f-115">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="3e73f-116">또한 도메인 모델 계층에는 도메인 모델의 인프라 요구 사항인 저장소 계약(인터페이스)가 포함된 도메인 모델 계층이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-116">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="3e73f-117">다시 말해 이 인터페이스는 인프라 계층이 구현해야 하는 저장소와 그 방법을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-117">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="3e73f-118">도메인 모델 계층이 Entity Framework와 같은 인프라 기술의 API나 클래스에 의해 "오염"되지 않게 도메인 모델계층의 외부에 저장소 구현을 배치하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-118">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="3e73f-119">도메인 엔터티 및 값 개체에 대한 기본으로 사용할 수 있는 사용자 지정 기본 클래스가 포함된 [SeedWork](https://martinfowler.com/bliki/Seedwork.html) 폴더도 참조할 수 있으므로 각각의 도메인 개체 클래스에서 코드가 중복되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-119">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="3e73f-120">사용자 지정 .NET 표준 라이브러리의 집계 구조</span><span class="sxs-lookup"><span data-stu-id="3e73f-120">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="3e73f-121">집계란 트랜잭션 일관성에 부합하도록 함께 그룹화된 도메인 개체의 클러스터를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-121">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="3e73f-122">이러한 개체는 엔터티의 인스턴스(집계 루트 또는 루트 엔터티 중 하나)와 다른 추가적인 값 개체가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-122">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="3e73f-123">트랜잭션 일관성이란 집계가 비즈니스 동작의 마지막까지 일관되고 최신인 상태를 유지하도록 보장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-123">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="3e73f-124">예를 들어, eShopOnContainers 주문 마이크로 서비스 도메인 모델의 주문 집계는 그림 9-11처럼 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-124">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="3e73f-125">**그림 9-11**.</span><span class="sxs-lookup"><span data-stu-id="3e73f-125">**Figure 9-11**.</span></span> <span data-ttu-id="3e73f-126">Visual Studio 솔루션의 주문 집계</span><span class="sxs-lookup"><span data-stu-id="3e73f-126">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="3e73f-127">집계 폴더의 아무 파일이나 열면 [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) 폴더에서 구현된 것처럼 엔터티나 값 개체처럼 사용자 지정 클래스 또는 인터페이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-127">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="3e73f-128">POCO 클래스로 도메인 엔터티 구현</span><span class="sxs-lookup"><span data-stu-id="3e73f-128">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="3e73f-129">도메인 엔터티를 구현하는 POCO 클래스를 만들어 .NET에서 도메인 모델을 구현합니다. </span><span class="sxs-lookup"><span data-stu-id="3e73f-129">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="3e73f-130">다음 예제에서는 Order 클래스가 엔터티 및 집계 루트로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-130">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="3e73f-131">Order 클래스는 엔터티 기본 클래스에서 파생되므로 엔터티와 관련한 공통 코드를 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-131">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="3e73f-132">이러한 기본 클래스 및 인터페이스는 사용자가 도메인 모델 프로젝트에서 정의하므로 EF 같은 ORM의 인프라 코드가 아니라 사용자 본인의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-132">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 2.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId;

    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    private string _description;
    private int? _paymentMethodId;

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;
  
    public Order(string userId, Address address, int cardTypeId, string cardNumber, string cardSecurityNumber,
            string cardHolderName, DateTime cardExpiration, int? buyerId = null, int? paymentMethodId = null)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.Submitted.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;

        // ...Additional code ...
    }

    public void AddOrderItem(int productId, string productName, 
                            decimal unitPrice, decimal discount, 
                            string pictureUrl, int units = 1)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...

        var orderItem = new OrderItem(productId, productName, unitPrice, discount, pictureUrl, units);
        
        _orderItems.Add(orderItem);
  
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

<span data-ttu-id="3e73f-133">이것은 POCO 클래스로 구현되는 도메인 엔터티라는 점에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-133">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="3e73f-134">Entity Framework Core나 기타 인프라 프레임워크에 대한 직접적인 종속성은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-134">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="3e73f-135">이 구현은 도메인 모델을 구현하는 C\#처럼 DDD여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-135">This implementation is as it should be in DDD, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="3e73f-136">또한 클래스에는 이름이 IAggregateRoot인 인터페이스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-136">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="3e73f-137">이 인터페이스는 빈 인터페이스로, *마커 인터페이스*라고도 불립니다. 즉 해당 엔터티 클래스도 집계 루트임을 표시하는 데만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-137">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="3e73f-138">마커 인터페이스는 가끔 안티 패턴으로도 간주되나 특이 인터페이스가 확장될 가능성이 있을 때 클래스를 표시하는 분명한 방법이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-138">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="3e73f-139">특성은 마커의 대안이 될 수 있지만 클래스 위에 Aggregate 특성 마커를 놓는 것보다는 IAggregate 인터페이스 옆에 기준 클래스(Entity)를 놓는 것이 더 빨리 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-139">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="3e73f-140">원하는 것을 선택하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-140">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="3e73f-141">집계 루트가 있으면 집계 엔터티의 일관성 및 비즈니스 규칙과 관련한 대부분의 코드가 Order 집계 루트 클래스의 메서드로 구현되어야 합니다(예를 들어 OrderItem 개체를 집계에 추가할 때는 AddOrderItem).</span><span class="sxs-lookup"><span data-stu-id="3e73f-141">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="3e73f-142">OrderItems 개체를 직접 또는 간접적으로 만들거나 업데이트하면 안 됩니다. AggregateRoot 클래스는 자식 엔터티에 대한 모든 업데이트 작업의 제어와 일관성을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-142">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

## <a name="encapsulating-data-in-the-domain-entities"></a><span data-ttu-id="3e73f-143">도메인 엔터티에서 데이터 캡슐화 </span><span class="sxs-lookup"><span data-stu-id="3e73f-143">Encapsulating data in the Domain Entities</span></span>

<span data-ttu-id="3e73f-144">엔터티 모델의 일반적인 문제는 공개적으로 액세스 가능한 목록 유형에 컬렉션 탐색 속성을 노출한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-144">A common problem in entity models is that they expose collection navigation properties as publicly accessible list types.</span></span> <span data-ttu-id="3e73f-145">따라서 협력 개발자가 이 컬렉션 유형의 콘텐츠를 조작하여 컬렉션과 관련한 중요한 비즈니스 규칙을 무시할 수 있고 이에 따라 개체가 무효한 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-145">This allows any collaborator developer to manipulate the contents of these collection types, which may bypass important business rules related to the collection, possibly leaving the object in an invalid state.</span></span> <span data-ttu-id="3e73f-146">이 문제에 대한 해결 방법은 관련 컬렉션에 대해 읽기 전용 액세스만을 노출하고 명시적으로 클라이언트가 이를 조작할 수 있는 방법을 정의하는 메서드를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-146">The solution to this is to expose read-only access to related collections and explicitly provide methods that define ways in which clients can manipulate them.</span></span>

<span data-ttu-id="3e73f-147">앞의 코드에서는 많은 속성이 읽기 전용이거나 비공개이며 클래스 메서드를 통해서만 업데이트 가능하므로 모든 업데이트에서 비즈니스 도메인 고정 항목과 클래스 메서드 내에서 명시한 논리를 고려하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-147">In the previous code, note that many attributes are read-only or private and are only updatable by the class methods, so any update takes into account business domain invariants and logic specified within the class methods.</span></span>

<span data-ttu-id="3e73f-148">예를 들어 다음 DDD 패턴에서는 명령 처리기 메서드나 응용 프로그램 계층 클래스에서 다음을 수행해서는 *안 됩니다*.</span><span class="sxs-lookup"><span data-stu-id="3e73f-148">For example, following DDD patterns, you should *not* do the following from any command handler method or application layer class:</span></span>

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

<span data-ttu-id="3e73f-149">이 경우 Add 메서드는 순전히 OrderItems 컬렉션에 대한 직접 액세스를 통해 데이터를 추가하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-149">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="3e73f-150">따라서 자식 엔터티를 통해 해당 작업과 관련된 대부분의 도메인 논리, 규칙 또는 유효성 검사는 응용 프로그램 계층 전체에 고르게 퍼집니다(명령 처리기 및 Web API 컨트롤러).</span><span class="sxs-lookup"><span data-stu-id="3e73f-150">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="3e73f-151">집계 루트를 우회하면 집계 루트가 고정, 유효성 또는 일관성을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-151">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="3e73f-152">결국 복잡한 코드나 트랜잭션 스크립트 코드가 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-152">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="3e73f-153">DDD 패턴을 따르려면 어떤 엔터티 속성에도 엔터티에 공개 Setter가 있어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-153">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="3e73f-154">엔터티의 변경 내용은 엔터티에서 수행하는 변경 내용에 대해 유비쿼터스 언어를 통해 명시적 메서드에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-154">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="3e73f-155">나아가 엔터티 내 컬렉션(예: 주문 항목)은 읽기 전용 속성이어야 합니다(나중에 설명하는 AsReadOnly 메서드).</span><span class="sxs-lookup"><span data-stu-id="3e73f-155">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="3e73f-156">집계 루트 클래스 메서드 또는 자식 엔터티 메서드 내에서만 업데이트할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-156">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="3e73f-157">주문 집계 루트에 대한 코드에서 볼 수 있듯이 엔터티 데이터나 자식 엔터티에 대한 모든 작업이 엔터티 클래스의 메서드를 통해서만 수행되도록 모든 Setter는 외부적으로 비공개이거나 최소한 읽기 전용이어야 합니다. </span><span class="sxs-lookup"><span data-stu-id="3e73f-157">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="3e73f-158">이렇게 하면 트랜잭션 스크립트 코드 구현보다는 제어되는 개체 중심 방식으로 일관성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-158">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="3e73f-159">다음 코드 조각에서는 주문 집계에 OrderItem 개체를 추가하는 데 적합한 코딩을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-159">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="3e73f-160">이 코드 조각에서 OrderItem 개체 생성과 관련한 대부분의 유효성 검사 또는 논리는 AddOrderItem 메서드에서 Order 집계 루트의 제어 하에 있습니다. 특히 집계의 다른 요소와 관련한 유효성 검사 및 논리가 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-160">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="3e73f-161">예를 들어, AddOrderItem을 여러 번 호출하면 동일한 제품 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-161">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="3e73f-162">이 메서드에서는 제품 항목을 검토하고 동리한 제품 항목을 여러 단위가 있는 단일 OrderItem 개체에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-162">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="3e73f-163">또한 할인 금액은 서로 다르지만 제품 ID가 같다면 더 높은 할인을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-163">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="3e73f-164">이 원칙은 OrderItem 개체에 대한 다른 도메인 논리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-164">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="3e73f-165">또한 새 OrderItem(params) 작업도 Order 집계 루트의 AddOrderItem 메서드에서 제어 및 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-165">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="3e73f-166">따라서 이 작업과 관련한 대부분의 논리 또는 유효성 검사(특히 다른 자식 엔터티 간의 일관성에 영향을 미치는 모든 항목)는 집계 루트 안의 단일 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-166">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="3e73f-167">이것이 집계 루트 패턴의 최종 목적입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-167">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="3e73f-168">Entity Framework Core 1.1 이상을 사용하면 속성 외에도 [필드에 매핑](https://docs.microsoft.com/ef/core/modeling/backing-field)을 지원하므로 DDD 엔터티가 더 잘 표현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-168">When you use Entity Framework Core 1.1 or later, a DDD entity can be better expressed because it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="3e73f-169">이것은 자식 엔터티 또는 값 개체의 컬렉션을 보호할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-169">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="3e73f-170">이 향상을 통해 속성 대신 간단한 비공개 필드를 사용하고 공개 메서드 안에서 필드 컬렉션에 대한 모든 업데이트를 구현하며 AsReadOnly 메서드를 통해 읽기 전용 액세스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-170">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="3e73f-171">DDD에서는 데이터의 고정 및 일관성을 제어하기 위해 엔터티(또는 생성자)의 메서드를 통해서만 엔터티를 업데이트하려 하므로 속성은 get 접근자를 통해서만 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-171">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="3e73f-172">속성은 비공개 필드를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-172">The properties are backed by private fields.</span></span> <span data-ttu-id="3e73f-173">비공개 멤버는 클래스 안에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-173">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="3e73f-174">그러나 한 가지 예외가 있는데 EF Core도 이 필드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-174">However, there one exception: EF Core needs to set these fields as well.</span></span>


### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="3e73f-175">데이터베이스 테이블의 필드에 대한 get 접근자와만 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="3e73f-175">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="3e73f-176">데이터베이스 테이블 열에 속성을 매핑하는 것은 도메인의 업무가 아니라 인프라 및 지속성 계층의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-176">Mapping properties to database table columns is not a domain responsibility but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="3e73f-177">여기서는 엔터티 모델링 방법과 관련하여 EF Core 1.1의 새로운 기능을 인지하는 정도로만 해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-177">We mention this here just so you are aware of the new capabilities in EF Core 1.1 or later related to how you can model entities.</span></span> <span data-ttu-id="3e73f-178">이 항목에 대한 추가 정보는 인프라 및 지속성 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-178">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="3e73f-179">EF Core 1.0을 사용할 경우 DbContext 안에서 getter를 통해서만 정의된 속성을 데이터베이스 테이블의 실제 필드에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-179">When you use EF Core 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="3e73f-180">이 작업은 PropertyBuilder 클래스의 HasField 메서드를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-180">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="3e73f-181">속성 없이 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="3e73f-181">Mapping fields without properties</span></span>

<span data-ttu-id="3e73f-182">EF Core 1.1 이상의 기능을 사용하여 열을 필드에 매핑하면 속성을 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-182">With the feature in EF Core 1.1 or later to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="3e73f-183">대신 테이블의 열을 필드에 매핑하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-183">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="3e73f-184">엔터티 외부에서 액세스할 필요가 없는 내부 상태에 대한 비공개 필드가 대표적인 사용 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-184">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="3e73f-185">예를 들어 앞의 OrderAggregate 코드 예제에는 `_paymentMethodId` 필드 같이 setter나 getter에 대한 관련 속성이 없는 몇 가지 비공개 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-185">For example, in the preceding OrderAggregate code example, there are several private fields, like the  `_paymentMethodId` field, that have no related property for either a setter or getter.</span></span> <span data-ttu-id="3e73f-186">해당 필드도 주문의 비즈니스 논리 안에서 산출되어 주문의 메서드에서 사용될 수 있지만 데이터베이스 안에서도 지속되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-186">That field could also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="3e73f-187">이 때문에 EF Core(v1.1 이후)에서는 관련 속성 없이 데이터베이스의 열에 필드를 매핑하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-187">So in EF Core (since v1.1) there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="3e73f-188">이것도 본 가이드의 [인프라 계층](#the-infrastructure-layer) 에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e73f-188">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e73f-189">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3e73f-189">Additional resources</span></span>

-   <span data-ttu-id="3e73f-190">**Vaughn Vernon. DDD 및 Entity Framework를 사용한 집계 모델링**</span><span class="sxs-lookup"><span data-stu-id="3e73f-190">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="3e73f-191">이것은 Entity Framework Core가 *아닙니다*.</span><span class="sxs-lookup"><span data-stu-id="3e73f-191">Note that this is *not* Entity Framework Core.</span></span>
    [*https://vaughnvernon.co/?p=879*](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="3e73f-192">**Julie Lerman. 도메인 기반 디자인의 코딩: 데이터 중심 개발을 위한 팁**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e73f-192">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="3e73f-193">**Udi Dahan. 완벽하게 캡슐화된 도메인 모델을 만드는 방법**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="3e73f-193">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3e73f-194">[이전] (microservice-domain-model.md) [다음t] (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="3e73f-194">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>
