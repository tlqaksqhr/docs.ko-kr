---
title: 형식 정보 보기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc957b345c1e66059551508f73e37e0f6d69f6cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399745"
---
# <a name="viewing-type-information"></a><span data-ttu-id="cc9c9-102">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="cc9c9-102">Viewing Type Information</span></span>
<span data-ttu-id="cc9c9-103"><xref:System.Type?displayProperty=nameWithType> 클래스는 리플렉션의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-103">The <xref:System.Type?displayProperty=nameWithType> class is central to reflection.</span></span> <span data-ttu-id="cc9c9-104">공용 언어 런타임은 리플렉션이 요청할 때 로드된 형식의 **Type**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-104">The common language runtime creates the **Type** for a loaded type when reflection requests it.</span></span> <span data-ttu-id="cc9c9-105">**Type** 개체의 메서드, 필드, 속성 및 중첩 클래스를 사용하여 해당 형식에 대한 모든 것을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-105">You can use a **Type** object's methods, fields, properties, and nested classes to find out everything about that type.</span></span>  
  
 <span data-ttu-id="cc9c9-106"><xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 또는 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>를 사용하여 로드되지 않은 어셈블리에서 **Type** 개체를 가져와 원하는 형식 또는 형식 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-106">Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> to obtain **Type** objects from assemblies that have not been loaded, passing in the name of the type or types you want.</span></span> <span data-ttu-id="cc9c9-107"><xref:System.Type.GetType%2A?displayProperty=nameWithType>을 사용하여 이미 로드된 어셈블리에서 **Type** 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-107">Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> to get the **Type** objects from an assembly that is already loaded.</span></span> <span data-ttu-id="cc9c9-108"><xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> 및 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>를 사용하여 모듈 **Type** 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-108">Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> and <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> to obtain module **Type** objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc9c9-109">제네릭 형식 및 메서드를 검사하고 조작하려면 [리플렉션 및 제네릭 형식](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) 및 [방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-109">If you want to examine and manipulate generic types and methods, please see the additional information provided in [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) and [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="cc9c9-110">다음 예제에서는 어셈블리에 대한 <xref:System.Reflection.Assembly> 개체 및 모듈을 가져오는 데 필요한 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-110">The following example shows the syntax necessary to get the <xref:System.Reflection.Assembly> object and module for an assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 <span data-ttu-id="cc9c9-111">다음 예제에서는 로드된 어셈블리에서 **Type** 개체를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-111">The following example demonstrates getting **Type** objects from a loaded assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 <span data-ttu-id="cc9c9-112">**Type**을 가져온 후 해당 형식의 멤버에 대한 정보를 검색할 수 있는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-112">Once you obtain a **Type**, there are many ways you can discover information about the members of that type.</span></span> <span data-ttu-id="cc9c9-113">예를 들어 현재 형식의 각 멤버를 설명하는 <xref:System.Reflection.MemberInfo> 개체의 배열을 가져오는 <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> 메서드를 호출하여 모든 형식의 멤버에 대한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-113">For example, you can find out about all the type's members by calling the <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> method, which obtains an array of <xref:System.Reflection.MemberInfo> objects describing each of the members of the current type.</span></span>  
  
 <span data-ttu-id="cc9c9-114">**Type** 클래스에서 메서드를 사용하여 이름으로 지정하는 하나 이상의 생성자, 메서드, 이벤트, 필드 또는 속성에 대한 정보를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-114">You can also use methods on the **Type** class to retrieve information about one or more constructors, methods, events, fields, or properties that you specify by name.</span></span> <span data-ttu-id="cc9c9-115">예를 들어 <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType>는 현재 클래스의 특정 생성자를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-115">For example, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsulates a specific constructor of the current class.</span></span>  
  
 <span data-ttu-id="cc9c9-116">**Type**이 있는 경우 <xref:System.Type.Module%2A?displayProperty=nameWithType> 속성을 사용하여 해당 형식이 포함된 모듈을 캡슐화하는 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-116">If you have a **Type**, you can use the <xref:System.Type.Module%2A?displayProperty=nameWithType> property to obtain an object that encapsulates the module containing that type.</span></span> <span data-ttu-id="cc9c9-117"><xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> 속성을 사용하여 모듈이 포함된 어셈블리를 캡슐화하는 개체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-117">Use the <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> property to locate an object that encapsulates the assembly containing the module.</span></span> <span data-ttu-id="cc9c9-118"><xref:System.Type.Assembly%2A?displayProperty=nameWithType> 속성을 사용하여 직접 형식을 캡슐화하는 어셈블리를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-118">You can obtain the assembly that encapsulates the type directly by using the <xref:System.Type.Assembly%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="systemtype-and-constructorinfo"></a><span data-ttu-id="cc9c9-119">System.Type 및 ConstructorInfo</span><span class="sxs-lookup"><span data-stu-id="cc9c9-119">System.Type and ConstructorInfo</span></span>  
 <span data-ttu-id="cc9c9-120">다음 예제에서는 클래스(이 경우 <xref:System.String> 클래스)에 대한 생성자를 나열하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-120">The following example shows how to list the constructors for a class, in this case, the <xref:System.String> class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a><span data-ttu-id="cc9c9-121">MemberInfo, MethodInfo, FieldInfo 및 PropertyInfo</span><span class="sxs-lookup"><span data-stu-id="cc9c9-121">MemberInfo, MethodInfo, FieldInfo, and PropertyInfo</span></span>  
 <span data-ttu-id="cc9c9-122"><xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> 또는 <xref:System.Reflection.PropertyInfo> 개체를 사용하여 형식의 메서드, 속성, 이벤트 및 필드에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-122">Obtain information about the type's methods, properties, events, and fields using <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo>, or <xref:System.Reflection.PropertyInfo> objects.</span></span>  
  
 <span data-ttu-id="cc9c9-123">다음 예제에서는 **MemberInfo**를 사용하여 **System.IO.File** 클래스의 멤버 수를 나열하고, <xref:System.Type.IsPublic%2A> 속성을 사용하여 클래스의 표시 유형을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-123">The following example uses **MemberInfo** to list the number of members in the **System.IO.File** class and uses the <xref:System.Type.IsPublic%2A> property to determine the visibility of the class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 <span data-ttu-id="cc9c9-124">다음 예제에서는 지정된 멤버의 형식을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-124">The following example investigates the type of the specified member.</span></span> <span data-ttu-id="cc9c9-125">**MemberInfo** 클래스의 멤버에 대한 리플렉션을 수행하고 해당 형식을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-125">It performs reflection on a member of the **MemberInfo** class, and lists its type.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 <span data-ttu-id="cc9c9-126">다음 예제에서는 모든 Reflection **\*Info** 클래스를 <xref:System.Reflection.BindingFlags>와 함께 사용하여 지정된 클래스의 모든 멤버(생성자, 필드, 속성, 이벤트 및 메서드)를 나열하고 멤버를 정적 및 인스턴스 범주로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-126">The following example uses all the Reflection **\*Info** classes along with <xref:System.Reflection.BindingFlags> to list all the members (constructors, fields, properties, events, and methods) of the specified class, dividing the members into static and instance categories.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cc9c9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc9c9-127">See Also</span></span>  
 <xref:System.Reflection.BindingFlags>  
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>  
 <xref:System.Type.GetType%2A?displayProperty=nameWithType>  
 <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>  
 <xref:System.Type.GetFields%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.MemberInfo>  
 <xref:System.Reflection.ConstructorInfo>  
 <xref:System.Reflection.MethodInfo>  
 <xref:System.Reflection.FieldInfo>  
 <xref:System.Reflection.EventInfo>  
 <xref:System.Reflection.ParameterInfo>  
 [<span data-ttu-id="cc9c9-128">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="cc9c9-128">Reflection and Generic Types</span></span>](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)
