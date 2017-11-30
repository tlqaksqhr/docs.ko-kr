---
title: "열거형 형식 대신 열거형 클래스를 사용 하 여"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 열거형 형식 대신 열거형 클래스를 사용 하 여"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="38b5e-104">열거형 형식 대신 열거형 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="38b5e-104">Using Enumeration classes instead of enum types</span></span>

<span data-ttu-id="38b5e-105">[열거형](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*열거형* 줄여서) 정수 계열 형식에 대 한 씬 언어 래퍼로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-105">[Enumerations](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enums* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="38b5e-106">값 닫힌된 값 집합에서 값을 저장 하는 경우에 대해 그 사용을 제한 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="38b5e-107">(예를 들어, 남성의 여성, 알 수 없는), 성별 또는 크기 (S, M, L, XL)에 따라 분류는 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-107">Classification based on gender (for example, male, female, unknown), or sizes (S, M, L, XL) are good examples.</span></span> <span data-ttu-id="38b5e-108">제어 흐름 또는 보다 강력한 개념에 대 한 열거형을 사용 하는 것을 [냄새 코드](http://deviq.com/code-smells/)합니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="38b5e-109">이 유형의 사용 취약 한 코드를 열거형의 값을 확인 하는 많은 제어 흐름 문의를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-109">This type of usage will lead to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="38b5e-110">대신, 개체 지향 언어의 모든 풍부한 기능을 활성화 하는 열거형 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span> <span data-ttu-id="38b5e-111">그러나 이것은 중요 한 문제 않으며 대부분의 경우 간단한 설명을 위해 있습니다 계속 사용할 수 일반 열거형 기본 설정 된 경우.</span><span class="sxs-lookup"><span data-stu-id="38b5e-111">However, this is not a critical issue and in many cases, for simplicity, you can still use regular enums if that is your preference.</span></span>

## <a name="implementing-enumeration-classes"></a><span data-ttu-id="38b5e-112">열거형 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="38b5e-112">Implementing Enumeration classes</span></span>

<span data-ttu-id="38b5e-113">다음 예제와 같이 eShopOnContainers에 정렬 마이크로 서비스 샘플 열거형 기본 클래스 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

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

<span data-ttu-id="38b5e-114">이 클래스에서 모든 엔터티 또는 값 개체의 경우 다음 CardType 열거형 클래스와 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="38b5e-115">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="38b5e-115">Additional resources</span></span>

-   <span data-ttu-id="38b5e-116">**열거형의 악의적인는-업데이트**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="38b5e-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="38b5e-117">**이 Hardman 합니다. 열거형 질병 분산 하는 방식을-것을 치료 하기 위한 방법 및**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="38b5e-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="38b5e-118">**Jimmy Bogard. 열거형 클래스**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="38b5e-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="38b5e-119">**Steve Smith 합니다. C#에서 Enum 대체**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="38b5e-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="38b5e-120">**Enumeration.cs 합니다.**</span><span class="sxs-lookup"><span data-stu-id="38b5e-120">**Enumeration.cs.**</span></span> <span data-ttu-id="38b5e-121">기본 eShopOnContainers의 열거형 클래스 [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="38b5e-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="38b5e-122">**CardType.cs**합니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-122">**CardType.cs**.</span></span> <span data-ttu-id="38b5e-123">열거형 클래스 eShopOnContainers 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="38b5e-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="38b5e-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span><span class="sxs-lookup"><span data-stu-id="38b5e-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="38b5e-125">[이전] (구현-값-objects.md) [다음] (도메인-모델-계층-validations.md)</span><span class="sxs-lookup"><span data-stu-id="38b5e-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
