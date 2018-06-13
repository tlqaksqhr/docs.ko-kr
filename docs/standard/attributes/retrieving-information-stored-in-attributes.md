---
title: 특성에 저장된 정보 검색
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b6799763b4635632728561eef2820b26820aeed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570410"
---
# <a name="retrieving-information-stored-in-attributes"></a><span data-ttu-id="d4d6f-102">특성에 저장된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-102">Retrieving Information Stored in Attributes</span></span>
<span data-ttu-id="d4d6f-103">사용자 지정 특성 검색은 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-103">Retrieving a custom attribute is a simple process.</span></span> <span data-ttu-id="d4d6f-104">먼저, 검색하려는 특성의 인스턴스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-104">First, declare an instance of the attribute you want to retrieve.</span></span> <span data-ttu-id="d4d6f-105">그런 다음, <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> 메서드를 사용하여 검색하려는 특성 값으로 새 특성을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-105">Then, use the <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> method to initialize the new attribute to the value of the attribute you want to retrieve.</span></span> <span data-ttu-id="d4d6f-106">새 특성이 초기화되면 해당 속성을 사용하여 값을 가져오기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-106">Once the new attribute is initialized, you simply use its properties to get the values.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d4d6f-107">이 항목에서는 실행 컨텍스트에 로드된 코드에 대한 특성을 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-107">This topic describes how to retrieve attributes for code loaded into the execution context.</span></span> <span data-ttu-id="d4d6f-108">리플렉션 전용 컨텍스트에 로드된 코드의 특성을 검색하려면 [방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)와 같이 <xref:System.Reflection.CustomAttributeData> 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-108">To retrieve attributes for code loaded into the reflection-only context, you must use the <xref:System.Reflection.CustomAttributeData> class, as shown in [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
 <span data-ttu-id="d4d6f-109">이 섹션에서는 특성을 검색하는 다음 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-109">This section describes the following ways to retrieve attributes:</span></span>  
  
