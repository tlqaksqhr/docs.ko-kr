---
title: "C# 버전 관리 - C# 가이드"
description: "C# 및 .NET에서 버전 관리의 작동 방식 이해"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.date: 01/08/2017
ms.topic: article
ms.prod: visual-studio-dev-14
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0b671333019c00abafcfb72533e30936f8fc6ad7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="versioning-in-c"></a><span data-ttu-id="7a8e0-104">C#으로 버전 관리</span><span class="sxs-lookup"><span data-stu-id="7a8e0-104">Versioning in C#</span></span> #

<span data-ttu-id="7a8e0-105">이 자습서에서는 .NET에서 버전 관리가 어떤 의미인지에 대해 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-105">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="7a8e0-106">또한 라이브러리의 버전을 관리할 때 및 라이브러리의 새 버전으로 업그레이드할 때 고려해야 할 요소에 대해 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-106">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of the a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="7a8e0-107">라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="7a8e0-107">Authoring Libraries</span></span>

<span data-ttu-id="7a8e0-108">공용 .NET 라이브러리를 만든 개발자라면 새로운 업데이트를 출시해야 하는 상황을 겪은 적 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-108">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="7a8e0-109">이 프로세스의 진행 방법은 기존 코드를 새 버전의 라이브러리로 원활하게 전환해야 하는 경우 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-109">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="7a8e0-110">새 릴리스를 만들 때 다음과 같은 몇 가지 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-110">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="7a8e0-111">유의적 버전</span><span class="sxs-lookup"><span data-stu-id="7a8e0-111">Semantic Versioning</span></span>

