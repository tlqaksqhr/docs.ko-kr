---
title: '방법: 리플렉션 전용 컨텍스트에 어셈블리 로드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7aa7f8a158a851baf76455da685059f02c69cb6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398728"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="0d77e-102">방법: 리플렉션 전용 컨텍스트에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="0d77e-102">How to: Load Assemblies into the Reflection-Only Context</span></span>
<span data-ttu-id="0d77e-103">리플렉션 전용 로드 컨텍스트를 사용하면 다른 플랫폼이나 다른 버전의 .NET Framework에 대해 컴파일된 어셈블리를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-103">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="0d77e-104">이 컨텍스트에 로드된 코드는 검사할 수만 있고 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-104">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="0d77e-105">즉, 생성자를 실행할 수 없기 때문에 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-105">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="0d77e-106">코드를 실행할 수 없기 때문에 종속성이 자동으로 로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-106">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="0d77e-107">종속성을 검사하려면 직접 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-107">If you need to examine them, you must load them yourself.</span></span>  
  
### <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="0d77e-108">리플렉션 전용 로드 컨텍스트에 어셈블리를 로드하려면</span><span class="sxs-lookup"><span data-stu-id="0d77e-108">To load an assembly into the reflection-only load context</span></span>  
  
1.  <span data-ttu-id="0d77e-109">표시 이름이 지정된 경우 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> 메서드 오버로드를 사용하여 어셈블리를 로드하고, 해당 경로가 지정된 경우 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 메서드를 사용하여 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-109">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="0d77e-110">어셈블리가 이진 이미지인 경우 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> 메서드 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-110">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d77e-111">리플렉션 전용 컨텍스트를 사용하여 실행 컨텍스트에 있는 버전 이외의 .NET Framework 버전에서 mscorlib.dll 버전을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-111">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>  
  
2.  <span data-ttu-id="0d77e-112">어셈블리에 종속성이 있는 경우 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 메서드는 종속성을 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-112">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="0d77e-113">종속성을 검사하려면 직접 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-113">If you need to examine them, you must load them yourself.</span></span>  
  
3.  <span data-ttu-id="0d77e-114">어셈블리의 <xref:System.Reflection.Assembly.ReflectionOnly%2A> 속성을 사용하여 어셈블리를 리플렉션 전용 컨텍스트에 로드할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-114">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>  
  
4.  <span data-ttu-id="0d77e-115">어셈블리 또는 어셈블리의 형식에 특성이 적용된 경우 <xref:System.Reflection.CustomAttributeData> 클래스를 통해 이러한 특성을 검사하여 리플렉션 전용 컨텍스트에서 코드를 실행하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-115">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="0d77e-116"><xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> 메서드의 적절한 오버로드를 사용하여 어셈블리, 멤버, 모듈 또는 매개 변수에 적용된 특성을 나타내는 <xref:System.Reflection.CustomAttributeData> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-116">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d77e-117">어셈블리에 또는 해당 내용에 적용되는 특성은 어셈블리에서 정의되거나, 리플렉션 전용 컨텍스트에 로드된 다른 어셈블리에서 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-117">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="0d77e-118">특성이 정의되어 있는 위치를 미리 확인할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-118">There is no way to tell in advance where the attributes are defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d77e-119">예</span><span class="sxs-lookup"><span data-stu-id="0d77e-119">Example</span></span>  
 <span data-ttu-id="0d77e-120">다음 코드 예제에서는 리플렉션 전용 컨텍스트에 로드된 어셈블리에 적용된 특성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-120">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>  
  
 <span data-ttu-id="0d77e-121">이 코드 예제는 생성자 두 개와 속성 하나를 사용하여 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-121">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="0d77e-122">어셈블리, 어셈블리에 선언된 형식, 형식의 메서드, 메서드의 매개 변수에 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-122">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="0d77e-123">실행할 경우 어셈블리는 리플렉션 전용 컨텍스트에 자동으로 로드되고 어셈블리와 어셈블리에 포함된 형식 및 멤버에 적용된 사용자 지정 특성에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-123">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d77e-124">코드 예제를 단순화하기 위해 어셈블리가 자동으로 로드 및 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-124">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="0d77e-125">일반적으로 실행 컨텍스트와 리플렉션 전용 컨텍스트에 동일한 어셈블리가 로드되는 경우는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d77e-125">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>  
  
 [!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
 [!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
 [!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0d77e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d77e-126">See Also</span></span>  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>  
 <xref:System.Reflection.Assembly.ReflectionOnly%2A>  
 <xref:System.Reflection.CustomAttributeData>
