---
title: "특성에 저장된 정보 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a><span data-ttu-id="9da9b-102">특성에 저장된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-102">Retrieving Information Stored in Attributes</span></span>
<span data-ttu-id="9da9b-103">사용자 지정 특성을 검색 하는 것은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-103">Retrieving a custom attribute is a simple process.</span></span> <span data-ttu-id="9da9b-104">먼저, 검색 하려는 특성의 인스턴스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-104">First, declare an instance of the attribute you want to retrieve.</span></span> <span data-ttu-id="9da9b-105">그런 다음 사용 하는 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> 메서드를 검색 하려는 특성의 값을 새 특성을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-105">Then, use the <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> method to initialize the new attribute to the value of the attribute you want to retrieve.</span></span> <span data-ttu-id="9da9b-106">새 특성의 초기화 된 단순히 속성을 사용 하 여 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-106">Once the new attribute is initialized, you simply use its properties to get the values.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9da9b-107">이 항목에서는 실행 컨텍스트에 로드 된 코드에 대 한 특성을 검색 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-107">This topic describes how to retrieve attributes for code loaded into the execution context.</span></span> <span data-ttu-id="9da9b-108">리플렉션 전용 컨텍스트에 로드 된 코드에 대 한 특성을 검색 하려면 사용 해야 합니다는 <xref:System.Reflection.CustomAttributeData> 클래스에 표시 된 대로 [하는 방법: 리플렉션 컨텍스트에 로드 어셈블리](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-108">To retrieve attributes for code loaded into the reflection-only context, you must use the <xref:System.Reflection.CustomAttributeData> class, as shown in [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
 <span data-ttu-id="9da9b-109">이 섹션에서는 특성을 검색 하려면 다음과 같은 방법으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-109">This section describes the following ways to retrieve attributes:</span></span>  
  
-   [<span data-ttu-id="9da9b-110">특성의 단일 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-110">Retrieving a single instance of an attribute</span></span>](#cpconretrievingsingleinstanceofattribute)  
  
-   [<span data-ttu-id="9da9b-111">동일한 범위에 적용 되는 특성의 여러 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-111">Retrieving multiple instances of an attribute applied to the same scope</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [<span data-ttu-id="9da9b-112">서로 다른 범위에 적용 되는 특성의 여러 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-112">Retrieving multiple instances of an attribute applied to different scopes</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a><span data-ttu-id="9da9b-113">특성의 단일 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-113">Retrieving a Single Instance of an Attribute</span></span>  
 <span data-ttu-id="9da9b-114">다음 예제에서는 `DeveloperAttribute` (이전 섹션에서 설명)에 적용 되는 `MainApp` 클래스 수준에는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-114">In the following example, the `DeveloperAttribute` (described in the previous section) is applied to the `MainApp` class on the class level.</span></span> <span data-ttu-id="9da9b-115">`GetAttribute` 메서드 **GetCustomAttribute** 에 저장 된 값을 검색 `DeveloperAttribute` 콘솔에이 표시 하기 전에 클래스 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-115">The `GetAttribute` method uses **GetCustomAttribute** to retrieve the values stored in `DeveloperAttribute` on the class level before displaying them to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 <span data-ttu-id="9da9b-116">이 프로그램 실행 하면 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-116">This program displays the following text when executed.</span></span>  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 <span data-ttu-id="9da9b-117">특성이 없으면는 **GetCustomAttribute** 메서드 초기화 `MyAttribute` 를 null 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-117">If the attribute is not found, the **GetCustomAttribute** method initializes `MyAttribute` to a null value.</span></span> <span data-ttu-id="9da9b-118">이 예제에서는 검사 `MyAttribute` 이러한 인스턴스에 대 한 특성이 없는 경우에 사용자에 게 알리는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-118">This example checks `MyAttribute` for such an instance and notifies the user if no attribute is found.</span></span> <span data-ttu-id="9da9b-119">경우는 `DeveloperAttribute` 사전에 클래스 범위를 콘솔에 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-119">If the `DeveloperAttribute` is not found in the class scope, the following message displays to the console.</span></span>  
  
```  
The attribute was not found.   
```  
  
 <span data-ttu-id="9da9b-120">이 예에서는 특성 정의 현재 네임 스페이스에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-120">This example assumes that the attribute definition is in the current namespace.</span></span> <span data-ttu-id="9da9b-121">특성 정의가 있는 현재 네임 스페이스에 없는 경우 네임 스페이스를 가져올 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-121">Remember to import the namespace in which the attribute definition resides if it is not in the current namespace.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a><span data-ttu-id="9da9b-122">동일한 범위에 적용 되는 특성의 여러 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-122">Retrieving Multiple Instances of an Attribute Applied to the Same Scope</span></span>  
 <span data-ttu-id="9da9b-123">이전 예에서 검사 하는 클래스 및 찾을 특성에 전달 됩니다 <xref:System.Attribute.GetCustomAttribute%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-123">In the previous example, the class to inspect and the specific attribute to find are passed to <xref:System.Attribute.GetCustomAttribute%2A>.</span></span> <span data-ttu-id="9da9b-124">해당 코드에는 특성의 한 인스턴스는 클래스 수준에서 적용 하는 경우만 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-124">That code works well if only one instance of an attribute is applied on the class level.</span></span> <span data-ttu-id="9da9b-125">그러나 특성의 여러 인스턴스는 동일한 클래스 수준에서 적용 되는 경우, 고 **GetCustomAttribute** 메서드는 모든 정보를 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-125">However, if multiple instances of an attribute are applied on the same class level, the **GetCustomAttribute** method does not retrieve all the information.</span></span> <span data-ttu-id="9da9b-126">동일한 특성의 여러 인스턴스는 동일한 범위에 적용 하는 경우에 사용할 수 있습니다 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> 특성의 모든 인스턴스를 배열에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-126">In cases where multiple instances of the same attribute are applied to the same scope, you can use <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> to place all instances of an attribute into an array.</span></span> <span data-ttu-id="9da9b-127">예를 들어 두 인스턴스의 `DeveloperAttribute` 동일한 클래스의 클래스 수준에서 적용 되는 `GetAttribute` 두 특성 모두에 있는 정보를 표시 하는 메서드를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-127">For example, if two instances of `DeveloperAttribute` are applied on the class level of the same class, the `GetAttribute` method can be modified to display the information found in both attributes.</span></span> <span data-ttu-id="9da9b-128">동일한 수준에 여러 특성을 적용 하려면 기억 특성으로 정의 되어야 합니다는 **AllowMultiple** 속성이로 설정 **true** 에 <xref:System.AttributeUsageAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-128">Remember, to apply multiple attributes on the same level, the attribute must be defined with the **AllowMultiple** property set to **true** in the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="9da9b-129">다음 코드 예제를 사용 하는 방법을 보여 줍니다는 **GetCustomAttributes** 의 모든 인스턴스를 참조 하는 배열을 만드는 메서드를 `DeveloperAttribute` 모든 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-129">The following code example shows how to use the **GetCustomAttributes** method to create an array that references all instances of `DeveloperAttribute` in any given class.</span></span> <span data-ttu-id="9da9b-130">그러면 모든 특성의 값은 콘솔에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-130">The values of all attributes are then displayed to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 <span data-ttu-id="9da9b-131">특성이 발견 되 면이 코드 사용자를 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-131">If no attributes are found, this code alerts the user.</span></span> <span data-ttu-id="9da9b-132">두 인스턴스 모두에 정보가 포함 되는 그렇지 않은 경우 `DeveloperAttribute` 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-132">Otherwise, the information contained in both instances of `DeveloperAttribute` is displayed.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a><span data-ttu-id="9da9b-133">서로 다른 범위에 적용 되는 특성의 여러 인스턴스 검색</span><span class="sxs-lookup"><span data-stu-id="9da9b-133">Retrieving Multiple Instances of an Attribute Applied to Different Scopes</span></span>  
 <span data-ttu-id="9da9b-134"><xref:System.Attribute.GetCustomAttributes%2A> 및 <xref:System.Attribute.GetCustomAttribute%2A> 메서드 전체 클래스를 검색 하지 않으며 해당 클래스에 특성의 모든 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-134">The <xref:System.Attribute.GetCustomAttributes%2A> and <xref:System.Attribute.GetCustomAttribute%2A> methods do not search an entire class and return all instances of an attribute in that class.</span></span> <span data-ttu-id="9da9b-135">대신, 이러한 지정 된 메서드 또는 멤버를 하나만 한 번에 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-135">Rather, they search only one specified method or member at a time.</span></span> <span data-ttu-id="9da9b-136">모든 멤버에 적용 된 동일한 특성을 가진 클래스 있고 해당 멤버에 적용 된 모든 특성의 값을 검색 하려는 경우를 제공 해야 모든 메서드나 멤버 개별적으로 **GetCustomAttributes** 및  **GetCustomAttribute**합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-136">If you have a class with the same attribute applied to every member and you want to retrieve the values in all the attributes applied to those members, you must supply every method or member individually to **GetCustomAttributes** and **GetCustomAttribute**.</span></span>  
  
 <span data-ttu-id="9da9b-137">다음 코드 예제에서는 매개 변수로 클래스를 사용 하 고 검색는 `DeveloperAttribute` (정의 된 이전에)와 해당 클래스의 모든 개별 메서드에서 클래스 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-137">The following code example takes a class as a parameter and searches for the `DeveloperAttribute` (defined previously) on the class level and on every individual method of that class.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 <span data-ttu-id="9da9b-138">인스턴스가 없으면는 `DeveloperAttribute` 메서드 수준 또는 클래스 수준에서 발견 되는 `GetAttribute` 특성이 없습니다. 발견 된 사용자에 게 알리는 메서드와 메서드 또는 특성을 포함 하지 않는 클래스의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-138">If no instances of the `DeveloperAttribute` are found on the method level or class level, the `GetAttribute` method notifies the user that no attributes were found and displays the name of the method or class that does not contain the attribute.</span></span> <span data-ttu-id="9da9b-139">특성을 찾을 경우는 `Name`, `Level`, 및 `Reviewed` 필드가 콘솔에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-139">If an attribute is found, the `Name`, `Level`, and `Reviewed` fields are displayed to the console.</span></span>  
  
 <span data-ttu-id="9da9b-140">멤버를 사용할 수는 <xref:System.Type> 클래스 전달 된 클래스의 개별 메서드 및 멤버를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-140">You can use the members of the <xref:System.Type> class to get the individual methods and members in the passed class.</span></span> <span data-ttu-id="9da9b-141">이 예에서는 먼저 쿼리는 **형식** 클래스 수준에 대 한 특성 정보를 가져올 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-141">This example first queries the **Type** object to get attribute information for the class level.</span></span> <span data-ttu-id="9da9b-142">사용 하 여 다음으로, <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> 모든 메서드의 배열로 인스턴스를 배치 하려면 <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> 메서드 수준의 특성 정보를 검색 하기 위해 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-142">Next, it uses <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> to place instances of all methods into an array of <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objects to retrieve attribute information for the method level.</span></span> <span data-ttu-id="9da9b-143">사용할 수도 있습니다는 <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> 속성 수준에서 특성에 대 한 확인 하는 메서드 또는 <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> 생성자 수준에 특성에 대 한 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da9b-143">You can also use the <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> method to check for attributes on the property level or <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> to check for attributes on the constructor level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da9b-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9da9b-144">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9da9b-145">특성</span><span class="sxs-lookup"><span data-stu-id="9da9b-145">Attributes</span></span>](../../../docs/standard/attributes/index.md)