<span data-ttu-id="7a8e0-112">[유의적 버전](http://semver.org/)(줄여서 SemVer)은 특정 중요 시점 이벤트를 나타내기 위해 라이브러리의 버전에 적용되는 명명 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-112">[Semantic versioning](http://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="7a8e0-113">라이브러리에 제공하는 버전 정보를 이용해 개발자가 동일한 라이브러리의 이전 버전을 사용하는 프로젝트와의 호환성을 확인하는 것이 가장 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-113">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="7a8e0-114">SemVer에 대한 가장 기본적인 접근법은 3개 구성 요소 형식 `MAJOR.MINOR.PATCH`입니다. 여기서:</span><span class="sxs-lookup"><span data-stu-id="7a8e0-114">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>
 
* <span data-ttu-id="7a8e0-115">`MAJOR`은 호환되지 않는 API 변경 사항이 있을 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-115">`MAJOR` is incremented when you make incompatible API changes</span></span>
* <span data-ttu-id="7a8e0-116">`MINOR`는 이전 버전과 호환성 방식으로 기능을 추가할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-116">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
* <span data-ttu-id="7a8e0-117">`PATCH`는 이전 버전과 호환성 버그 수정을 만들 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-117">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="7a8e0-118">.NET 라이브러리에 버전 정보를 적용할 때 시험판 버전 등과 같은 기타 시나리오를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-118">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="7a8e0-119">이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="7a8e0-119">Backwards Compatibility</span></span>

<span data-ttu-id="7a8e0-120">라이브러리의 새 버전을 릴리스하면 이전 버전과의 호환성이 주요 관심사 중 하나가 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-120">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="7a8e0-121">이전 버전에 종속된 코드가 다시 컴파일할 때 새 버전과 작동하는 경우, 라이브러리의 새 버전은 이전 버전과 소스가 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-121">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="7a8e0-122">이전 버전을 사용하는 응용 프로그램이 다시 컴파일하지 않고도 새 버전과 작동하는 경우 라이브러리의 새 버전은 이진 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-122">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="7a8e0-123">라이브러리 이전 버전과의 호환성을 유지하고자 할 경우 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-123">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

* <span data-ttu-id="7a8e0-124">가상 메서드: 새 버전에서 가상 메서드를 가상이 아닌 상태로 만들 경우, 해당 메서드를 재정의하는 프로젝트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-124">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="7a8e0-125">여기에는 엄청난 변화가 따르므로 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-125">This is a huge breaking change and is strongly discouraged.</span></span>
* <span data-ttu-id="7a8e0-126">메서드 시그니처: 메서드 동작 업데이트 시 시그니처도 변경해야 하는 경우, 해당 메서드에 대한 코드 호출이 계속 작동하도록 오버로드를 대신 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-126">Method signatures: When updating a method behaviour requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="7a8e0-127">구현의 일관성이 유지되도록 항상 이전 메서드 시그니처를 조작하여 새 메서드 시그니처를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-127">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
* <span data-ttu-id="7a8e0-128">[Obsolete 특성](programming-guide/concepts/attributes/common-attributes.md#Obsolete): 사용되지 않는 클래스 또는 클래스 멤버를 지정하고 이후 버전에서 제거되도록 하려면 코드에 이 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-128">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span>
<span data-ttu-id="7a8e0-129">이렇게 하면 라이브러리를 활용하는 개발자가 큰 변화에 더 잘 대비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-129">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
* <span data-ttu-id="7a8e0-130">선택적 메서드 인수: 전에는 선택 사항이었던 메서드 인수를 필수로 만들거나 기본값을 변경하는 경우, 해당 인수를 제공하지 않는 모든 코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-130">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>
> [!NOTE]
> <span data-ttu-id="7a8e0-131">필수 인수를 선택 사항으로 만드는 것은 특히 메서드의 동작을 변경하지 않을 경우 거의 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-131">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behaviour.</span></span>

<span data-ttu-id="7a8e0-132">라이브러리의 새 버전으로 업그레이드하는 방법이 쉬울수록 사용자가 더 빨리 업그레이드할 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-132">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="7a8e0-133">응용 프로그램 구성 파일</span><span class="sxs-lookup"><span data-stu-id="7a8e0-133">Application Configuration File</span></span>

<span data-ttu-id="7a8e0-134">.NET 개발자는 대부분의 프로젝트 형식에서 [`app.config` 파일](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx)을 발견할 가능성이 매우 높습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-134">As a .NET developer there's a very high chance you've encountered [the `app.config` file](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) present in most project types.</span></span>
<span data-ttu-id="7a8e0-135">이 간단한 구성 파일은 새로운 업데이트 출시를 개선하는 데 큰 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-135">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="7a8e0-136">일반적으로 라이브러리를 설계할 때 정기적으로 변경될 가능성이 있는 정보를 `app.config` 파일에 저장하도록 해야 합니다. 이렇게 하면 해당 정보가 업데이트될 때 라이브러리를 다시 컴파일하지 않고 이전 버전의 구성 파일을 새로운 파일로 바꾸기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-136">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="7a8e0-137">라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="7a8e0-137">Consuming Libraries</span></span>

<span data-ttu-id="7a8e0-138">다른 개발자가 만든 .NET 라이브러리를 사용하는 개발자는 라이브러리의 새 버전이 자신의 프로젝트와 완전히 호환되지 않을 수 있으며 그러한 변경 사항에 적응하기 위해 자신의 코드를 업데이트해야 상황에 종종 처하게 된다는 사실을 알고 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-138">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="7a8e0-139">다행히 C# 및 .NET 에코시스템에는 큰 변화가 생긴 새로운 라이브러리 버전과 작동하도록 앱을 손쉽게 업데이트할 수 있는 기능과 기술이 마련되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-139">Lucky for you C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="7a8e0-140">어셈블리 바인딩 리디렉션</span><span class="sxs-lookup"><span data-stu-id="7a8e0-140">Assembly Binding Redirection</span></span>

<span data-ttu-id="7a8e0-141">앱이 사용하는 라이브러리의 버전을 업데이트하기 위해 `app.config` 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-141">You can use the `app.config` file to update the version of a library your app uses.</span></span> <span data-ttu-id="7a8e0-142">[*바인딩 리디렉션*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx)을 추가하면 앱을 다시 컴파일하지 않고도 새 라이브러리 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-142">By adding what is called a [*binding redirect*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx) your can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="7a8e0-143">다음 예제에서는 원래 컴파일된 `1.0.0` 버전 대신 `ReferencedLibrary`의 `1.0.1` 패치 버전을 사용하도록 앱의 `app.config` 파일을 업데이트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-143">The following example shows how you would update your app's `app.config` file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="7a8e0-144">이 방법은 `ReferencedLibrary`의 새 버전이 앱과 이진 호환되는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-144">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="7a8e0-145">호환성을 결정할 때 확인해야 할 변경 사항은 위의 [이전 버전과 호환성](#backwards-compatibility) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-145">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="7a8e0-146">new</span><span class="sxs-lookup"><span data-stu-id="7a8e0-146">new</span></span>

<span data-ttu-id="7a8e0-147">상속된 기본 클래스의 멤버를 숨기려면 `new` 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-147">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="7a8e0-148">이것은 파생 클래스가 기본 클래스의 업데이트에 응답할 수 있는 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-148">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="7a8e0-149">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-149">Take the following example:</span></span>

<span data-ttu-id="7a8e0-150">[!code-csharp['new' 한정자의 샘플 사용](../../samples/csharp/versioning/new/Program.cs#sample)]</span><span class="sxs-lookup"><span data-stu-id="7a8e0-150">[!code-csharp[Sample usage of the 'new' modifier](../../samples/csharp/versioning/new/Program.cs#sample)]</span></span>

<span data-ttu-id="7a8e0-151">**Output**</span><span class="sxs-lookup"><span data-stu-id="7a8e0-151">**Output**</span></span>

```
A base method
A derived method
```

<span data-ttu-id="7a8e0-152">위의 예제에서는 `DerivedClass`가 `BaseClass`에 있는 `MyMethod` 메서드를 숨기는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-152">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="7a8e0-153">즉, 라이브러리의 새 버전에 있는 기본 클래스가 파생 클래스에 이미 있는 멤버를 추가하면 파생 클래스 멤버에 `new` 한정자를 사용하여 기본 클래스 멤버를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-153">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="7a8e0-154">`new` 한정자를 지정하지 않으면 파생 클래스는 기본 클래스에서 충돌하는 멤버를 기본적으로 숨깁니다. 컴파일러 경고가 생성되지만 코드는 여전히 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-154">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="7a8e0-155">즉, 기존 클래스에 새 멤버를 추가하기만 하면 라이브러리의 새 버전이 소스와 이진 모두 여기에 종속된 코드와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-155">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="7a8e0-156">override</span><span class="sxs-lookup"><span data-stu-id="7a8e0-156">override</span></span>

<span data-ttu-id="7a8e0-157">`override` 한정자를 사용하면 파생된 구현은 기본 클래스 멤버의 구현을 숨기는 대신 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-157">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="7a8e0-158">기본 클래스 멤버에 `virtual` 한정자를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-158">The base class member needs to have the `virtual` modifier applied to it.</span></span>

<span data-ttu-id="7a8e0-159">[!code-csharp['override' 한정자의 샘플 사용법](../../samples/csharp/versioning/override/Program.cs#sample)]</span><span class="sxs-lookup"><span data-stu-id="7a8e0-159">[!code-csharp[Sample usage of the 'override' modifier](../../samples/csharp/versioning/override/Program.cs#sample)]</span></span>

<span data-ttu-id="7a8e0-160">**Output**</span><span class="sxs-lookup"><span data-stu-id="7a8e0-160">**Output**</span></span>

```
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="7a8e0-161">`override` 한정자는 컴파일 시간에 평가되며, 재정의할 가상 멤버를 찾지 못하면 컴파일러에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-161">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="7a8e0-162">라이브러리 버전 간을 더욱 간편하게 전환하려면 여기서 설명한 방법을 익히고 어떤 상황에서 사용해야 할지를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a8e0-162">Your knowledge of the discussed techniques as well as your understanding of what situations to use them will go a long way to boost the ease of transition between versions of a library.</span></span>

