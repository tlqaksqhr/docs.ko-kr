---
title: 열거형 형식 대신 열거형 클래스 사용
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 열거형 형식 대신 열거형 클래스 사용
keywords: Docker, 마이크로 서비스, ASP.NET, 컨테이너
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9df8dc3373930d38bf9f53e9c3a9e986156d3d89
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="0b075-104">열거형 형식 대신 열거형 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="0b075-104">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="0b075-105">[열거형](../../../../docs/csharp/language-reference/keywords/enum.md)(또는 줄여서 *열거형 형식*)은 정수 형식에 대한 씬 언어 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-105">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="0b075-106">닫힌 값 집합에서 값을 저장하는 경우 해당 사용을 제한해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="0b075-107">성별(예: 남성, 여성, 알 수 없음) 또는 크기(작음, 중간, 큼)에 따른 분류는 좋은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-107">Classification based on gender (for example, male, female, unknown) or sizes (small, medium, large) are good examples.</span></span> <span data-ttu-id="0b075-108">제어 흐름 또는 추가 추상화에 열거형을 사용하는 것은 [코드 스멜](http://deviq.com/code-smells/)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="0b075-109">이 형식으로 사용하면 열거형의 값을 확인하는 여러 제어 흐름 문을 사용하여 취약한 코드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-109">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="0b075-110">대신 개체 지향 언어의 모든 풍부한 기능을 활성화하는 열거형 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="0b075-111">그러나 중요한 항목은 아니며 대부분의 경우에 간단한 설명을 위해 기본 설정된 기본 [열거형 형식](../../../../docs/csharp/language-reference/keywords/enum.md)을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-111">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="0b075-112">열거형 기본 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="0b075-112">Implementing an Enumeration base class</span></span>

<span data-ttu-id="0b075-113">다음 예제와 같이 eShopOnContainers의 마이크로 서비스를 정렬하면 샘플 열거형 기본 클래스 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

<span data-ttu-id="0b075-114">엔터티 또는 값 개체에서 이 클래스를 다음 CardType 열거형 클래스와 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b075-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }

    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a><span data-ttu-id="0b075-115">추가 자료</span><span class="sxs-lookup"><span data-stu-id="0b075-115">Additional resources</span></span>

-   <span data-ttu-id="0b075-116">**열거형을 의심할 것 - 업데이트**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="0b075-116">**Enum’s are evil—update**
[*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="0b075-117">**Daniel Hardman 열거형이 질병을 전파하는 방법 - 및 질병 치료 방법**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="0b075-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="0b075-118">**Jimmy Bogard. 열거형 클래스**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="0b075-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="0b075-119">**Steve Smith. C#의 열거형 옵션**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="0b075-119">**Steve Smith. Enum Alternatives in C#**
[*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="0b075-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="0b075-120">**Enumeration.cs.**</span></span> <span data-ttu-id="0b075-121">eShopOnContainers의 기본 열거형 클래스 [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="0b075-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="0b075-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="0b075-122">**CardType.cs**.</span></span> <span data-ttu-id="0b075-123">eShopOnContainers의 샘플 열거형 클래스</span><span class="sxs-lookup"><span data-stu-id="0b075-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="0b075-124">[이전](implement-value-objects.md) [다음](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="0b075-124">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