-   [<span data-ttu-id="d4d6f-110">특성의 단일 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-110">Retrieving a single instance of an attribute</span></span>](#cpconretrievingsingleinstanceofattribute)  
  
-   [<span data-ttu-id="d4d6f-111">동일한 범위에 적용된 특성의 다중 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-111">Retrieving multiple instances of an attribute applied to the same scope</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [<span data-ttu-id="d4d6f-112">다양한 범위에 적용된 특성의 다중 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-112">Retrieving multiple instances of an attribute applied to different scopes</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a><span data-ttu-id="d4d6f-113">특성의 단일 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-113">Retrieving a Single Instance of an Attribute</span></span>  
 <span data-ttu-id="d4d6f-114">다음 예제에서 `DeveloperAttribute`(이전 섹션에 설명되어 있음)는 클래스 수준의 `MainApp` 클래스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-114">In the following example, the `DeveloperAttribute` (described in the previous section) is applied to the `MainApp` class on the class level.</span></span> <span data-ttu-id="d4d6f-115">`GetAttribute` 메서드는 클래스 수준의 `DeveloperAttribute`에 저장된 값을 콘솔에 표시하기 전에 먼저 **GetCustomAttribute**를 사용하여 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-115">The `GetAttribute` method uses **GetCustomAttribute** to retrieve the values stored in `DeveloperAttribute` on the class level before displaying them to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 <span data-ttu-id="d4d6f-116">이 프로그램은 실행 시 다음 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-116">This program displays the following text when executed.</span></span>  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 <span data-ttu-id="d4d6f-117">특성을 찾을 수 없는 경우 **GetCustomAttribute** 메서드는 `MyAttribute`를 null 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-117">If the attribute is not found, the **GetCustomAttribute** method initializes `MyAttribute` to a null value.</span></span> <span data-ttu-id="d4d6f-118">이 예제는 해당 인스턴스의 `MyAttribute`를 확인하고 특성을 찾을 수 없는 경우 사용자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-118">This example checks `MyAttribute` for such an instance and notifies the user if no attribute is found.</span></span> <span data-ttu-id="d4d6f-119">클래스 범위에서 `DeveloperAttribute`를 찾을 수 없는 경우 다음 메시지가 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-119">If the `DeveloperAttribute` is not found in the class scope, the following message displays to the console.</span></span>  
  
```  
The attribute was not found.   
```  
  
 <span data-ttu-id="d4d6f-120">이 예제에서는 특성 정의가 현재 네임스페이스에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-120">This example assumes that the attribute definition is in the current namespace.</span></span> <span data-ttu-id="d4d6f-121">현재 네임스페이스에 없는 경우 특성 정의가 있는 네임스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-121">Remember to import the namespace in which the attribute definition resides if it is not in the current namespace.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a><span data-ttu-id="d4d6f-122">동일한 범위에 적용된 특성의 다중 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-122">Retrieving Multiple Instances of an Attribute Applied to the Same Scope</span></span>  
 <span data-ttu-id="d4d6f-123">이전 예제에서는 검사할 클래스 및 찾을 특정 특성이 <xref:System.Attribute.GetCustomAttribute%2A>에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-123">In the previous example, the class to inspect and the specific attribute to find are passed to <xref:System.Attribute.GetCustomAttribute%2A>.</span></span> <span data-ttu-id="d4d6f-124">특성의 인스턴스 하나만 클래스 수준에서 적용되는 경우 해당 코드가 제대로 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-124">That code works well if only one instance of an attribute is applied on the class level.</span></span> <span data-ttu-id="d4d6f-125">그러나 특성의 여러 인스턴스가 동일한 클래스 수준에서 적용되는 경우 **GetCustomAttribute** 메서드가 모든 정보를 검색하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-125">However, if multiple instances of an attribute are applied on the same class level, the **GetCustomAttribute** method does not retrieve all the information.</span></span> <span data-ttu-id="d4d6f-126">동일한 특성의 여러 인스턴스가 동일한 범위에 적용되는 경우 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>를 사용하여 특성의 모든 인스턴스를 배열에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-126">In cases where multiple instances of the same attribute are applied to the same scope, you can use <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> to place all instances of an attribute into an array.</span></span> <span data-ttu-id="d4d6f-127">예를 들어 `DeveloperAttribute`의 두 인스턴스가 동일한 클래스의 클래스 수준에서 적용되는 경우 `GetAttribute` 메서드를 수정하여 두 특성 모두에서 찾은 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-127">For example, if two instances of `DeveloperAttribute` are applied on the class level of the same class, the `GetAttribute` method can be modified to display the information found in both attributes.</span></span> <span data-ttu-id="d4d6f-128">동일한 수준의 여러 특성을 적용하려면 <xref:System.AttributeUsageAttribute>에서 **AllowMultiple** 속성을 **true**로 설정하여 특성을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-128">Remember, to apply multiple attributes on the same level, the attribute must be defined with the **AllowMultiple** property set to **true** in the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="d4d6f-129">다음 코드 예제에서는 **GetCustomAttributes** 메서드를 사용하여 지정된 특정 클래스에서 `DeveloperAttribute`의 모든 인스턴스를 참조하는 배열을 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-129">The following code example shows how to use the **GetCustomAttributes** method to create an array that references all instances of `DeveloperAttribute` in any given class.</span></span> <span data-ttu-id="d4d6f-130">이렇게 하면 모든 특성 값이 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-130">The values of all attributes are then displayed to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 <span data-ttu-id="d4d6f-131">특성을 찾을 수 없는 경우 이 코드는 사용자에게 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-131">If no attributes are found, this code alerts the user.</span></span> <span data-ttu-id="d4d6f-132">특성을 찾은 경우 `DeveloperAttribute`의 두 인스턴스 모두에 포함된 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-132">Otherwise, the information contained in both instances of `DeveloperAttribute` is displayed.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a><span data-ttu-id="d4d6f-133">다양한 범위에 적용된 특성의 다중 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="d4d6f-133">Retrieving Multiple Instances of an Attribute Applied to Different Scopes</span></span>  
 <span data-ttu-id="d4d6f-134"><xref:System.Attribute.GetCustomAttributes%2A> 및 <xref:System.Attribute.GetCustomAttribute%2A> 메서드는 클래스 전체를 검색하지 않고 해당 클래스 특성의 모든 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-134">The <xref:System.Attribute.GetCustomAttributes%2A> and <xref:System.Attribute.GetCustomAttribute%2A> methods do not search an entire class and return all instances of an attribute in that class.</span></span> <span data-ttu-id="d4d6f-135">대신, 한 번에 하나의 지정된 메서드 또는 멤버만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-135">Rather, they search only one specified method or member at a time.</span></span> <span data-ttu-id="d4d6f-136">모든 멤버에 동일한 특성이 적용된 클래스가 있는데 해당 멤버에 적용된 모든 특성의 값을 검색하려는 경우 모든 메서드 또는 멤버를 **GetCustomAttributes** 및 **GetCustomAttribute**에 개별적으로 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-136">If you have a class with the same attribute applied to every member and you want to retrieve the values in all the attributes applied to those members, you must supply every method or member individually to **GetCustomAttributes** and **GetCustomAttribute**.</span></span>  
  
 <span data-ttu-id="d4d6f-137">다음 코드 예제에서는 클래스를 매개 변수로 사용하여 클래스 수준에서 그리고 해당 클래스의 모든 개별 메서드에서 `DeveloperAttribute`(이전에 정의됨)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-137">The following code example takes a class as a parameter and searches for the `DeveloperAttribute` (defined previously) on the class level and on every individual method of that class.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 <span data-ttu-id="d4d6f-138">메서드 수준 또는 클래스 수준에서 `DeveloperAttribute`의 인스턴스를 찾을 수 없는 경우 `GetAttribute` 메서드는 특성을 찾을 수 없음을 사용자에게 알리고 특성이 포함되지 않은 메서드 또는 클래스의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-138">If no instances of the `DeveloperAttribute` are found on the method level or class level, the `GetAttribute` method notifies the user that no attributes were found and displays the name of the method or class that does not contain the attribute.</span></span> <span data-ttu-id="d4d6f-139">특성을 찾은 경우 `Name`, `Level` 및 `Reviewed` 필드가 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-139">If an attribute is found, the `Name`, `Level`, and `Reviewed` fields are displayed to the console.</span></span>  
  
 <span data-ttu-id="d4d6f-140"><xref:System.Type> 클래스의 멤버를 사용하여 전달된 클래스의 개별 메서드 및 멤버를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-140">You can use the members of the <xref:System.Type> class to get the individual methods and members in the passed class.</span></span> <span data-ttu-id="d4d6f-141">이 예제에서는 먼저 **Type** 개체를 쿼리하여 클래스 수준에 대한 특성 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-141">This example first queries the **Type** object to get attribute information for the class level.</span></span> <span data-ttu-id="d4d6f-142">그런 다음, 메서드 수준의 특성 정보를 검색하기 위해 <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>를 사용하여 모든 메서드의 인스턴스를 <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> 개체의 배열에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-142">Next, it uses <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> to place instances of all methods into an array of <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objects to retrieve attribute information for the method level.</span></span> <span data-ttu-id="d4d6f-143">또한 <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> 메서드를 사용하여 속성 수준의 특성을 확인하거나 <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType>를 사용하여 생성자 수준의 특성을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d6f-143">You can also use the <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> method to check for attributes on the property level or <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> to check for attributes on the constructor level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d6f-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4d6f-144">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d4d6f-145">특성</span><span class="sxs-lookup"><span data-stu-id="d4d6f-145">Attributes</span></span>](../../../docs/standard/attributes/index.md)
