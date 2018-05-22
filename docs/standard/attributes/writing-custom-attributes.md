---
title: 사용자 지정 특성 작성
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114d24c1fc523d5501deb4aa17f9541c5a918276
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="writing-custom-attributes"></a><span data-ttu-id="2ab75-102">사용자 지정 특성 작성</span><span class="sxs-lookup"><span data-stu-id="2ab75-102">Writing Custom Attributes</span></span>
<span data-ttu-id="2ab75-103">사용자 지정 특성을 직접 디자인하는 데 새로운 개념을 모두 알 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-103">To design your own custom attributes, you do not need to master many new concepts.</span></span> <span data-ttu-id="2ab75-104">개체 지향 프로그래밍에 익숙하고 클래스 디자인 방법을 알고 있는 것으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-104">If you are familiar with object-oriented programming and know how to design classes, you already have most of the knowledge needed.</span></span> <span data-ttu-id="2ab75-105">사용자 지정 특성은 본래 <xref:System.Attribute?displayProperty=nameWithType>에서 직접 또는 간접적으로 파생된 일반적인 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-105">Custom attributes are essentially traditional classes that derive directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ab75-106">일반적인 클래스와 마찬가지로 사용자 지정 특성에도 데이터를 저장하고 검색하는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-106">Just like traditional classes, custom attributes contain methods that store and retrieve data.</span></span>  
  
 <span data-ttu-id="2ab75-107">사용자 지정 특성 클래스를 올바르게 디자인하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-107">The primary steps to properly design custom attribute classes are as follows:</span></span>  
  
