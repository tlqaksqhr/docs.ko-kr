---
title: "C# 인터페이스 - C# 언어 둘러보기"
description: "인터페이스는 C#의 형식이 구현하는 계약을 정의합니다."
keywords: ".NET, c샵, 인터페이스, 다중 상속, 다형성"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 673ac56f3f5732fcda02d313b6f4273708ae365f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="interfaces"></a><span data-ttu-id="31e59-104">인터페이스</span><span class="sxs-lookup"><span data-stu-id="31e59-104">Interfaces</span></span>

<span data-ttu-id="31e59-105">***인터페이스***는 클래스 및 구조체에서 구현될 수 있는 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-105">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="31e59-106">인터페이스는 메서드, 속성, 이벤트 및 인덱서를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-106">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="31e59-107">인터페이스는 정의하는 멤버의 구현을 제공하지 않으며 단순히 인터페이스를 구현하는 클래스 또는 구조체에서 제공해야 하는 멤버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-107">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="31e59-108">인터페이스는 ***다중 상속***을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-108">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="31e59-109">다음 예제에서 인터페이스 `IComboBox`는 `ITextBox` 및 `IListBox`를 둘 다 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-109">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

<span data-ttu-id="31e59-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span><span class="sxs-lookup"><span data-stu-id="31e59-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span></span>

<span data-ttu-id="31e59-111">클래스 및 구조체는 여러 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-111">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="31e59-112">다음 예제에서 클래스 `EditBox`는 `IControl` 및 `IDataBound`를 둘 다 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-112">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

<span data-ttu-id="31e59-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span><span class="sxs-lookup"><span data-stu-id="31e59-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span></span>

<span data-ttu-id="31e59-114">클래스 또는 구조체가 특정 인터페이스를 구현하는 경우 해당 클래스 또는 구조체의 인스턴스를 해당 인터페이스 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-114">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="31e59-115">예</span><span class="sxs-lookup"><span data-stu-id="31e59-115">For example</span></span>

<span data-ttu-id="31e59-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span><span class="sxs-lookup"><span data-stu-id="31e59-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span></span>

<span data-ttu-id="31e59-117">인스턴스가 정적으로 특정 인터페이스를 구현하는 것으로 알려지지 않은 경우 동적 형식 캐스팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-117">In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="31e59-118">예를 들어 다음 문에서는 동적 형식 캐스팅을 사용하여 개체의 `IControl` 및 `IDataBound` 인터페이스 구현을 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-118">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="31e59-119">개체의 실제 런타임 형식이 `EditBox`이므로 캐스팅은 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-119">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

<span data-ttu-id="31e59-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span><span class="sxs-lookup"><span data-stu-id="31e59-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span></span>

<span data-ttu-id="31e59-121">이전 `EditBox` 클래스에서 `IControl` 인터페이스의 `Paint` 메서드와 에서 `IDataBound` 인터페이스의 `Bind` 메서드는 공용 멤버를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-121">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="31e59-122">또한 C#에서는 명시적 ***인터페이스 멤버 구현***을 지원하여 클래스 또는 구조체가 멤버를 공용으로 만들지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-122">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="31e59-123">명시적 인터페이스 멤버 구현은 정규화된 인터페이스 멤버 이름을 사용하여 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-123">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="31e59-124">예를 들어 `EditBox` 클래스는 다음과 같이 명시적 인터페이스 멤버 구현을 사용하여 `IControl.Paint` 및 `IDataBound.Bind` 메서드를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-124">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

<span data-ttu-id="31e59-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span><span class="sxs-lookup"><span data-stu-id="31e59-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span></span>

<span data-ttu-id="31e59-126">명시적 인터페이스 멤버는 인터페이스 형식을 통해서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-126">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="31e59-127">예를 들어 이전 EditBox 클래스가 제공한 `IControl.Paint`의 구현은 먼저 `EditBox` 참조를 `IControl` 인터페이스 형식으로 변환해야만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e59-127">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

<span data-ttu-id="31e59-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span><span class="sxs-lookup"><span data-stu-id="31e59-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="31e59-129">[이전](arrays.md)
[다음](enums.md)</span><span class="sxs-lookup"><span data-stu-id="31e59-129">[Previous](arrays.md)
[Next](enums.md)</span></span>

