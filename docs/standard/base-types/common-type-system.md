---
title: "심층 공용 형식 시스템"
description: "심층 공용 형식 시스템"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b5482a1d-7bdc-40fe-aa45-10df930ceb5b
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6be672acc84a76106e25b82574acad16beb4a8ac
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="common-type-system-in-depth"></a><span data-ttu-id="71c31-104">심층 공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="71c31-104">Common type system in depth</span></span>

<span data-ttu-id="71c31-105">이 항목은 공용 형식 시스템을 자세히 설명하는 다음 섹션으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-105">This topic contains the following sections that explore the common type system in depth:</span></span>

* [<span data-ttu-id="71c31-106">.NET의 형식</span><span class="sxs-lookup"><span data-stu-id="71c31-106">Types in .NET</span></span>](#types-in-net)

* [<span data-ttu-id="71c31-107">형식 정의</span><span class="sxs-lookup"><span data-stu-id="71c31-107">Type definitions</span></span>](#type-definitions)

* [<span data-ttu-id="71c31-108">형식 멤버</span><span class="sxs-lookup"><span data-stu-id="71c31-108">Type members</span></span>](#type-members)

* [<span data-ttu-id="71c31-109">형식 멤버의 특성</span><span class="sxs-lookup"><span data-stu-id="71c31-109">Characteristics of type members</span></span>](#characteristics-of-type-members)


## <a name="types-in-net"></a><span data-ttu-id="71c31-110">.NET의 형식</span><span class="sxs-lookup"><span data-stu-id="71c31-110">Types in .NET</span></span>

<span data-ttu-id="71c31-111">.NET의 모든 형식은 값 형식 또는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-111">All types in .NET are either value types or reference types.</span></span> 

<span data-ttu-id="71c31-112">값 형식은 해당 형식의 개체가 개체의 실제 값으로 나타나는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-112">Value types are data types whose objects are represented by the object's actual value.</span></span> <span data-ttu-id="71c31-113">값 형식의 인스턴스가 변수에 할당되면 해당 변수에는 값의 새 사본이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-113">If an instance of a value type is assigned to a variable, that variable is given a fresh copy of the value.</span></span>

<span data-ttu-id="71c31-114">참조 형식은 해당 형식의 개체가 개체의 실제 값에 대한 참조(포인터와 유사)로 나타나는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-114">Reference types are data types whose objects are represented by a reference (similar to a pointer) to the object's actual value.</span></span> <span data-ttu-id="71c31-115">참조 형식이 변수에 할당되면 해당 변수는 원래 값을 참조하거나 가리키며</span><span class="sxs-lookup"><span data-stu-id="71c31-115">If a reference type is assigned to a variable, that variable references (points to) the original value.</span></span> <span data-ttu-id="71c31-116">복사는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-116">No copy is made.</span></span> 

<span data-ttu-id="71c31-117">.NET의 공용 형식 시스템에서는 다음과 같은 다섯 가지 범주의 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-117">The common type system in .NET supports the following five categories of types:</span></span>

* [<span data-ttu-id="71c31-118">클래스</span><span class="sxs-lookup"><span data-stu-id="71c31-118">Classes</span></span>](#classes)

* [<span data-ttu-id="71c31-119">구조체</span><span class="sxs-lookup"><span data-stu-id="71c31-119">Structures</span></span>](#structures)

* [<span data-ttu-id="71c31-120">열거형</span><span class="sxs-lookup"><span data-stu-id="71c31-120">Enumerations</span></span>](#enumerations)

* [<span data-ttu-id="71c31-121">인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c31-121">Interfaces</span></span>](#interfaces)

* [<span data-ttu-id="71c31-122">대리자</span><span class="sxs-lookup"><span data-stu-id="71c31-122">Delegates</span></span>](#delegates)

### <a name="classes"></a><span data-ttu-id="71c31-123">클래스</span><span class="sxs-lookup"><span data-stu-id="71c31-123">Classes</span></span>

<span data-ttu-id="71c31-124">클래스는 다른 클래스에서 직접 파생될 수 있거나 [System.Object](xref:System.Object)에서 암시적으로 파생되는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-124">A class is a reference type that can be derived directly from another class and that is derived implicitly from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="71c31-125">클래스는 개체(클래스의 인스턴스)가 수행할 수 있는 작업(메서드, 이벤트 또는 속성)과 개체에 포함된 데이터(필드)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-125">The class defines the operations that an object (which is an instance of the class) can perform (methods, events, or properties) and the data that the object contains (fields).</span></span> <span data-ttu-id="71c31-126">구현 없이 정의만이 포함된 인터페이스와는 달리, 클래스에는 대개 정의와 구현이 모두 포함되어 있지만 구현이 없는 멤버가 하나 이상 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-126">Although a class generally includes both definition and implementation (unlike interfaces, for example, which contain only definition without implementation), it can have one or more members that have no implementation.</span></span>

<span data-ttu-id="71c31-127">다음 표에는 클래스가 가질 수 있는 일부 특성에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-127">The following table describes some of the characteristics that a class may have.</span></span> <span data-ttu-id="71c31-128">런타임을 지원하는 각 언어에는 클래스나 클래스 멤버가 이들 특성 중 하나 이상을 갖고 있음을 표시하는 방식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-128">Each language that supports the runtime provides a way to indicate that a class or class member has one or more of these characteristics.</span></span> <span data-ttu-id="71c31-129">그러나 .NET을 대상으로 하는 개별 프로그래밍 언어에서 이 특성들을 모두 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-129">However, individual programming languages that target .NET may not make all these characteristics available.</span></span>

<span data-ttu-id="71c31-130">특성</span><span class="sxs-lookup"><span data-stu-id="71c31-130">Characteristic</span></span> | <span data-ttu-id="71c31-131">설명</span><span class="sxs-lookup"><span data-stu-id="71c31-131">Description</span></span>
-------------- | -----------
<span data-ttu-id="71c31-132">sealed</span><span class="sxs-lookup"><span data-stu-id="71c31-132">sealed</span></span> | <span data-ttu-id="71c31-133">이 형식에서 다른 클래스를 파생할 수 없도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-133">Specifies that another class cannot be derived from this type.</span></span>
<span data-ttu-id="71c31-134">구현</span><span class="sxs-lookup"><span data-stu-id="71c31-134">implements</span></span> | <span data-ttu-id="71c31-135">인터페이스 멤버의 구현을 제공하여 클래스에서 하나 이상의 인터페이스를 사용할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-135">Indicates that the class uses one or more interfaces by providing implementations of interface members.</span></span>
<span data-ttu-id="71c31-136">abstract</span><span class="sxs-lookup"><span data-stu-id="71c31-136">abstract</span></span> | <span data-ttu-id="71c31-137">클래스를 인스턴스화할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-137">Indicates that the class cannot be instantiated.</span></span> <span data-ttu-id="71c31-138">이러한 클래스를 사용하려면 다른 클래스를 파생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-138">To use it, you must derive another class from it.</span></span>
<span data-ttu-id="71c31-139">상속</span><span class="sxs-lookup"><span data-stu-id="71c31-139">inherits</span></span> | <span data-ttu-id="71c31-140">기본 클래스를 지정한 곳에서 클래스의 인스턴스를 사용할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-140">Indicates that instances of the class can be used anywhere the base class is specified.</span></span> <span data-ttu-id="71c31-141">기본 클래스에서 상속된 파생 클래스에서는 기본 클래스에서 제공하는 공용 멤버의 구현을 사용할 수도 있고, 파생 클래스의 고유한 구현을 사용하여 공용 멤버의 구현을 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-141">A derived class that inherits from a base class can use the implementation of any public members provided by the base class, or the derived class can override the implementation of the public members with its own implementation.</span></span>
<span data-ttu-id="71c31-142">exported 또는 not exported</span><span class="sxs-lookup"><span data-stu-id="71c31-142">exported or not exported</span></span> | <span data-ttu-id="71c31-143">클래스를 정의한 어셈블리 밖에서 클래스를 볼 수 있는지의 여부를 지정하며</span><span class="sxs-lookup"><span data-stu-id="71c31-143">Indicates whether a class is visible outside the assembly in which it is defined.</span></span> <span data-ttu-id="71c31-144">이 특성은 중첩 클래스에는 적용되지 않고 최상위 클래스에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-144">This characteristic applies only to top-level classes and not to nested classes.</span></span>

> [!NOTE]
> <span data-ttu-id="71c31-145">클래스는 부모 클래스 또는 구조체 내에 중첩될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-145">A class can also be nested in a parent class or structure.</span></span> <span data-ttu-id="71c31-146">중첩된 클래스에도 멤버 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-146">Nested classes also have member characteristics.</span></span> <span data-ttu-id="71c31-147">자세한 내용은 [중첩 형식](#nested-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71c31-147">For more information, see [Nested types](#nested-types).</span></span>

<span data-ttu-id="71c31-148">구현이 없는 클래스 멤버는 추상 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-148">Class members that have no implementation are abstract members.</span></span> <span data-ttu-id="71c31-149">하나 이상의 멤버가 있는 클래스는 그 자체가 추상적이기 때문에 이 클래스의 새 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-149">A class that has one or more abstract members is itself abstract; new instances of it cannot be created.</span></span> <span data-ttu-id="71c31-150">런타임을 대상으로 하는 일부 언어에서는 추상 멤버가 없는 클래스를 추상으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-150">Some languages that target the runtime let you mark a class as abstract even if none of its members are abstract.</span></span> <span data-ttu-id="71c31-151">파생 클래스에서 상속하거나 재정의할 수 있는 기본 기능의 집합을 캡슐화하려는 경우 상황에 따라 추상 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-151">You can use an abstract class when you want to encapsulate a basic set of functionality that derived classes can inherit or override when appropriate.</span></span> <span data-ttu-id="71c31-152">추상이 아닌 클래스를 구체적인 클래스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-152">Classes that are not abstract are referred to as concrete classes.</span></span>

<span data-ttu-id="71c31-153">클래스는 인터페이스를 여러 개 구현할 수 있지만 모든 클래스가 암시적으로 상속받는 [System.Object](xref:System.Object) 외에 하나의 기본 클래스에서만 상속받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-153">A class can implement any number of interfaces, but it can inherit from only one base class in addition to [System.Object](xref:System.Object), from which all classes inherit implicitly.</span></span> <span data-ttu-id="71c31-154">모든 클래스에는 클래스의 새 인스턴스를 초기화하는 생성자가 최소한 하나는 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-154">All classes must have at least one constructor, which initializes new instances of the class.</span></span> <span data-ttu-id="71c31-155">생성자를 명시적으로 정의하지 않으면 대부분의 컴파일러는 자동으로 매개 변수가 없는 기본 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-155">If you do not explicitly define a constructor, most compilers will automatically provide a default (parameterless) constructor.</span></span>

### <a name="structures"></a><span data-ttu-id="71c31-156">구조체</span><span class="sxs-lookup"><span data-stu-id="71c31-156">Structures</span></span>

<span data-ttu-id="71c31-157">구조체는 [System.Object](xref:System.Object)에서 파생된 [System.ValueType](xref:System.ValueType)에서 다시 암시적으로 파생되는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-157">A structure is a value type that derives implicitly from [System.ValueType](xref:System.ValueType), which in turn is derived from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="71c31-158">구조체는 적은 메모리를 요구하는 값을 나타낼 때 유용할 뿐 아니라 강력한 형식의 매개 변수를 갖는 메서드에 값으로 전달되는 매개 변수로 값을 전달할 때도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-158">A structure is very useful for representing values whose memory requirements are small, and for passing values as by-value parameters to methods that have strongly typed parameters.</span></span> <span data-ttu-id="71c31-159">.NET의 모든 기본 데이터 형식([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) 및 [UInt64](xref:System.UInt64))은 구조체로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-159">In .NET, all primitive data types ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), and [UInt64](xref:System.UInt64)) are defined as structures.</span></span>

<span data-ttu-id="71c31-160">클래스와 마찬가지로 구조체는 데이터(구조체의 필드)와 해당 데이터에 대해 수행할 수 있는 작업(구조체의 메서드)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-160">Like classes, structures define both data (the fields of the structure) and the operations that can be performed on that data (the methods of the structure).</span></span> <span data-ttu-id="71c31-161">이는 [System.Object](xref:System.Object) 및 [System.ValueType](xref:System.ValueType) 클래스에 정의된 가상 메서드와 값 형식 자체에 정의된 메서드를 비롯하여 구조체에서 메서드를 호출할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-161">This means that you can call methods on structures, including the virtual methods defined on the [System.Object](xref:System.Object) and [System.ValueType](xref:System.ValueType) classes, and any methods defined on the value type itself.</span></span> <span data-ttu-id="71c31-162">다시 말하면 구조체에는 필드, 속성, 이벤트뿐 아니라 정적 및 비정적 메서드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-162">In other words, structures can have fields, properties, and events, as well as static and nonstatic methods.</span></span> <span data-ttu-id="71c31-163">구조체의 인스턴스를 만들어 매개 변수로 전달하고 지역 변수로 저장하거나 다른 값 형식 또는 참조 형식의 필드에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-163">You can create instances of structures, pass them as parameters, store them as local variables, or store them in a field of another value type or reference type.</span></span> <span data-ttu-id="71c31-164">구조체는 인터페이스를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-164">Structures can also implement interfaces.</span></span>

<span data-ttu-id="71c31-165">또한 값 형식이 몇 가지 측면에서 클래스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-165">Value types also differ from classes in several respects.</span></span> <span data-ttu-id="71c31-166">먼저, 값 형식은 [System.ValueType](xref:System.ValueType)에서 암시적으로 상속되긴 하지만 형식에서 직접 상속받을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-166">First, although they implicitly inherit from [System.ValueType](xref:System.ValueType), they cannot directly inherit from any type.</span></span> <span data-ttu-id="71c31-167">마찬가지로 모든 값 형식은 봉인되어 있으므로 이 형식에서 다른 형식을 파생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-167">Similarly, all value types are sealed, which means that no other type can be derived from them.</span></span> <span data-ttu-id="71c31-168">값 형식에는 생성자도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-168">They also do not require constructors.</span></span>

<span data-ttu-id="71c31-169">공용 언어 런타임에서는 각 값 형식에 대해 해당 boxed 형식 클래스를 제공합니다. 이 클래스는 값 형식과 동일한 상태 및 동작을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-169">For each value type, the common language runtime supplies a corresponding boxed type, which is a class that has the same state and behavior as the value type.</span></span> <span data-ttu-id="71c31-170">값 형식의 인스턴스가 [System.Object](xref:System.Object) 형식의 매개 변수를 허용하는 메서드에 전달될 때는 boxing됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-170">An instance of a value type is boxed when it is passed to a method that accepts a parameter of type [System.Object](xref:System.Object).</span></span> <span data-ttu-id="71c31-171">하지만 참조로 전달되는 매개 변수로 값 형식을 허용하는 메서드 호출에서 컨트롤이 반환될 때는 이 인스턴스가 unboxing됩니다. 즉, 클래스의 인스턴스에서 값 형식의 인스턴스로 다시 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-171">It is unboxed (that is, converted from an instance of a class back to an instance of a value type) when control returns from a method call that accepts a value type as a by-reference parameter.</span></span> <span data-ttu-id="71c31-172">일부 언어에서는 boxed 형식이 필요할 때 별도의 구문을 사용해야 하지만 그 밖의 언어에서는 필요할 때 자동으로 boxed 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-172">Some languages require that you use special syntax when the boxed type is required; others automatically use the boxed type when it is needed.</span></span> <span data-ttu-id="71c31-173">값 형식을 정의하면 boxed 형식과 unboxed 형식이 모두 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-173">When you define a value type, you are defining both the boxed and the unboxed type.</span></span>

### <a name="enumerations"></a><span data-ttu-id="71c31-174">열거형</span><span class="sxs-lookup"><span data-stu-id="71c31-174">Enumerations</span></span>

<span data-ttu-id="71c31-175">열거형(enum)은 [System.Enum](xref:System.Enum)에서 직접 상속받고 내부 기본 형식의 값에 대한 대체 이름을 제공하는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-175">An enumeration (enum) is a value type that inherits directly from [System.Enum](xref:System.Enum) and that supplies alternate names for the values of an underlying primitive type.</span></span> <span data-ttu-id="71c31-176">열거형 형식은 이름, 내부 형식 및 필드 집합으로 구성됩니다. 내부 형식은 기본으로 제공되는 부호 있는 정수나 부호 없는 정수 형식(예: [Byte](xref:System.Byte), [Int32](xref:System.Int32) 또는 [UInt64](xref:System.UInt64)) 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-176">An enumeration type has a name, an underlying type that must be one of the built-in signed or unsigned integer types (such as [Byte](xref:System.Byte), [Int32](xref:System.Int32), or [UInt64](xref:System.UInt64)), and a set of fields.</span></span> <span data-ttu-id="71c31-177">각 필드는 상수를 나타내는 정적 리터럴 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-177">The fields are static literal fields, each of which represents a constant.</span></span> <span data-ttu-id="71c31-178">여러 필드에 동일한 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-178">The same value can be assigned to multiple fields.</span></span> <span data-ttu-id="71c31-179">이 경우 리플렉션 및 문자열 변환을 위해 값 중 하나를 기본 열거형 값으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-179">When this occurs, you must mark one of the values as the primary enumeration value for reflection and string conversion.</span></span>

<span data-ttu-id="71c31-180">내부 형식의 값을 열거형에 할당하거나 반대로도 할당할 수 있으며 이때 런타임에서 캐스팅할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-180">You can assign a value of the underlying type to an enumeration and vice versa (no cast is required by the runtime).</span></span> <span data-ttu-id="71c31-181">열거형의 인스턴스를 만들고 열거형의 내부 형식에 정의된 메서드뿐 아니라 [System.Enum](xref:System.Enum)의 메서드도 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-181">You can create an instance of an enumeration and call the methods of [System.Enum](xref:System.Enum), as well as any methods defined on the enumeration's underlying type.</span></span> <span data-ttu-id="71c31-182">그러나 일부 언어에서는 내부 형식의 인스턴스가 필요한 경우 열거형을 매개 변수로 전달할 수 없고 그 반대로도 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-182">However, some languages might not let you pass an enumeration as a parameter when an instance of the underlying type is required (or vice versa).</span></span>

<span data-ttu-id="71c31-183">다음은 열거형에 적용되는 추가 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-183">The following additional restrictions apply to enumerations:</span></span> 

* <span data-ttu-id="71c31-184">고유의 메서드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-184">They cannot define their own methods.</span></span>

* <span data-ttu-id="71c31-185">인터페이스를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-185">They cannot implement interfaces.</span></span>

* <span data-ttu-id="71c31-186">속성 또는 이벤트를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-186">They cannot define properties or events.</span></span>

* <span data-ttu-id="71c31-187">열거형은 제네릭 형식 내에 중첩되어 있으므로 단독 제네릭이 아니면 제네릭이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-187">They cannot be generic, unless they are generic only because they are nested within a generic type.</span></span> <span data-ttu-id="71c31-188">즉, 열거형에는 자체의 형식 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-188">That is, an enumeration cannot have type parameters of its own.</span></span> 

> [!NOTE]
> <span data-ttu-id="71c31-189">C#으로 만든 중첩 형식(열거형 포함)은 모든 바깥쪽 제네릭 형식의 형식 매개 변수를 포함하므로 자체의 형식 매개 변수가 없더라도 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-189">Nested types (including enumerations) created with C# include the type parameters of all enclosing generic types, and are therefore generic even if they do not have type parameters of their own.</span></span> <span data-ttu-id="71c31-190">자세한 내용은 [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71c31-190">For more information, see the [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) reference topic.</span></span> 

<span data-ttu-id="71c31-191">[FlagsAttribute](xref:System.FlagsAttribute) 특성은 비트 필드라는 특수한 열거형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-191">The [FlagsAttribute](xref:System.FlagsAttribute) attribute denotes a special kind of enumeration called a bit field.</span></span> <span data-ttu-id="71c31-192">런타임 자체에서는 기존의 열거형과 비트 필드를 구분하지 않지만 언어에 따라서는 이를 구분할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-192">The runtime itself does not distinguish between traditional enumerations and bit fields, but your language might do so.</span></span> <span data-ttu-id="71c31-193">이를 구분할 경우 열거형이 아니라 비트 필드에 비트 연산자를 적용하여 명명되지 않은 값을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-193">When this distinction is made, bitwise operators can be used on bit fields, but not on enumerations, to generate unnamed values.</span></span> <span data-ttu-id="71c31-194">일반적으로 열거형은 요일, 국가 또는 지역 이름 등과 같은 고유한 요소의 목록에 사용하고,</span><span class="sxs-lookup"><span data-stu-id="71c31-194">Enumerations are generally used for lists of unique elements, such as days of the week, country or region names, and so on.</span></span> <span data-ttu-id="71c31-195">비트 필드는 `Red And Big And Fast` 같은 조합에서 나타날 수 있는 특성 및 수량 목록에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-195">Bit fields are generally used for lists of qualities or quantities that might occur in combination, such as `Red And Big And Fast`.</span></span>

<span data-ttu-id="71c31-196">다음 예제에서는 비트 필드와 기존의 열거형을 둘 다 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-196">The following example shows how to use both bit fields and traditional enumerations.</span></span>

```csharp
using System;
using System.Collections.Generic;

// A traditional enumeration of some root vegetables.
public enum SomeRootVegetables
{
    HorseRadish,
    Radish,
    Turnip
}

// A bit field or flag enumeration of harvesting seasons.
[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

public class Example
{
   public static void Main()
   {
       // Hash table of when vegetables are available.
       Dictionary<SomeRootVegetables, Seasons> AvailableIn = new Dictionary<SomeRootVegetables, Seasons>();

       AvailableIn[SomeRootVegetables.HorseRadish] = Seasons.All;
       AvailableIn[SomeRootVegetables.Radish] = Seasons.Spring;
       AvailableIn[SomeRootVegetables.Turnip] = Seasons.Spring | 
            Seasons.Autumn;

       // Array of the seasons, using the enumeration.
       Seasons[] theSeasons = new Seasons[] { Seasons.Summer, Seasons.Autumn, 
            Seasons.Winter, Seasons.Spring };

       // Print information of what vegetables are available each season.
       foreach (Seasons season in theSeasons)
       {
          Console.Write(String.Format(
              "The following root vegetables are harvested in {0}:\n", 
              season.ToString("G")));
          foreach (KeyValuePair<SomeRootVegetables, Seasons> item in AvailableIn)
          {
             // A bitwise comparison.
             if (((Seasons)item.Value & season) > 0)
                 Console.Write(String.Format("  {0:G}\n", 
                      (SomeRootVegetables)item.Key));
          }
       }
   }
}
// The example displays the following output:
//    The following root vegetables are harvested in Summer:
//      HorseRadish
//    The following root vegetables are harvested in Autumn:
//      Turnip
//      HorseRadish
//    The following root vegetables are harvested in Winter:
//      HorseRadish
//    The following root vegetables are harvested in Spring:
//      Turnip
//      Radish
//      HorseRadish
```

```vb
Imports System.Collections.Generic

' A traditional enumeration of some root vegetables.
Public Enum SomeRootVegetables
   HorseRadish
   Radish
   Turnip
End Enum 

' A bit field or flag enumeration of harvesting seasons.
<Flags()> Public Enum Seasons
   None = 0
   Summer = 1
   Autumn = 2
   Winter = 4
   Spring = 8
   All = Summer Or Autumn Or Winter Or Spring
End Enum 

' Entry point.
Public Class Example
   Public Shared Sub Main()
      ' Hash table of when vegetables are available.
      Dim AvailableIn As New Dictionary(Of SomeRootVegetables, Seasons)()

      AvailableIn(SomeRootVegetables.HorseRadish) = Seasons.All
      AvailableIn(SomeRootVegetables.Radish) = Seasons.Spring
      AvailableIn(SomeRootVegetables.Turnip) = Seasons.Spring Or _
                                               Seasons.Autumn

      ' Array of the seasons, using the enumeration.
      Dim theSeasons() As Seasons = {Seasons.Summer, Seasons.Autumn, _
                                     Seasons.Winter, Seasons.Spring}

      ' Print information of what vegetables are available each season.
      For Each season As Seasons In theSeasons
         Console.WriteLine(String.Format( _
              "The following root vegetables are harvested in {0}:", _
              season.ToString("G")))
         For Each item As KeyValuePair(Of SomeRootVegetables, Seasons) In AvailableIn
            ' A bitwise comparison.
            If(CType(item.Value, Seasons) And season) > 0 Then
               Console.WriteLine("  " + _
                     CType(item.Key, SomeRootVegetables).ToString("G"))
            End If
         Next
      Next
   End Sub 
End Class 
' The example displays the following output:
'    The following root vegetables are harvested in Summer:
'      HorseRadish
'    The following root vegetables are harvested in Autumn:
'      Turnip
'      HorseRadish
'    The following root vegetables are harvested in Winter:
'      HorseRadish
'    The following root vegetables are harvested in Spring:
'      Turnip
'      Radish
'      HorseRadish
```

### <a name="interfaces"></a><span data-ttu-id="71c31-197">인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c31-197">Interfaces</span></span>

<span data-ttu-id="71c31-198">인터페이스는 "실행 가능" 관계나 "소유" 관계를 지정하는 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-198">An interface defines a contract that specifies a "can do" relationship or a "has a" relationship.</span></span> <span data-ttu-id="71c31-199">인터페이스는 비교 및 정렬([IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) 인터페이스), 같은지 테스트([IEquatable&lt;T&gt;](xref:System.IEquatable%601) 인터페이스) 또는 컬렉션의 항목 열거([IEnumerable](xref:System.Collections.IEnumerable) 및 [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) 인터페이스)와 같은 기능을 구현하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-199">Interfaces are often used to implement functionality, such as comparing and sorting (the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces), testing for equality (the [IEquatable&lt;T&gt;](xref:System.IEquatable%601) interface), or enumerating items in a collection (the [IEnumerable](xref:System.Collections.IEnumerable) and [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) interfaces).</span></span> <span data-ttu-id="71c31-200">인터페이스에는 속성, 메서드 및 이벤트가 있을 수 있으며 이러한 멤버는 모두 추상 멤버입니다. 즉, 인터페이스는 멤버와 시그니처를 정의하지만 각 인터페이스 멤버의 기능은 인터페이스를 구현하는 형식에서 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-200">Interfaces can have properties, methods, and events, all of which are abstract members; that is, although the interface defines the members and their signatures, it leaves it to the type that implements the interface to define the functionality of each interface member.</span></span> <span data-ttu-id="71c31-201">따라서 인터페이스를 구현하는 모든 클래스나 구조체는 인터페이스에 선언된 추상 멤버에 대한 정의를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-201">This means that any class or structure that implements an interface must supply definitions for the abstract members declared in the interface.</span></span> <span data-ttu-id="71c31-202">인터페이스를 구현하는 클래스나 구조체에서 하나 이상의 다른 인터페이스를 함께 구현해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-202">An interface can require any implementing class or structure to also implement one or more other interfaces.</span></span>

<span data-ttu-id="71c31-203">인터페이스에는 다음과 같은 제약 조건이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-203">The following restrictions apply to interfaces:</span></span> 

* <span data-ttu-id="71c31-204">인터페이스의 액세스 가능성은 원하는 대로 선언할 수 있지만 모든 인터페이스 멤버는 공용 액세스 가능성을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-204">An interface can be declared with any accessibility, but interface members must all have public accessibility.</span></span>

* <span data-ttu-id="71c31-205">인터페이스는 생성자를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-205">Interfaces cannot define constructors.</span></span>

* <span data-ttu-id="71c31-206">인터페이스는 필드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-206">Interfaces cannot define fields.</span></span>

* <span data-ttu-id="71c31-207">인터페이스에서는 인스턴스 멤버만을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-207">Interfaces can define only instance members.</span></span> <span data-ttu-id="71c31-208">정적 멤버는 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-208">They cannot define static members.</span></span>

<span data-ttu-id="71c31-209">둘 이상의 인터페이스에서 동일한 시그니처의 멤버를 선언할 수 있고 이들 멤버가 별도의 구현을 가질 수 있으므로 각 언어에서는 멤버를 요구하는 인터페이스에 구현을 매핑하기 위한 규칙을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-209">Each language must provide rules for mapping an implementation to the interface that requires the member, because more than one interface can declare a member with the same signature, and these members can have separate implementations.</span></span>

### <a name="delegates"></a><span data-ttu-id="71c31-210">대리자</span><span class="sxs-lookup"><span data-stu-id="71c31-210">Delegates</span></span>

<span data-ttu-id="71c31-211">대리자는 C++의 함수 포인터와 비슷한 목적으로 사용되는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-211">Delegates are reference types that serve a purpose similar to that of function pointers in C++.</span></span> <span data-ttu-id="71c31-212">대리자는 .NET의 이벤트 처리기와 콜백 함수에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-212">They are used for event handlers and callback functions in .NET.</span></span> <span data-ttu-id="71c31-213">함수 포인터와 달리 대리자는 안전하고, 확인할 수 있으며, 형식이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-213">Unlike function pointers, delegates are secure, verifiable, and type safe.</span></span> <span data-ttu-id="71c31-214">대리자 형식은 호환되는 시그니처가 포함된 정적 메서드 또는 인스턴스 메서드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-214">A delegate type can represent any instance method or static method that has a compatible signature.</span></span> 

<span data-ttu-id="71c31-215">대리자 매개 변수의 형식이 메서드 매개 변수의 형식보다 제한적인 경우 대리자의 매개 변수는 메서드의 해당 매개 변수와 호환됩니다. 이 경우 대리자로 전달된 인수를 안전하게 메서드로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-215">A parameter of a delegate is compatible with the corresponding parameter of a method if the type of the delegate parameter is more restrictive than the type of the method parameter, because this guarantees that an argument passed to the delegate can be passed safely to the method.</span></span>

<span data-ttu-id="71c31-216">마찬가지로 메서드의 반환 형식이 대리자의 반환 형식보다 제한적인 경우 대리자의 반환 형식은 메서드의 반환 형식과 호환됩니다. 이 경우 메서드의 반환 값을 안전하게 대리자의 반환 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-216">Similarly, the return type of a delegate is compatible with the return type of a method if the return type of the method is more restrictive than the return type of the delegate, because this guarantees that the return value of the method can be cast safely to the return type of the delegate.</span></span>

<span data-ttu-id="71c31-217">예를 들어 [IEnumerable](xref:System.Collections.IEnumerable) 형식의 매개 변수가 있고 반환 형식이 [Object](xref:System.Object)인 대리자는 [Object](xref:System.Object) 형식의 매개 변수가 있고 반환 값이 [IEnumerable](xref:System.Collections.IEnumerable) 형식인 메서드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-217">For example, a delegate that has a parameter of type [IEnumerable](xref:System.Collections.IEnumerable) and a return type of [Object](xref:System.Object) can represent a method that has a parameter of type [Object](xref:System.Object) and a return value of type [IEnumerable](xref:System.Collections.IEnumerable).</span></span> 

 <span data-ttu-id="71c31-218">대리자는 이 대리자가 나타내는 메서드에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-218">A delegate is said to be bound to the method it represents.</span></span> <span data-ttu-id="71c31-219">대리자는 메서드에 바인딩될 뿐 아니라 개체에도 바인딩될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-219">In addition to being bound to the method, a delegate can be bound to an object.</span></span> <span data-ttu-id="71c31-220">개체는 메서드의 첫 번째 매개 변수를 나타내며 대리자가 호출될 때마다 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-220">The object represents the first parameter of the method, and is passed to the method every time the delegate is invoked.</span></span> <span data-ttu-id="71c31-221">메서드가 인스턴스 메서드이면 바인딩된 개체가 암시적 `this` 매개 변수(Visual Basic의 경우 `Me`)로 전달됩니다. 메서드가 정적이면 개체는 메서드의 첫 번째 정식 매개 변수로 전달되며 대리자 시그니처가 나머지 매개 변수와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-221">If the method is an instance method, the bound object is passed as the implicit `this` parameter (`Me` in Visual Basic); if the method is static, the object is passed as the first formal parameter of the method, and the delegate signature must match the remaining parameters.</span></span> 
 
 <span data-ttu-id="71c31-222">모든 대리자는 [System.Delegate](xref:System.Delegate)에서 상속받는 [System.MulticastDelegate](xref:System.MulticastDelegate)에서 다시 상속받습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-222">All delegates inherit from [System.MulticastDelegate](xref:System.MulticastDelegate), which inherits from [System.Delegate](xref:System.Delegate).</span></span> <span data-ttu-id="71c31-223">C# 및 Visual Basic 언어에서는 이러한 형식에서 상속받는 것을 허용하지 않으며,</span><span class="sxs-lookup"><span data-stu-id="71c31-223">The C# and Visual Basic languages don't allow inheritance from these types.</span></span> <span data-ttu-id="71c31-224">대신 대리자를 선언하기 위한 키워드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-224">Instead, they provide keywords for declaring delegates.</span></span>
 
 <span data-ttu-id="71c31-225">대리자는 [MulticastDelegate](xref:System.MulticastDelegate)에서 상속받기 때문에 대리자에 호출 목록이 있습니다. 이 목록에는 대리자가 나타내는 메서드와 대리자가 호출될 때 실행되는 메서드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-225">Because delegates inherit from [MulticastDelegate](xref:System.MulticastDelegate), a delegate has an invocation list, which is a list of methods that the delegate represents and that are executed when the delegate is invoked.</span></span> <span data-ttu-id="71c31-226">이 목록의 모든 메서드는 대리자가 호출될 때 제공되는 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-226">All methods in the list receive the arguments supplied when the delegate is invoked.</span></span>

> [!NOTE]
> <span data-ttu-id="71c31-227">호출 목록에 하나 이상의 메서드가 있는 대리자에 대해서는 반환 형식을 가지고 있더라도 반환 값이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-227">The return value is not defined for a delegate that has more than one method in its invocation list, even if the delegate has a return type.</span></span>

<span data-ttu-id="71c31-228">대부분의 경우 콜백 메서드와 마찬가지로 대리자는 하나의 메서드만 나타내며, 대리자를 만들고 호출하는 것 외에는 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-228">In many cases, such as with callback methods, a delegate represents only one method, and the only actions you have to take are creating the delegate and invoking it.</span></span> 

<span data-ttu-id="71c31-229">.NET에서는 여러 메서드를 나타내는 대리자에 대해 [Delegate](xref:System.Delegate) 및 [MulticastDelegate](xref:System.MulticastDelegate) 대리자 클래스의 메서드를 제공하여 대리자 호출 목록에 메서드 추가([Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) 메서드), 메서드 제거([Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) 메서드), 호출 목록 가져오기([Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) 메서드) 등의 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-229">For delegates that represent multiple methods, .NET provides methods of the [Delegate](xref:System.Delegate) and [MulticastDelegate](xref:System.MulticastDelegate) delegate classes to support operations such as adding a method to a delegate's invocation list (the [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) method), removing a method (the [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) method), and getting the invocation list (the [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) method).</span></span>

> [!NOTE]
> <span data-ttu-id="71c31-230">C# 또는 Visual Basic에서는 이벤트 처리기 대리자에 대해 이러한 메서드를 사용할 필요가 없습니다. 해당 언어에서 이벤트 처리기를 추가하고 제거하기 위한 구문을 제공하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-230">It is not necessary to use these methods for event-handler delegates in C# or Visual Basic, because these languages provide syntax for adding and removing event handlers.</span></span>

## <a name="type-definitions"></a><span data-ttu-id="71c31-231">형식 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-231">Type definitions</span></span>

<span data-ttu-id="71c31-232">형식 정의에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-232">A type definition includes the following:</span></span> 

* <span data-ttu-id="71c31-233">형식에 정의되어 있는 특성</span><span class="sxs-lookup"><span data-stu-id="71c31-233">Any attributes defined on the type.</span></span>

* <span data-ttu-id="71c31-234">형식의 액세스 가능성(표시 여부)</span><span class="sxs-lookup"><span data-stu-id="71c31-234">The type's accessibility (visibility).</span></span>

* <span data-ttu-id="71c31-235">형식의 이름</span><span class="sxs-lookup"><span data-stu-id="71c31-235">The type's name.</span></span>

* <span data-ttu-id="71c31-236">형식의 기본 형식</span><span class="sxs-lookup"><span data-stu-id="71c31-236">The type's base type.</span></span>

* <span data-ttu-id="71c31-237">형식에서 구현하는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c31-237">Any interfaces implemented by the type.</span></span>

* <span data-ttu-id="71c31-238">형식의 멤버 각각에 대한 정의</span><span class="sxs-lookup"><span data-stu-id="71c31-238">Definitions for each of the type's members.</span></span>

### <a name="attributes"></a><span data-ttu-id="71c31-239">특성</span><span class="sxs-lookup"><span data-stu-id="71c31-239">Attributes</span></span>

<span data-ttu-id="71c31-240">특성에서는 추가적인 사용자 정의 메타데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-240">Attributes provide additional user-defined metadata.</span></span> <span data-ttu-id="71c31-241">특성은 어셈블리의 형식에 대한 추가 정보를 저장하거나 디자인 타임 또는 런타임 환경에서 형식 멤버의 동작을 수정하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-241">Most commonly, they are used to store additional information about a type in its assembly, or to modify the behavior of a type member in either the design-time or run-time environment.</span></span> 

<span data-ttu-id="71c31-242">특성은 그 자체가 [System.Attribute](xref:System.Attribute)에서 상속받는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-242">Attributes are themselves classes that inherit from [System.Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="71c31-243">특성 사용을 지원하는 언어 각각에는 특성을 언어 요소에 적용하기 위한 자체 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-243">Languages that support the use of attributes each have their own syntax for applying attributes to a language element.</span></span> <span data-ttu-id="71c31-244">특성은 거의 대부분의 언어 요소에 적용될 수 있으며, 특성이 적용될 수 있는 특정 요소는 해당 특성 클래스에 적용된 [AttributeUsageAttribute](xref:System.AttributeUsageAttribute)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-244">Attributes can be applied to almost any language element; the specific elements to which an attribute can be applied are defined by the [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) that is applied to that attribute class.</span></span>

### <a name="type-accessibility"></a><span data-ttu-id="71c31-245">형식 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="71c31-245">Type accessibility</span></span>

<span data-ttu-id="71c31-246">모든 형식에는 다른 형식에서 액세스할 수 있는지를 제어하는 한정자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-246">All types have a modifier that governs their accessibility from other types.</span></span> <span data-ttu-id="71c31-247">다음 표에서는 런타임에서 지원하는 형식 액세스 가능성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-247">The following table describes the type accessibilities supported by the runtime.</span></span>

<span data-ttu-id="71c31-248">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="71c31-248">Accessibility</span></span> | <span data-ttu-id="71c31-249">설명</span><span class="sxs-lookup"><span data-stu-id="71c31-249">Description</span></span>
------------- | -----------
<span data-ttu-id="71c31-250">public</span><span class="sxs-lookup"><span data-stu-id="71c31-250">public</span></span> | <span data-ttu-id="71c31-251">모든 어셈블리에서 액세스할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-251">The type is accessible by all assemblies.</span></span>
<span data-ttu-id="71c31-252">어셈블리</span><span class="sxs-lookup"><span data-stu-id="71c31-252">assembly</span></span> | <span data-ttu-id="71c31-253">해당 어셈블리 안에서만 액세스할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-253">The type is accessible only from within its assembly.</span></span>

<span data-ttu-id="71c31-254">중첩된 형식의 액세스 가능성은 액세스 가능 도메인에 따라 다릅니다. 액세스 가능 도메인은 멤버에 대해 선언된 액세스 가능성 및 한 수준 위 형식의 액세스 가능 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-254">The accessibility of a nested type depends on its accessibility domain, which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="71c31-255">그러나 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-255">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>

<span data-ttu-id="71c31-256">`P` 프로그램 내의 `T` 형식에서 선언된 중첩된 멤버 `M`의 접근성 도메인은 다음과 같이 정의됩니다. `M` 자체가 형식일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-256">The accessibility domain of a nested member `M` declared in a type `T`within a program `P` is defined as follows (noting that `M` might itself be a type):</span></span> 

* <span data-ttu-id="71c31-257">`M`에 대해 선언된 액세스 가능성이 `public`인 경우 `M`의 액세스 가능 도메인은 `T`의 액세스 가능 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-257">If the declared accessibility of `M` is `public`, the accessibility domain of `M` is the accessibility domain of `T`.</span></span>

* <span data-ttu-id="71c31-258">`M`에 대해 선언된 액세스 가능성이 `protected internal`인 경우 `M`의 액세스 가능 도메인은 `T`의 프로그램 텍스트를 가진 `P`의 액세스 가능 도메인과 `T` 외부에 선언된 `P`에서 파생된 모든 형식의 프로그램 텍스트 사이의 교집합 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-258">If the declared accessibility of `M` is `protected internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `P` and the program text of any type derived from `T` declared outside `P`.</span></span>

* <span data-ttu-id="71c31-259">`M`에 대해 선언된 액세스 가능성이 `protected`인 경우 `M`의 액세스 가능 도메인은 `T`의 프로그램 텍스트를 가진 `T`의 액세스 가능 도메인과 `T`에서 파생된 모든 형식 사이의 교집합 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-259">If the declared accessibility of `M` is `protected`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `T` and any type derived from `T`.</span></span>

* <span data-ttu-id="71c31-260">`M`의 선언된 접근성이 `internal`인 경우 `M`의 접근성 도메인은 `P`의 접근성 도메인과 프로그램 텍스트 `T`의 교집합 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-260">If the declared accessibility of `M` is `internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of`P`.</span></span>

* <span data-ttu-id="71c31-261">`M`에 대해 선언된 액세스 가능성이 `private`인 경우 `M`의 액세스 가능 도메인은 `T`의 프로그램 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-261">If the declared accessibility of `M` is `private`, the accessibility domain of `M` is the program text of `T`.</span></span>

### <a name="type-names"></a><span data-ttu-id="71c31-262">형식 이름</span><span class="sxs-lookup"><span data-stu-id="71c31-262">Type names</span></span>

<span data-ttu-id="71c31-263">공용 형식 시스템에서 형식 이름에는 두 가지 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-263">The common type system imposes only two restrictions on names:</span></span> 

* <span data-ttu-id="71c31-264">모든 이름은 유니코드(16비트) 문자의 문자열로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-264">All names are encoded as strings of Unicode (16-bit) characters.</span></span>

* <span data-ttu-id="71c31-265">이름에 값 0x0000(16비트)을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-265">Names are not permitted to have an embedded (16-bit) value of 0x0000.</span></span>

<span data-ttu-id="71c31-266">그러나 대부분의 언어에서는 형식 이름에 대해 추가적인 제한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-266">However, most languages impose additional restrictions on type names.</span></span> <span data-ttu-id="71c31-267">비교 연산은 바이트 단위로 수행되므로 대/소문자를 구분하며 로캘에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-267">All comparisons are done on a byte-by-byte basis, and are therefore case-sensitive and locale-independent.</span></span>

<span data-ttu-id="71c31-268">형식은 다른 모듈 및 어셈블리의 형식을 참조할 수 있지만 하나의 .NET 모듈 내에서 완전히 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-268">Although a type might reference types from other modules and assemblies, a type must be fully defined within one .NET module.</span></span> <span data-ttu-id="71c31-269">컴파일러 지원에 따라 차이가 있지만 형식은 여러 소스 코드 파일로 분리될 수 있습니다. 형식 이름은 네임스페이스 내에서만 고유하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-269">(Depending on compiler support, however, it can be divided into multiple source code files.) Type names need be unique only within a namespace.</span></span> <span data-ttu-id="71c31-270">형식을 완전하게 식별하려면 형식의 구현을 포함하는 네임스페이스를 통해 형식 이름을 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-270">To fully identify a type, the type name must be qualified by the namespace that contains the implementation of the type.</span></span>

### <a name="base-types-and-interfaces"></a><span data-ttu-id="71c31-271">기본 형식 및 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c31-271">Base types and interfaces</span></span>

<span data-ttu-id="71c31-272">형식은 다른 형식에서 값과 동작을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-272">A type can inherit values and behaviors from another type.</span></span> <span data-ttu-id="71c31-273">공용 형식 시스템에서는 둘 이상의 기본 형식에서 형식을 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-273">The common type system does not allow types to inherit from more than one base type.</span></span>

<span data-ttu-id="71c31-274">형식에서 구현할 수 있는 인터페이스의 수는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-274">A type can implement any number of interfaces.</span></span> <span data-ttu-id="71c31-275">인터페이스를 구현하려면 형식에서 해당 인터페이스의 모든 가상 멤버를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-275">To implement an interface, a type must implement all the virtual members of that interface.</span></span> <span data-ttu-id="71c31-276">가상 메서드는 파생된 형식에서 구현할 수 있으며 정적으로 또는 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-276">A virtual method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span>

## <a name="type-members"></a><span data-ttu-id="71c31-277">형식 멤버</span><span class="sxs-lookup"><span data-stu-id="71c31-277">Type members</span></span>

<span data-ttu-id="71c31-278">런타임을 사용하면 형식의 동작과 상태를 지정하는 형식의 멤버를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-278">The runtime enables you to define members of your type, which specifies the behavior and state of a type.</span></span> <span data-ttu-id="71c31-279">다음과 같은 형식 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-279">Type members include the following:</span></span>

* [<span data-ttu-id="71c31-280">필드</span><span class="sxs-lookup"><span data-stu-id="71c31-280">Fields</span></span>](#fields)

* [<span data-ttu-id="71c31-281">속성</span><span class="sxs-lookup"><span data-stu-id="71c31-281">Properties</span></span>](#properties)

* [<span data-ttu-id="71c31-282">메서드</span><span class="sxs-lookup"><span data-stu-id="71c31-282">Methods</span></span>](#methods)

* [<span data-ttu-id="71c31-283">생성자</span><span class="sxs-lookup"><span data-stu-id="71c31-283">Constructors</span></span>](#constructors)

* [<span data-ttu-id="71c31-284">이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-284">Events</span></span>](#events)

* [<span data-ttu-id="71c31-285">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="71c31-285">Nested types</span></span>](#nested-types)

### <a name="fields"></a><span data-ttu-id="71c31-286">필드</span><span class="sxs-lookup"><span data-stu-id="71c31-286">Fields</span></span>

<span data-ttu-id="71c31-287">필드는 형식의 상태를 설명하고 상태의 일부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-287">A field describes and contains part of the type's state.</span></span> <span data-ttu-id="71c31-288">필드는 런타임에서 지원하는 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-288">Fields can be of any type supported by the runtime.</span></span> <span data-ttu-id="71c31-289">필드는 대개 `private` 또는 `protected`이므로 클래스 내부나 파생 클래스에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-289">Most commonly, fields are either `private` or `protected`, so that they are accessible only from within the class or from a derived class.</span></span> <span data-ttu-id="71c31-290">필드의 값을 형식 외부에서 수정할 수 있는 경우 일반적으로 속성 집합 접근자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-290">If the value of a field can be modified from outside its type, a property set accessor is typically used.</span></span> <span data-ttu-id="71c31-291">공개적으로 노출된 필드는 대개 읽기 전용이며 다음 두 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-291">Publicly exposed fields are usually read-only and can be of two types:</span></span> 

* <span data-ttu-id="71c31-292">상수. 해당 값은 디자인 타임에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-292">Constants, whose value is assigned at design time.</span></span> <span data-ttu-id="71c31-293">상수는 `static`(Visual Basic의 경우 `Shared`) 키워드를 통해 정의되지는 않지만 클래스의 정적 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-293">These are static members of a class, although they are not defined using the `static` (`Shared` in Visual Basic) keyword.</span></span>

* <span data-ttu-id="71c31-294">읽기 전용 변수. 해당 값은 클래스 생성자에서만 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-294">Read-only variables, whose values can be assigned in the class constructor.</span></span>

<span data-ttu-id="71c31-295">다음 예제에서는 이 두 가지 읽기 전용 필드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-295">The following example illustrates these two usages of read-only fields.</span></span>

```csharp
using System;

public class Constants
{
   public const double Pi = 3.1416;
   public readonly DateTime BirthDate;

   public Constants(DateTime birthDate)
   {
      this.BirthDate = birthDate;
   }
}

public class Example
{
   public static void Main()
   {
      Constants con = new Constants(new DateTime(1974, 8, 18));
      Console.Write(Constants.Pi + "\n");
      Console.Write(con.BirthDate.ToString("d") + "\n");
   }
}
// The example displays the following output if run on a system whose current
// culture is en-US:
//    3.1417
//    8/18/1974
```

```vb
Public Class Constants
   Public Const Pi As Double = 3.1416
   Public ReadOnly BirthDate As Date

   Public Sub New(birthDate As Date)
      Me.BirthDate = birthDate
   End Sub
End Class

Public Module Example
   Public Sub Main()
      Dim con As New Constants(#8/18/1974#)
      Console.WriteLine(Constants.Pi.ToString())
      Console.WriteLine(con.BirthDate.ToString("d"))
   End Sub
End Module
' The example displays the following output if run on a system whose current
' culture is en-US:
'    3.1417
'    8/18/1974
```

### <a name="properties"></a><span data-ttu-id="71c31-296">속성</span><span class="sxs-lookup"><span data-stu-id="71c31-296">Properties</span></span>

<span data-ttu-id="71c31-297">속성은 형식의 값 또는 상태에 이름을 지정하고 속성의 값을 가져오거나 설정하는 데 사용하는 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-297">A property names a value or state of the type and defines methods for getting or setting the property's value.</span></span> <span data-ttu-id="71c31-298">속성은 기본 형식, 기본 형식의 컬렉션, 사용자 정의 형식 또는 사용자 정의 형식의 컬렉션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-298">Properties can be primitive types, collections of primitive types, user-defined types, or collections of user-defined types.</span></span> <span data-ttu-id="71c31-299">속성은 주로 형식의 공용 인터페이스를 형식의 실제 표시와 무관하게 유지하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-299">Properties are often used to keep the public interface of a type independent from the type's actual representation.</span></span> <span data-ttu-id="71c31-300">따라서 속성은 클래스에 직접 저장되지 않은 값을 반영하거나(예를 들어 속성이 계산된 값을 반환하는 경우) 값이 전용 필드에 할당되기 전에 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-300">This enables properties to reflect values that are not directly stored in the class (for example, when a property returns a computed value) or to perform validation before values are assigned to private fields.</span></span> <span data-ttu-id="71c31-301">다음 예제에서는 후자의 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-301">The following example illustrates the latter pattern.</span></span>

```csharp
using System;

public class Person
{
   private int m_Age;

   public int Age
   { 
      get { return m_Age; }
      set {
         if (value < 0 || value > 125)
         {
            throw new ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.");
         }
         else
         {
            m_Age = value;
         }         
      }
   }
}
```

```vb
Public Class Person
   Private m_Age As Integer

   Public Property Age As Integer
      Get
         Return m_Age
      End Get
      Set
         If value < 0 Or value > 125 Then
            Throw New ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.")
         Else
            m_Age = value
         End If
      End Set
   End Property
End Class
```

<span data-ttu-id="71c31-302">읽기 가능한 속성이 포함된 형식의 MSIL(Microsoft Intermediate Language)에는 속성 자체뿐만 아니라 `get`*_propertyname* 메서드도 포함되어 있으며 쓰기 가능한 속성이 포함된 형식의 MSIL에는 `set`*_propertyname* 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-302">In addition to including the property itself, the Microsoft intermediate language (MSIL) for a type that contains a readable property includes a `get`*_propertyname* method, and the MSIL for a type that contains a writable property includes a `set`*_propertyname* method.</span></span>

### <a name="methods"></a><span data-ttu-id="71c31-303">메서드</span><span class="sxs-lookup"><span data-stu-id="71c31-303">Methods</span></span>

<span data-ttu-id="71c31-304">메서드는 형식에 대해 수행할 수 있는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-304">A method describes operations that are available on the type.</span></span> <span data-ttu-id="71c31-305">메서드의 시그니처에서는 모든 매개 변수 및 반환 값에 허용되는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-305">A method's signature specifies the allowable types of all its parameters and of its return value.</span></span>

<span data-ttu-id="71c31-306">대부분의 메서드는 메서드 호출에 필요한 매개 변수 개수를 정확하게 정의하지만, 일부 메서드는 일정하지 않은 수의 매개 변수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-306">Although most methods define the precise number of parameters required for method calls, some methods support a variable number of parameters.</span></span> <span data-ttu-id="71c31-307">이러한 메서드에 대해 선언된 최종 매개 변수는 [ParamArrayAttribute](xref:System.ParamArrayAttribute) 특성으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-307">The final declared parameter of these methods is marked with the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute.</span></span> <span data-ttu-id="71c31-308">일반적으로 언어 컴파일러는 C#의 `params` 및 Visual Basic의 `ParamArray` 등과 같이 [ParamArrayAttribute](xref:System.ParamArrayAttribute)를 명시적으로 사용할 필요가 없도록 하는 키워드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-308">Language compilers typically provide a keyword, such as `params` in C# and `ParamArray` in Visual Basic, that makes explicit use of [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnecessary.</span></span>

### <a name="constructors"></a><span data-ttu-id="71c31-309">생성자</span><span class="sxs-lookup"><span data-stu-id="71c31-309">Constructors</span></span>

<span data-ttu-id="71c31-310">생성자는 클래스 또는 구조체의 새 인스턴스를 만드는 특수한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-310">A constructor is a special kind of method that creates new instances of a class or structure.</span></span> <span data-ttu-id="71c31-311">다른 메서드와 마찬가지로 생성자는 매개 변수를 포함할 수 있지만 반환 값은 가지지 않습니다. 즉, `void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-311">Like any other method, a constructor can include parameters; however, constructors have no return value (that is, they return `void`).</span></span> 

<span data-ttu-id="71c31-312">클래스의 소스 코드에서 생성자를 명시적으로 정의하지 않은 경우 컴파일러는 매개 변수가 없는 기본 생성자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-312">If the source code for a class does not explicitly define a constructor, the compiler includes a default (parameterless) constructor.</span></span> <span data-ttu-id="71c31-313">그러나 클래스의 소스 코드에서 매개 변수가 있는 생성자만 정의하는 경우 C# 컴파일러는 매개 변수가 없는 생성자를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-313">However, if the source code for a class defines only parameterized constructors, the C# compiler doesn't generate a parameterless constructor.</span></span>

<span data-ttu-id="71c31-314">구조체의 소스 코드에서 생성자를 정의하는 경우 해당 생성자에는 매개 변수가 있어야 합니다. 구조체에서는 기본 생성자(매개 변수가 없는 생성자)를 정의할 수 없으며 컴파일러는 구조체 또는 다른 값 형식에 대해 매개 변수가 없는 생성자를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-314">If the source code for a structure defines constructors, they must be parameterized; a structure cannot define a default (parameterless) constructor, and compilers do not generate parameterless constructors for structures or other value types.</span></span> <span data-ttu-id="71c31-315">모든 값 형식에는 암시적 기본 생성자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-315">All value types do have an implicit default constructor.</span></span> <span data-ttu-id="71c31-316">이 생성자는 공용 언어 런타임에서 구현되며 구조의 모든 필드를 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-316">This constructor is implemented by the common language runtime and initializes all fields of the structure to their default values.</span></span> 

### <a name="events"></a><span data-ttu-id="71c31-317">이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-317">Events</span></span>

<span data-ttu-id="71c31-318">이벤트는 응답할 수 있는 인시던트를 정의하고 이벤트를 구독, 구독 취소 및 발생시키기 위한 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-318">An event defines an incident that can be responded to, and defines methods for subscribing to, unsubscribing from, and raising the event.</span></span> <span data-ttu-id="71c31-319">이벤트는 주로 다른 형식에 상태 변경 내용을 알려주는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-319">Events are often used to inform other types of state changes.</span></span>

### <a name="nested-types"></a><span data-ttu-id="71c31-320">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="71c31-320">Nested types</span></span>

<span data-ttu-id="71c31-321">중첩 형식은 다른 형식의 멤버인 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-321">A nested type is a type that is a member of some other type.</span></span> <span data-ttu-id="71c31-322">중첩 형식은 포함하는 형식과 밀접하게 결합되어야 하고 일반 용도의 형식으로 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-322">Nested types should be tightly coupled to their containing type and must not be useful as a general-purpose type.</span></span> <span data-ttu-id="71c31-323">중첩 형식은 해당 선언 형식에서 중첩 형식의 인스턴스를 만들고 사용하며 중첩 형식의 사용이 공용 멤버에게 노출되지 않는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-323">Nested types are useful when the declaring type uses and creates instances of the nested type, and use of the nested type is not exposed in public members.</span></span>

<span data-ttu-id="71c31-324">중첩 형식은 일부 개발자에게 혼란을 줄 수 있으므로 불가피한 경우를 제외하고는 공개적으로 표시하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-324">Nested types are confusing to some developers and should not be publicly visible unless there is a compelling reason for visibility.</span></span> <span data-ttu-id="71c31-325">잘 디자인된 라이브러리에서 개발자는 개체를 인스턴스화하거나 변수를 선언할 때 중첩 형식을 거의 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-325">In a well-designed library, developers should rarely have to use nested types to instantiate objects or declare variables.</span></span>

## <a name="characteristics-of-type-members"></a><span data-ttu-id="71c31-326">형식 멤버의 특성</span><span class="sxs-lookup"><span data-stu-id="71c31-326">Characteristics of type members</span></span>

<span data-ttu-id="71c31-327">공용 형식 시스템에서 형식 멤버는 다양한 특성을 가질 수 있지만 언어에서 이런 특성을 모두 지원할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-327">The common type system allows type members to have a variety of characteristics; however, languages are not required to support all these characteristics.</span></span> <span data-ttu-id="71c31-328">다음 표에서는 멤버 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-328">The following table describes member characteristics.</span></span>

<span data-ttu-id="71c31-329">특성</span><span class="sxs-lookup"><span data-stu-id="71c31-329">Characteristic</span></span> | <span data-ttu-id="71c31-330">적용 대상</span><span class="sxs-lookup"><span data-stu-id="71c31-330">Can apply to</span></span> | <span data-ttu-id="71c31-331">설명</span><span class="sxs-lookup"><span data-stu-id="71c31-331">Description</span></span>
-------------- | ------------ | -----------
<span data-ttu-id="71c31-332">abstract</span><span class="sxs-lookup"><span data-stu-id="71c31-332">abstract</span></span> | <span data-ttu-id="71c31-333">메서드, 속성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-333">Methods, properties, and events</span></span> | <span data-ttu-id="71c31-334">형식에서 메서드 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-334">The type does not supply the method's implementation.</span></span> <span data-ttu-id="71c31-335">추상 메서드를 구현하거나 상속하는 형식에서 메서드에 대한 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-335">Types that inherit or implement abstract methods must supply an implementation for the method.</span></span> <span data-ttu-id="71c31-336">그러나 파생된 형식 자체가 추상 형식인 경우만은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-336">The only exception is when the derived type is itself an abstract type.</span></span> <span data-ttu-id="71c31-337">모든 추상 메서드는 가상 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-337">All abstract methods are virtual.</span></span>
<span data-ttu-id="71c31-338">private</span><span class="sxs-lookup"><span data-stu-id="71c31-338">private</span></span> | <span data-ttu-id="71c31-339">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-339">All</span></span> | <span data-ttu-id="71c31-340">멤버와 동일한 형식 또는 중첩된 형식 내에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-340">Accessible only from within the same type as the member, or within a nested type.</span></span>
<span data-ttu-id="71c31-341">family</span><span class="sxs-lookup"><span data-stu-id="71c31-341">family</span></span> | <span data-ttu-id="71c31-342">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-342">All</span></span> | <span data-ttu-id="71c31-343">멤버와 동일한 형식 내에서, 그리고 그 멤버에서 상속된 파생된 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-343">Accessible from within the same type as the member, and from derived types that inherit from it.</span></span>
<span data-ttu-id="71c31-344">assemby</span><span class="sxs-lookup"><span data-stu-id="71c31-344">assemby</span></span> | <span data-ttu-id="71c31-345">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-345">All</span></span> | <span data-ttu-id="71c31-346">형식이 정의된 어셈블리에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-346">Accessible only in the assembly in which the type is defined.</span></span>
<span data-ttu-id="71c31-347">family and assembly</span><span class="sxs-lookup"><span data-stu-id="71c31-347">family and assembly</span></span> | <span data-ttu-id="71c31-348">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-348">All</span></span> | <span data-ttu-id="71c31-349">패밀리와 어셈블리 모두에 대한 액세스 자격이 있는 형식에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-349">Accessible only from types that qualify for both family and assembly access.</span></span>
<span data-ttu-id="71c31-350">family or assemby</span><span class="sxs-lookup"><span data-stu-id="71c31-350">family or assemby</span></span> | <span data-ttu-id="71c31-351">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-351">All</span></span> | <span data-ttu-id="71c31-352">패밀리 또는 어셈블리에 대한 액세스 자격이 있는 형식에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-352">Accessible only from types that qualify for either family or assembly access.</span></span>
<span data-ttu-id="71c31-353">public</span><span class="sxs-lookup"><span data-stu-id="71c31-353">public</span></span> | <span data-ttu-id="71c31-354">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-354">All</span></span> | <span data-ttu-id="71c31-355">모든 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-355">Accessible from any type.</span></span>
<span data-ttu-id="71c31-356">final</span><span class="sxs-lookup"><span data-stu-id="71c31-356">final</span></span> | <span data-ttu-id="71c31-357">메서드, 속성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-357">Methods, properties, and events</span></span> | <span data-ttu-id="71c31-358">가상 메서드는 파생된 형식에서 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-358">The virtual method cannot be overridden in a derived type.</span></span>
<span data-ttu-id="71c31-359">initialize-only</span><span class="sxs-lookup"><span data-stu-id="71c31-359">initialize-only</span></span> | <span data-ttu-id="71c31-360">필드</span><span class="sxs-lookup"><span data-stu-id="71c31-360">Fields</span></span> | <span data-ttu-id="71c31-361">값을 초기화할 수만 있고 초기화 이후에는 작성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-361">The value can only be initialized, and cannot be written after initialization.</span></span>
<span data-ttu-id="71c31-362">인스턴스</span><span class="sxs-lookup"><span data-stu-id="71c31-362">instance</span></span> | <span data-ttu-id="71c31-363">필드, 메서드, 속성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-363">Fields, methods, properties, and events</span></span> | <span data-ttu-id="71c31-364">`static`(C#), `Shared`(Visual Basic), `virtual`(C#) 또는 `Overridable`(Visual Basic)로 표시되지 않은 멤버는 instance 키워드가 없는 인스턴스 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-364">If a member is not marked as `static` (C#), `Shared` (Visual Basic), `virtual` (C#), or `Overridable` (Visual Basic),  it is an instance member (there is no instance keyword).</span></span> <span data-ttu-id="71c31-365">멤버를 사용하는 개체 수만큼의 멤버 복사본이 메모리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-365">There will be as many copies of such members in memory as there are objects that use it.</span></span>
<span data-ttu-id="71c31-366">리터럴</span><span class="sxs-lookup"><span data-stu-id="71c31-366">literal</span></span> | <span data-ttu-id="71c31-367">필드</span><span class="sxs-lookup"><span data-stu-id="71c31-367">Fields</span></span> | <span data-ttu-id="71c31-368">필드에 할당되는 값은 컴파일 타임에 알려지는 기본 제공 값 형식의 고정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-368">The value assigned to the field is a fixed value, known at compile time, of a built-in value type.</span></span> <span data-ttu-id="71c31-369">리터럴 필드를 때로는 상수라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-369">Literal fields are sometimes referred to as constants.</span></span>
<span data-ttu-id="71c31-370">newslot 또는 override</span><span class="sxs-lookup"><span data-stu-id="71c31-370">newslot or override</span></span> | <span data-ttu-id="71c31-371">모두</span><span class="sxs-lookup"><span data-stu-id="71c31-371">All</span></span> | <span data-ttu-id="71c31-372">멤버가 시그니처가 같은 상속된 멤버와 상호 작용하는 방법을 정의합니다. `newslot`은 시그니처가 같은 상속된 멤버를 숨기고, `override`는 상속된 가상 메서드의 정의를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-372">Defines how the member interacts with inherited members that have the same signature: `newslot` hides inherited members that have the same signature; `override` replaces the definition of an inherited virtual method.</span></span> <span data-ttu-id="71c31-373">기본값은 새 슬롯입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-373">The default is newslot.</span></span>
<span data-ttu-id="71c31-374">정적</span><span class="sxs-lookup"><span data-stu-id="71c31-374">static</span></span> | <span data-ttu-id="71c31-375">필드, 메서드, 속성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-375">Fields, methods, properties, and events</span></span> | <span data-ttu-id="71c31-376">멤버는 형식의 특정 인스턴스가 아니라 멤버가 정의된 형식에 속합니다. 멤버는 형식의 인스턴스가 작성되지 않은 경우에도 존재하며 형식의 모든 인스턴스 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-376">The member belongs to the type it is defined on, not to a particular instance of the type; the member exists even if an instance of the type is not created, and it is shared among all instances of the type.</span></span>
<span data-ttu-id="71c31-377">virtual</span><span class="sxs-lookup"><span data-stu-id="71c31-377">virtual</span></span> | <span data-ttu-id="71c31-378">메서드, 속성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="71c31-378">Methods, properties, and events</span></span> | <span data-ttu-id="71c31-379">메서드는 파생된 형식에서 구현할 수 있으며 정적으로 또는 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-379">The method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span> <span data-ttu-id="71c31-380">동적 호출을 사용하는 경우, 메서드의 어떤 구현을 호출할지 결정하는 것은 컴파일 타임에 알려진 형식이 아니라 런타임에 호출을 수행하는 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-380">If dynamic invocation is used, the type of the instance that makes the call at run time (rather than the type known at compile time) determines which implementation of the method is called.</span></span> <span data-ttu-id="71c31-381">가상 메서드를 정적으로 호출하려면 원하는 버전의 메서드를 사용하는 형식으로 변수를 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-381">To invoke a virtual method statically, the variable might have to be cast to a type that uses the desired version of the method.</span></span>

### <a name="overloading"></a><span data-ttu-id="71c31-382">오버로딩</span><span class="sxs-lookup"><span data-stu-id="71c31-382">Overloading</span></span>

<span data-ttu-id="71c31-383">각 형식 멤버에는 고유의 시그니처가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-383">Each type member has a unique signature.</span></span> <span data-ttu-id="71c31-384">메서드 시그니처는 메서드 이름과 매개 변수 목록(메서드 인수의 순서 및 형식)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-384">Method signatures consist of the method name and a parameter list (the order and types of the method's arguments).</span></span> <span data-ttu-id="71c31-385">형식 내에서 시그니처를 다르게 하여 이름이 같은 여러 개의 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-385">Multiple methods with the same name can be defined within a type as long as their signatures differ.</span></span> <span data-ttu-id="71c31-386">이름이 같은 둘 이상의 메서드를 정의하면 메서드가 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-386">When two or more methods with the same name are defined, the method is said to be overloaded.</span></span> <span data-ttu-id="71c31-387">예를 들어 [System.Char](xref:System.Char)에서는 `IsDigit` 메서드가 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-387">For example, in [System.Char](xref:System.Char), the `IsDigit` method is overloaded.</span></span> <span data-ttu-id="71c31-388">한 메서드는 [Char](xref:System.Char)을 사용하고,</span><span class="sxs-lookup"><span data-stu-id="71c31-388">One method takes a [Char](xref:System.Char).</span></span> <span data-ttu-id="71c31-389">다른 메서드는 [String](xref:System.String) 및 [Int32](xref:System.Int32)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-389">The other method takes a [String](xref:System.String) and an [Int32](xref:System.Int32).</span></span> 

> [!NOTE]
> <span data-ttu-id="71c31-390">반환 형식은 메서드 시그니처의 일부로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-390">The return type is not considered part of a method's signature.</span></span> <span data-ttu-id="71c31-391">즉, 메서드는 반환 형식만 다를 경우에는 오버로드될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-391">That is, methods cannot be overloaded if they differ only by return type.</span></span>

### <a name="inheriting-overriding-and-hiding-members"></a><span data-ttu-id="71c31-392">멤버 상속, 재정의 및 숨기기</span><span class="sxs-lookup"><span data-stu-id="71c31-392">Inheriting, overriding, and hiding members</span></span>

<span data-ttu-id="71c31-393">파생된 형식에서는 기본 형식의 멤버를 모두 상속합니다. 즉, 파생된 형식에서 이러한 멤버를 정의하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-393">A derived type inherits all members of its base type; that is, these members are defined on, and available to, the derived type.</span></span> <span data-ttu-id="71c31-394">상속된 멤버의 동작 또는 품질을 다음과 같은 두 가지 방법으로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-394">The behavior or qualities of inherited members can be modified in two ways:</span></span> 

* <span data-ttu-id="71c31-395">파생된 형식에서 동일한 시그니처를 가진 새 멤버를 정의하여 상속 멤버를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-395">A derived type can hide an inherited member by defining a new member with the same signature.</span></span> <span data-ttu-id="71c31-396">이는 이전의 공용 멤버를 전용 멤버로 변경하거나 `final`로 표시된 상속된 메서드에 대해 새로운 동작을 정의하기 위해 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-396">This might be done to make a previously public member private or to define new behavior for an inherited method that is marked as `final`.</span></span>

* <span data-ttu-id="71c31-397">상속된 가상 메서드를 파생된 형식에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-397">A derived type can override an inherited virtual method.</span></span> <span data-ttu-id="71c31-398">메서드를 재정의하면 컴파일 타임에 알려진 변수의 형식이 아니라 런타임에 값의 형식을 기반으로 호출되는 메서드에 대한 새 정의가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-398">The overriding method provides a new definition of the method that will be invoked based on the type of the value at run time rather than the type of the variable known at compile time.</span></span> <span data-ttu-id="71c31-399">가상 메서드가 `final`로 표시되어 있지 않고 새 메서드에서 최소한 가상 메서드와 동일한 수준의 액세스 가능성을 갖는 경우에만 가상 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c31-399">A method can override a virtual method only if the virtual method is not marked as `final` and the new method is at least as accessible as the virtual method.</span></span>

## <a name="see-also"></a><span data-ttu-id="71c31-400">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71c31-400">See also</span></span>

[<span data-ttu-id="71c31-401">.NET Framework의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="71c31-401">Type conversion in the .NET Framework</span></span>](type-conversion.md)