-   [<span data-ttu-id="2ab75-108">AttributeUsageAttribute 적용</span><span class="sxs-lookup"><span data-stu-id="2ab75-108">Applying the AttributeUsageAttribute</span></span>](#cpconapplyingattributeusageattribute)  
  
-   [<span data-ttu-id="2ab75-109">특성 클래스 선언</span><span class="sxs-lookup"><span data-stu-id="2ab75-109">Declaring the attribute class</span></span>](#cpcondeclaringattributeclass)  
  
-   [<span data-ttu-id="2ab75-110">생성자 선언</span><span class="sxs-lookup"><span data-stu-id="2ab75-110">Declaring constructors</span></span>](#cpcondeclaringconstructors)  
  
-   [<span data-ttu-id="2ab75-111">속성 선언</span><span class="sxs-lookup"><span data-stu-id="2ab75-111">Declaring properties</span></span>](#cpcondeclaringproperties)  
  
 <span data-ttu-id="2ab75-112">이 섹션에서는 각 단계에 대해 설명한 다음 마지막으로 [사용자 지정 특성 예제](#cpconcustomattributeexample)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-112">This section describes each of these steps and concludes with a [custom attribute example](#cpconcustomattributeexample).</span></span>  
  
<a name="cpconapplyingattributeusageattribute"></a>   
## <a name="applying-the-attributeusageattribute"></a><span data-ttu-id="2ab75-113">AttributeUsageAttribute 적용</span><span class="sxs-lookup"><span data-stu-id="2ab75-113">Applying the AttributeUsageAttribute</span></span>  
 <span data-ttu-id="2ab75-114">사용자 지정 특성을 선언하는 과정은 **AttributeUsageAttribute**를 사용하여 특성 클래스의 주요 특징 일부를 정의하는 것으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-114">A custom attribute declaration begins with the **AttributeUsageAttribute**, which defines some of the key characteristics of your attribute class.</span></span> <span data-ttu-id="2ab75-115">예를 들어 다른 클래스에서 특성을 상속할 수 있는지 여부를 지정하거나 해당 특성이 적용될 수 있는 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-115">For example, you can specify whether your attribute can be inherited by other classes or specify which elements the attribute can be applied to.</span></span> <span data-ttu-id="2ab75-116">다음 코드 조각에서는 **AttributeUsageAttribute**의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-116">The following code fragment demonstrates how to use the **AttributeUsageAttribute**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <span data-ttu-id="2ab75-117"><xref:System.AttributeUsageAttribute?displayProperty=nameWithType>에는 사용자 지정 특성을 만드는 데 필요한 세 가지 멤버인 [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2) 및 [AllowMultiple](#cpconwritingcustomattributesanchor3)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-117">The <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> has three members that are important for the creation of custom attributes: [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2), and [AllowMultiple](#cpconwritingcustomattributesanchor3).</span></span>  
  
<a name="cpconwritingcustomattributesanchor1"></a>   
### <a name="attributetargets-member"></a><span data-ttu-id="2ab75-118">AttributeTargets 멤버</span><span class="sxs-lookup"><span data-stu-id="2ab75-118">AttributeTargets Member</span></span>  
 <span data-ttu-id="2ab75-119">앞의 예제에는 특성을 모든 프로그램 요소에 적용하는 **AttributeTargets.All** 이 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-119">In the previous example, **AttributeTargets.All** is specified, indicating that this attribute can be applied to all program elements.</span></span> <span data-ttu-id="2ab75-120">또는 특성이 클래스에만 적용되도록 **AttributeTargets.Class**를 지정하거나 특성이 메서드에만 적용되도록 **AttributeTargets.Method**를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-120">Alternatively, you can specify **AttributeTargets.Class**, indicating that your attribute can be applied only to a class, or **AttributeTargets.Method**, indicating that your attribute can be applied only to a method.</span></span> <span data-ttu-id="2ab75-121">이러한 방법으로 사용자 지정 특성을 사용하여 모든 프로그램 요소의 설명을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-121">All program elements can be marked for description by a custom attribute in this manner.</span></span>  
  
 <span data-ttu-id="2ab75-122">또한 <xref:System.AttributeTargets>의 인스턴스를 여러 개 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-122">You can also pass multiple instances of <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="2ab75-123">다음 코드 조각에서는 사용자 지정 특성이 모든 클래스 또는 메서드에 적용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-123">The following code fragment specifies that a custom attribute can be applied to any class or method.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
<a name="cpconwritingcustomattributesanchor2"></a>   
### <a name="inherited-property"></a><span data-ttu-id="2ab75-124">Inherited 속성</span><span class="sxs-lookup"><span data-stu-id="2ab75-124">Inherited Property</span></span>  
 <span data-ttu-id="2ab75-125"><xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 특성이 적용된 클래스에서 파생된 클래스가 해당 특성을 상속할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-125">The <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property indicates whether your attribute can be inherited by classes that are derived from the classes to which your attribute is applied.</span></span> <span data-ttu-id="2ab75-126">이 특성에는 **true** (기본값) 또는 **false** 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-126">This property takes either a **true** (the default) or **false** flag.</span></span> <span data-ttu-id="2ab75-127">예를 들어 다음 코드 예제에서 `MyAttribute` 의 <xref:System.AttributeUsageAttribute.Inherited%2A> 값은 기본값인 **true**인 반면 `YourAttribute` 의 <xref:System.AttributeUsageAttribute.Inherited%2A> 값은 **false**입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-127">For example, in the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.Inherited%2A> value of **true**, while `YourAttribute` has an <xref:System.AttributeUsageAttribute.Inherited%2A> value of **false**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 <span data-ttu-id="2ab75-128">이 두 특성은 기본 클래스인 `MyClass`의 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-128">The two attributes are then applied to a method in the base class `MyClass`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 <span data-ttu-id="2ab75-129">마지막으로, `YourClass` 클래스가 기본 클래스인 `MyClass`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-129">Finally, the class `YourClass` is inherited from the base class `MyClass`.</span></span> <span data-ttu-id="2ab75-130">`MyMethod` 메서드는 `MyAttribute`를 표시하지만 `YourAttribute`는 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-130">The method `MyMethod` shows `MyAttribute`, but not `YourAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
<a name="cpconwritingcustomattributesanchor3"></a>   
### <a name="allowmultiple-property"></a><span data-ttu-id="2ab75-131">AllowMultiple 속성</span><span class="sxs-lookup"><span data-stu-id="2ab75-131">AllowMultiple Property</span></span>  
 <span data-ttu-id="2ab75-132"><xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> 속성은 하나의 요소에 대해 특성의 인스턴스가 여러 개 있을 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-132">The <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> property indicates whether multiple instances of your attribute can exist on an element.</span></span> <span data-ttu-id="2ab75-133">**true**로 설정되어 있으면 여러 개의 인스턴스가 있을 수 있으며, **false** (기본값)로 설정되어 있으면 하나의 인스턴스만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-133">If set to **true**, multiple instances are allowed; if set to **false** (the default), only one instance is allowed.</span></span>  
  
 <span data-ttu-id="2ab75-134">다음 예제에서 `MyAttribute` 의 <xref:System.AttributeUsageAttribute.AllowMultiple%2A> 값은 기본값인 **false**인 반면 `YourAttribute` 의 값은 **true**입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-134">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.AllowMultiple%2A> value of **false**, while `YourAttribute` has a value of **true**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 <span data-ttu-id="2ab75-135">이 특성의 인스턴스가 여러 개 적용되면 `MyAttribute` 에서는 컴파일러 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-135">When multiple instances of these attributes are applied, `MyAttribute` produces a compiler error.</span></span> <span data-ttu-id="2ab75-136">다음 코드 예제에서는 `YourAttribute` 를 올바르게 사용한 경우와 `MyAttribute`를 잘못 사용한 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-136">The following code example shows the valid use of `YourAttribute` and the invalid use of `MyAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 <span data-ttu-id="2ab75-137"><xref:System.AttributeUsageAttribute.AllowMultiple%2A> 속성과 <xref:System.AttributeUsageAttribute.Inherited%2A> 속성이 모두 **true**로 설정된 경우에는 다른 클래스에서 상속된 클래스가 특성을 상속할 수 있으며 동일한 자식 클래스에 적용된 동일한 특성의 다른 인스턴스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-137">If both the <xref:System.AttributeUsageAttribute.AllowMultiple%2A> property and the <xref:System.AttributeUsageAttribute.Inherited%2A> property are set to **true**, a class that is inherited from another class can inherit an attribute and have another instance of the same attribute applied in the same child class.</span></span> <span data-ttu-id="2ab75-138"><xref:System.AttributeUsageAttribute.AllowMultiple%2A> 이 **false**로 설정된 경우에는 자식 클래스에 있는 동일한 특성의 새 인스턴스가 부모 클래스에 있는 모든 특성 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-138">If <xref:System.AttributeUsageAttribute.AllowMultiple%2A> is set to **false**, the values of any attributes in the parent class will be overwritten by new instances of the same attribute in the child class.</span></span>  
  
<a name="cpcondeclaringattributeclass"></a>   
## <a name="declaring-the-attribute-class"></a><span data-ttu-id="2ab75-139">특성 클래스 선언</span><span class="sxs-lookup"><span data-stu-id="2ab75-139">Declaring the Attribute Class</span></span>  
 <span data-ttu-id="2ab75-140"><xref:System.AttributeUsageAttribute>를 적용한 다음 특성을 상세히 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-140">After you apply the <xref:System.AttributeUsageAttribute>, you can begin to define the specifics of your attribute.</span></span> <span data-ttu-id="2ab75-141">특성 클래스를 선언하는 과정은 다음 코드에서처럼 일반적인 클래스를 선언하는 과정과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-141">The declaration of an attribute class looks similar to the declaration of a traditional class, as demonstrated by the following code.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 <span data-ttu-id="2ab75-142">이 특성 정의는 다음과 같은 몇 가지 점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-142">This attribute definition demonstrates the following points:</span></span>  
  
-   <span data-ttu-id="2ab75-143">특성 클래스는 공용 클래스로 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-143">Attribute classes must be declared as public classes.</span></span>  
  
-   <span data-ttu-id="2ab75-144">특성 클래스의 이름은 규칙에 따라 **Attribute**로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-144">By convention, the name of the attribute class ends with the word **Attribute**.</span></span> <span data-ttu-id="2ab75-145">이 규칙을 반드시 적용할 필요는 없지만 가독성을 향상시키기 위해 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-145">While not required, this convention is recommended for readability.</span></span> <span data-ttu-id="2ab75-146">특성이 적용될 때 Attribute라는 단어를 포함시키지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-146">When the attribute is applied, the inclusion of the word Attribute is optional.</span></span>  
  
-   <span data-ttu-id="2ab75-147">모든 특성 클래스는 **System.Attribute**에서 직접 또는 간접적으로 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-147">All attribute classes must inherit directly or indirectly from **System.Attribute**.</span></span>  
  
-   <span data-ttu-id="2ab75-148">Microsoft VisualBasic에서는 모든 사용자 지정 특성 클래스에 **AttributeUsageAttribute** 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-148">In Microsoft Visual Basic, all custom attribute classes must have the **AttributeUsageAttribute** attribute.</span></span>  
  
<a name="cpcondeclaringconstructors"></a>   
## <a name="declaring-constructors"></a><span data-ttu-id="2ab75-149">생성자 선언</span><span class="sxs-lookup"><span data-stu-id="2ab75-149">Declaring Constructors</span></span>  
 <span data-ttu-id="2ab75-150">특성은 일반적인 클래스와 동일한 방법으로 생성자를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-150">Attributes are initialized with constructors in the same way as traditional classes.</span></span> <span data-ttu-id="2ab75-151">다음 코드 조각에서는 일반적인 특성 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-151">The following code fragment illustrates a typical attribute constructor.</span></span> <span data-ttu-id="2ab75-152">이 공용 생성자는 매개 변수를 적용하여 해당 매개 변수의 값을 멤버 변수와 같은 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-152">This public constructor takes a parameter and sets its value equal to a member variable.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 <span data-ttu-id="2ab75-153">생성자를 오버로드하여 값을 다르게 조합하여 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-153">You can overload the constructor to accommodate different combinations of values.</span></span> <span data-ttu-id="2ab75-154">또한 사용자 지정 특성 클래스에 대한 [속성](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52)을 정의하면 특성을 초기화 할 때 명명된 매개변수와 위치 매개 변수를 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-154">If you also define a [property](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52) for your custom attribute class, you can use a combination of named and positional parameters when initializing the attribute.</span></span> <span data-ttu-id="2ab75-155">일반적으로 모든 필수 매개 변수는 positional로 정의하고 모든 선택적 매개 변수는 named로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-155">Typically, you define all required parameters as positional and all optional parameters as named.</span></span> <span data-ttu-id="2ab75-156">이때 필수 매개 변수가 없으면 특성을 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-156">In this case, the attribute cannot be initialized without the required parameter.</span></span> <span data-ttu-id="2ab75-157">다른 모든 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-157">All other parameters are optional.</span></span> <span data-ttu-id="2ab75-158">Visual Basic에서는 특성 클래스의 생성자가 ParamArray 인수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-158">Note that in Visual Basic, constructors for an attribute class should not use a ParamArray argument.</span></span>  
  
 <span data-ttu-id="2ab75-159">다음 코드 예제에서는 앞의 생성자를 사용하는 특성이 선택적 매개 변수와 필수 매개 변수를 사용하여 적용되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-159">The following code example shows how an attribute that uses the previous constructor can be applied using optional and required parameters.</span></span> <span data-ttu-id="2ab75-160">이 예제에서는 특성에 하나의 필수 부울 값과 하나의 선택적 문자열 속성이 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-160">It assumes that the attribute has one required Boolean value and one optional string property.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
<a name="cpcondeclaringproperties"></a>   
## <a name="declaring-properties"></a><span data-ttu-id="2ab75-161">속성 선언</span><span class="sxs-lookup"><span data-stu-id="2ab75-161">Declaring Properties</span></span>  
 <span data-ttu-id="2ab75-162">명명된 매개 변수를 정의하거나 특성에 의해 저장된 값을 쉽게 반환하려면 [속성](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52)을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-162">If you want to define a named parameter or provide an easy way to return the values stored by your attribute, declare a [property](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span></span> <span data-ttu-id="2ab75-163">특성 속성은 반환될 데이터 형식에 대한 설명이 포함된 공용 엔터티로 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-163">Attribute properties should be declared as public entities with a description of the data type that will be returned.</span></span> <span data-ttu-id="2ab75-164">속성 값을 포함할 변수를 정의한 다음 이를 **get** 및 **set** 메서드와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-164">Define the variable that will hold the value of your property and associate it with the **get** and **set** methods.</span></span> <span data-ttu-id="2ab75-165">다음 코드 예제에서는 특성에 간단한 속성을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-165">The following code example demonstrates how to implement a simple property in your attribute.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
<a name="cpconcustomattributeexample"></a>   
## <a name="custom-attribute-example"></a><span data-ttu-id="2ab75-166">사용자 지정 특성 예제</span><span class="sxs-lookup"><span data-stu-id="2ab75-166">Custom Attribute Example</span></span>  
 <span data-ttu-id="2ab75-167">이 섹션에서는 앞에서 설명한 내용을 종합하고, 간단한 특성을 디자인하여 코드 섹션의 작성자에 대한 정보를 나타내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-167">This section incorporates the previous information and shows how to design a simple attribute that documents information about the author of a section of code.</span></span> <span data-ttu-id="2ab75-168">이 예제에서 사용된 특성에는 프로그래머의 이름 및 수준과 코드 검토 여부가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-168">The attribute in this example stores the name and level of the programmer, and whether the code has been reviewed.</span></span> <span data-ttu-id="2ab75-169">이 특성은 저장할 실제 값이 포함된 세 개의 private 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-169">It uses three private variables to store the actual values to save.</span></span> <span data-ttu-id="2ab75-170">각 변수는 값을 가져오고 설정하는 public 속성으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-170">Each variable is represented by a public property that gets and sets the values.</span></span> <span data-ttu-id="2ab75-171">마지막으로 두 개의 필수 매개 변수를 사용하여 생성자가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-171">Finally, the constructor is defined with two required parameters.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 <span data-ttu-id="2ab75-172">전체 이름인 `DeveloperAttribute`나 약식 이름인 `Developer`를 다음 중 한 가지 방법으로 사용하여 이 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-172">You can apply this attribute using the full name, `DeveloperAttribute`, or using the abbreviated name, `Developer`, in one of the following ways.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 <span data-ttu-id="2ab75-173">첫 번째 예제에서는 필수 요소인 명명된 매개 변수만 사용하여 적용된 특성을 보여 주고, 두 번째 예제에서는 필수 매개 변수와 선택적 매개 변수를 모두 사용하여 적용된 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ab75-173">The first example shows the attribute applied with only the required named parameters, while the second example shows the attribute applied with both the required and optional parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab75-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ab75-174">See Also</span></span>  
 <xref:System.Attribute?displayProperty=nameWithType>  
 <xref:System.AttributeUsageAttribute>  
 [<span data-ttu-id="2ab75-175">특성</span><span class="sxs-lookup"><span data-stu-id="2ab75-175">Attributes</span></span>](../../../docs/standard/attributes/index.md)
