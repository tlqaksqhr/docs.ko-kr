---
title: "구조체 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 67fa4f764e6e40041e4b8e37eccbd1adb2b509d3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="a184b-102">구조체 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a184b-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="a184b-103">`struct` 형식은 `Point`, `Rectangle`, `Color`등의 간단한 개체를 나타내는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="a184b-104">점을 [자동으로 구현된 속성](../../../csharp/language-reference/keywords/class.md) 이 있는 [클래스](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)로 표현할 수도 있지만 일부 시나리오에서는 [구조체](../../../csharp/language-reference/keywords/struct.md) 를 사용하는 것이 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="a184b-105">예를 들어 1000개의 `Point` 개체가 있는 배열을 선언하는 경우에는 각 개체를 참조하기 위해 추가 메모리를 할당하게 되며, 이러한 경우 구조체가 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="a184b-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 에 <xref:System.Drawing.Point>라는 개체가 포함되어 있으므로 이 예제의 구조체 이름은 "CoOrds"로 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "CoOrds" instead.</span></span>  
  
 <span data-ttu-id="a184b-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a184b-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="a184b-108">구조체에 대해 기본 생성자(매개 변수 없음)를 정의하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-108">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="a184b-109">구조체 본문에서 인스턴스 필드를 초기화해도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-109">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="a184b-110">구조체의 멤버는 매개 변수가 있는 생성자를 사용하거나 구조체가 선언된 후 멤버에 개별적으로 액세스하는 방법으로만 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-110">You can initialize struct members only by using a parameterized constructor or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="a184b-111">전용 멤버 또는 다른 방법으로 액세스할 수 없는 멤버는 생성자 내부에서만 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-111">Any private or otherwise inaccessible members can be initialized only in a constructor.</span></span>  
  
 <span data-ttu-id="a184b-112">[new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 구조체 개체를 생성할 경우 구조체 개체가 생성된 후에 적절한 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-112">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called.</span></span> <span data-ttu-id="a184b-113">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-113">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="a184b-114">이런 경우에는 생성자를 호출하지 않으므로 할당이 더 효율적으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-114">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="a184b-115">하지만 필드가 할당되지 않은 상태로 남아 있게 되며 개체를 사용하려면 모든 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-115">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span>  
  
 <span data-ttu-id="a184b-116">구조체에 참조 형식인 멤버가 있는 경우 멤버의 기본 생성자가 명시적으로 호출되어야 합니다. 그렇지 않으면 멤버가 할당되지 않은 상태로 남아 있게 되므로 구조체를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-116">When a struct contains a reference type as a member, the default constructor of the member must be invoked explicitly, otherwise the member remains unassigned and the struct cannot be used.</span></span> <span data-ttu-id="a184b-117">이 경우 컴파일러 오류 CS0171이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-117">(This results in compiler error CS0171.)</span></span>  
  
 <span data-ttu-id="a184b-118">클래스의 경우와는 달리 구조체에 대한 상속은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="a184b-119">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="a184b-120">그러나 구조체는 기본 클래스 <xref:System.Object>에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="a184b-121">구조체는 클래스에서 인터페이스를 구현하는 것과 동일한 방식으로 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="a184b-122">`struct`키워드를 사용하여 클래스를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="a184b-123">C#에서 클래스와 구조체는 구문적으로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="a184b-124">구조체는 값 형식인 반면 클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="a184b-125">자세한 내용은 [값 형식](../../../csharp/language-reference/keywords/value-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a184b-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="a184b-126">참조 형식 구문이 필요한 경우가 아니라면 작은 클래스는 구조체로 대신 선언하면 시스템에서 보다 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="a184b-127">예제 1</span><span class="sxs-lookup"><span data-stu-id="a184b-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="a184b-128">설명</span><span class="sxs-lookup"><span data-stu-id="a184b-128">Description</span></span>  
 <span data-ttu-id="a184b-129">이 예제에서는 기본 생성자와 매개 변수가 있는 생성자 둘 다를 사용하여 `struct` 를 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a184b-130">코드</span><span class="sxs-lookup"><span data-stu-id="a184b-130">Code</span></span>  
 <span data-ttu-id="a184b-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a184b-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="a184b-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a184b-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="a184b-133">예제 2</span><span class="sxs-lookup"><span data-stu-id="a184b-133">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="a184b-134">설명</span><span class="sxs-lookup"><span data-stu-id="a184b-134">Description</span></span>  
 <span data-ttu-id="a184b-135">이 예제에서는 구조체의 특징에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-135">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="a184b-136">여기서는 `new` 연산자를 사용하지 않고 CoOrds 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-136">It creates a CoOrds object without using the `new` operator.</span></span> <span data-ttu-id="a184b-137">`struct` 를 `class`로 바꾸면 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a184b-137">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a184b-138">코드</span><span class="sxs-lookup"><span data-stu-id="a184b-138">Code</span></span>  
 <span data-ttu-id="a184b-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a184b-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="a184b-140">[!code-cs[csProgGuideObjects #3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a184b-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a184b-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a184b-141">See Also</span></span>  
 <span data-ttu-id="a184b-142">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a184b-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a184b-143">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="a184b-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="a184b-144">구조체</span><span class="sxs-lookup"><span data-stu-id="a184b-144">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

