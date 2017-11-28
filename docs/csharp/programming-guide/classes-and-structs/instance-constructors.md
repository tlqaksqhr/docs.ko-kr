---
title: "인스턴스 생성자(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: efb82128ffc27a7c065d2ba12bfc08396d3b5cf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="aa632-102">인스턴스 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="aa632-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="aa632-103">인스턴스 생성자는 [new](../../../csharp/language-reference/keywords/new.md) 식을 사용하여 [class](../../../csharp/language-reference/keywords/class.md)의 개체를 만들 때 인스턴스 멤버 변수를 만들고 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="aa632-104">[정적](../../../csharp/language-reference/keywords/static.md) 클래스 또는 비정적 클래스의 정적 변수를 초기화하려면 정적 생성자를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="aa632-105">자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa632-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="aa632-106">다음 예제에서는 인스턴스 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-106">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="aa632-107">이해를 돕기 위해 이 클래스에는 public 필드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-107">For clarity, this class contains public fields.</span></span> <span data-ttu-id="aa632-108">public 필드를 사용하면 어디에 있든 프로그램 내의 모든 메서드가 확인되지 않고 개체의 내부 작업에 무제한 액세스할 수 있으므로 프로그래밍 시 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-108">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="aa632-109">데이터 멤버는 일반적으로 private여야 하며, 클래스 메서드 및 속성을 통해서만 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-109">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="aa632-110">`CoOrds` 클래스를 기반으로 하는 개체를 만들 때마다 이 인스턴스 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-110">This instance constructor is called whenever an object based on the `CoOrds` class is created.</span></span> <span data-ttu-id="aa632-111">인수를 사용하지 않는 이러한 생성자를 *기본 생성자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-111">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="aa632-112">그러나 추가 생성자를 제공하는 것이 유용한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-112">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="aa632-113">예를 들어 데이터 멤버에 대한 초기 값을 지정할 수 있는 생성자를 `CoOrds` 클래스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-113">For example, we can add a constructor to the `CoOrds` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 <span data-ttu-id="aa632-114">이렇게 하면 기본 또는 특정 초기 값으로 `CoOrd` 개체를 다음과 같이 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-114">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 <span data-ttu-id="aa632-115">클래스에 생성자가 없는 경우 기본 생성자가 자동으로 생성되고 개체 필드를 초기화하는 데 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-115">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="aa632-116">예를 들어 [int](../../../csharp/language-reference/keywords/int.md)가 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-116">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="aa632-117">기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa632-117">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="aa632-118">따라서 `CoOrds` 클래스 기본 생성자는 모든 데이터 멤버를 0으로 초기화하기 때문에 클래스의 작동 방식을 변경하지 않고 완전히 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-118">Therefore, because the `CoOrds` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="aa632-119">여러 생성자를 사용하는 전체 예제는 이 항목의 뒷부분에 있는 예제 1에서 제공되고, 자동으로 생성된 생성자의 예는 예제 2에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-119">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="aa632-120">인스턴스 생성자를 사용하여 기본 클래스의 인스턴스 생성자를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-120">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="aa632-121">클래스 생성자는 다음과 같이 이니셜라이저를 통해 기본 클래스의 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-121">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 <span data-ttu-id="aa632-122">이 예제에서 `Circle` 클래스는 `Circle`이 파생되는 `Shape`에서 제공하는 생성자에 반경과 높이를 나타내는 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-122">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="aa632-123">`Shape` 및 `Circle`을 사용하는 전체 예제는 이 항목에서 예제 3으로 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-123">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="aa632-124">예제 1</span><span class="sxs-lookup"><span data-stu-id="aa632-124">Example 1</span></span>  
 <span data-ttu-id="aa632-125">다음 예제에서는 인수 없는 클래스 생성자와 두 개의 인수를 사용하는 클래스 생성자가 있는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-125">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="aa632-126">예제 2</span><span class="sxs-lookup"><span data-stu-id="aa632-126">Example 2</span></span>  
 <span data-ttu-id="aa632-127">이 예제에서 `Person` 클래스에는 생성자가 없으며, 기본 생성자가 자동으로 제공되고 필드는 해당 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-127">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 <span data-ttu-id="aa632-128">`age`의 기본값은 `0`이고, `name`의 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-128">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="aa632-129">기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa632-129">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="aa632-130">예제 3</span><span class="sxs-lookup"><span data-stu-id="aa632-130">Example 3</span></span>  
 <span data-ttu-id="aa632-131">다음 예제에서는 기본 클래스 이니셜라이저를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="aa632-132">`Circle` 클래스는 제네릭 클래스 `Shape`에서 파생되고, `Cylinder` 클래스는 `Circle` 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="aa632-133">각 파생 클래스의 생성자는 해당 기본 클래스 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa632-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 <span data-ttu-id="aa632-134">기본 클래스 생성자 호출에 대한 추가 예제는 [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), [base](../../../csharp/language-reference/keywords/base.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa632-134">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa632-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa632-135">See Also</span></span>  
 [<span data-ttu-id="aa632-136">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="aa632-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="aa632-137">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="aa632-137">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="aa632-138">생성자</span><span class="sxs-lookup"><span data-stu-id="aa632-138">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="aa632-139">종료자</span><span class="sxs-lookup"><span data-stu-id="aa632-139">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [<span data-ttu-id="aa632-140">static</span><span class="sxs-lookup"><span data-stu-id="aa632-140">static</span></span>](../../../csharp/language-reference/keywords/static.md)
