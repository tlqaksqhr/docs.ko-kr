---
title: "Seedwork (다시 사용할 수 있는 기본 클래스와 인터페이스 도메인 모델에 대해)"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Seedwork (다시 사용할 수 있는 기본 클래스와 인터페이스 도메인 모델에 대해)"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="ed3c1-104">Seedwork (다시 사용할 수 있는 기본 클래스와 인터페이스 도메인 모델에 대해)</span><span class="sxs-lookup"><span data-stu-id="ed3c1-104">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="ed3c1-105">솔루션 폴더에 포함 되어는 *SeedWork* 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-105">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="ed3c1-106">*SeedWork* 폴더 도메인 엔터티 및 값 개체에 대 한 기본으로 사용할 수 있는 사용자 지정 기본 클래스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-106">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="ed3c1-107">각 도메인의 개체 클래스에 대 한 중복 번호가 있으므로 이러한 기본 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-107">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="ed3c1-108">이러한 유형의 클래스에 대 한 폴더 라고 *SeedWork* 와 하지 것 같은 *프레임 워크*합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-108">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="ed3c1-109">호출 될 *SeedWork* 폴더에는 작은 하위 집합만 실제로 간주할 수 없습니다. 프레임 워크는 다시 사용할 수 있는 클래스를 포함 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-109">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="ed3c1-110">*Seedwork* 으로 도입 하는 용어 [Michael 페더](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) 하 여 알려진 및 [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) 공통, SharedKernel, 해당 폴더의 이름을 수도 있지만 또는 유사한 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-110">*Seedwork* is a term introduced by [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="ed3c1-111">그림 9-12 도메인 모델 seedwork 정렬 마이크로 서비스에서 구성 하는 클래스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-111">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="ed3c1-112">엔터티와 ValueObject, 열거형, 같은 몇 가지 사용자 지정 기본 클래스와 몇 가지 인터페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-112">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="ed3c1-113">이러한 인터페이스 (IRepository 및 IUnitOfWork) 구현 되어야 하는 사항에 대 한 인프라 계층을 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-113">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="ed3c1-114">이러한 인터페이스 에서도 종속성 주입을 통해 응용 프로그램 계층에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-114">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="ed3c1-115">**그림 9-12**합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-115">**Figure 9-12**.</span></span> <span data-ttu-id="ed3c1-116">샘플은 도메인 모델 "seedwork"에 대 한 기본 클래스와 인터페이스의 설정</span><span class="sxs-lookup"><span data-stu-id="ed3c1-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="ed3c1-117">대부분의 개발자는 정식 프레임 워크 하지 프로젝트 간에 공유 하는 재사용을 복사 및 붙여넣기의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="ed3c1-118">모든 레이어 또는 라이브러리의 seedworks가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="ed3c1-119">그러나 클래스 및 인터페이스 집합을 가져오는 충분히 큰 경우 단일 클래스 라이브러리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="ed3c1-120">사용자 지정 엔터티 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="ed3c1-120">The custom Entity base class</span></span>

<span data-ttu-id="ed3c1-121">다음 코드는 모든 도메인 엔터티에서 엔터티 ID와 같은 동일한 방식으로 사용할 수 있는 코드를 배치할 수 있는 엔터티는 기본 클래스의 예는 [같음 연산자](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)등입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etc.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }
  
    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="ed3c1-122">도메인 모델 계층에서 리포지토리 계약 (인터페이스)</span><span class="sxs-lookup"><span data-stu-id="ed3c1-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="ed3c1-123">리포지토리 계약은 단순히 각 집계에 사용할 저장소의 계약 요구를 표현 하는.NET 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> <span data-ttu-id="ed3c1-124">EF 핵심 코드 또는 모든 기타 인프라 종속성과 함께 코드를 자체에 있는 저장소, 도메인 모델 내에서 구현 되어야 합니다. 저장소 정의 하는 인터페이스를 구현만 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code, must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span>

<span data-ttu-id="ed3c1-125">이 연습 (도메인 모델 계층에서 리포지토리 인터페이스를 배치)와 관련 된 패턴은 구분 인터페이스 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="ed3c1-126">으로 [설명](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) 으로 Martin Fowler "하나에 인터페이스를 정의 하려면 사용 하 여 구분 인터페이스 패키지 하지만 다른 구현.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-126">As [explained](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="ed3c1-127">이러한 방식으로 클라이언트에 필요한 인터페이스에 대 한 종속성 수 인식할 수 없습니다 완전히 구현 합니다. "</span><span class="sxs-lookup"><span data-stu-id="ed3c1-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="ed3c1-128">구분 된 인터페이스 패턴 사용 하도록 설정할 수에 (이 경우는 마이크로 서비스에 대 한 웹 API 프로젝트) 응용 프로그램 계층에는 도메인 모델에 정의 된 요구 사항에 대 한 종속성 있지만 인프라/지 속성에 직접 종속성 하지 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="ed3c1-129">인프라에서 구현 되는 구현을 격리 하 종속성 주입을 사용할 수는 또한 지 속성 계층 저장소를 사용 하 여 / 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="ed3c1-130">예를 들어 IOrderRepository 인터페이스와 다음 예제에서는 작업 OrderRepository 클래스 인프라 계층에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="ed3c1-131">응용 프로그램의 현재 구현에서 코드 하기만 쿼리는 주문 업데이트를 확인 하 고 CQS 접근 방식을 구현 되지 않은 분할 다음 이후 데이터베이스에 순서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3c1-131">In the current implementation of the application, the code just needs to add the order to the database, since queries are split following the CQS approach, and updates to orders are not implemented.</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="ed3c1-132">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="ed3c1-132">Additional resources</span></span>

-   <span data-ttu-id="ed3c1-133">**Martin Fowler. 분리 된 인터페이스입니다. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span><span class="sxs-lookup"><span data-stu-id="ed3c1-133">**Martin Fowler. Separated Interface.**
[*http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ed3c1-134">[이전] (net-코어-마이크로 서비스-도메인-model.md) [다음] (구현 값 objects.md)</span><span class="sxs-lookup"><span data-stu-id="ed3c1-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
