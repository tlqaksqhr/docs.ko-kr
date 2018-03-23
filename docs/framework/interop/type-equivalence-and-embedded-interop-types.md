---
title: 동일 형식 및 포함 된 interop 형식
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- type equivalence
- embedded interop types
- primary interop assemblies,not necessary in CLR version 4
- NoPIA
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03b906c71b1b3e8f4817697edb520f8cfef1e009
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="type-equivalence-and-embedded-interop-types"></a><span data-ttu-id="9334a-102">동일 형식 및 포함 된 interop 형식</span><span class="sxs-lookup"><span data-stu-id="9334a-102">Type equivalence and embedded interop types</span></span>

<span data-ttu-id="9334a-103">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터 공용 언어 런타임은 관리되는 어셈블리가 interop 어셈블리에서 COM 형식에 대한 형식 정보를 가져오도록 요구하는 대신 COM 형식에 대한 형식 정보를 관리되는 어셈블리에 직접 포함하는 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-103">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the common language runtime supports embedding type information for COM types directly into managed assemblies, instead of requiring the managed assemblies to obtain type information for COM types from interop assemblies.</span></span> <span data-ttu-id="9334a-104">포함된 형식 정보에는 관리되는 어셈블리에서 실제로 사용되는 형식 및 멤버만 포함되므로 두 개의 관리되는 어셈블리에서 동일한 COM 형식이 전혀 다르게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-104">Because the embedded type information includes only the types and members that are actually used by a managed assembly, two managed assemblies might have very different views of the same COM type.</span></span> <span data-ttu-id="9334a-105">관리되는 어셈블리마다 COM 형식의 해당 보기를 나타내는 다른 <xref:System.Type> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-105">Each managed assembly has a different <xref:System.Type> object to represent its view of the COM type.</span></span> <span data-ttu-id="9334a-106">공용 언어 런타임은 인터페이스, 구조체, 열거형 및 대리자에 대한 이러한 다양한 보기 간에 형식 동등을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-106">The common language runtime supports type equivalence between these different views for interfaces, structures, enumerations, and delegates.</span></span>

<span data-ttu-id="9334a-107">형식 동등은 관리되는 어셈블리 간에 전달되는 COM 개체를 수신 어셈블리에서 적절한 관리되는 형식으로 캐스팅할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-107">Type equivalence means that a COM object that is passed from one managed assembly to another can be cast to the appropriate managed type in the receiving assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="9334a-108">형식 동등 및 포함된 interop 형식은 응용 프로그램과 함께 interop 어셈블리를 배포할 필요가 없기 때문에 COM 구성 요소를 사용하는 응용 프로그램 및 추가 기능의 배포를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-108">Type equivalence and embedded interop types simplify the deployment of applications and add-ins that use COM components, because it is not necessary to deploy interop assemblies with the applications.</span></span> <span data-ttu-id="9334a-109">공유 COM 구성 요소의 개발자는 이전 버전의 .NET Framework에서 해당 구성 요소를 사용하려는 경우 여전히 PIA(주 interop 어셈블리)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-109">Developers of shared COM components still have to create primary interop assemblies (PIAs) if they want their components to be used by earlier versions of the .NET Framework.</span></span>

## <a name="type-equivalence"></a><span data-ttu-id="9334a-110">형식 동등성</span><span class="sxs-lookup"><span data-stu-id="9334a-110">Type equivalence</span></span>

 <span data-ttu-id="9334a-111">COM 형식 동등은 인터페이스, 구조체, 열거형 및 대리자에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-111">Equivalence of COM types is supported for interfaces, structures, enumerations, and delegates.</span></span> <span data-ttu-id="9334a-112">COM 형식은 다음 조건이 모두 true인 경우 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-112">COM types qualify as equivalent if all of the following are true:</span></span>

- <span data-ttu-id="9334a-113">형식이 둘 다 인터페이스, 둘 다 구조체, 둘 다 열거형 또는 둘 다 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-113">The types are both interfaces, or both structures, or both enumerations, or both delegates.</span></span>

- <span data-ttu-id="9334a-114">다음 섹션에 설명된 대로 형식의 ID가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-114">The types have the same identity, as described in the next section.</span></span>

- <span data-ttu-id="9334a-115">에 설명 된 대로 두 유형 모두 같은 형식는 [형식 동등성에 대 한 COM 표시 형식을](#marking-com-types-for-type-equivalence) 섹션.</span><span class="sxs-lookup"><span data-stu-id="9334a-115">Both types are eligible for type equivalence, as described in the [Marking COM types for type equivalence](#marking-com-types-for-type-equivalence) section.</span></span>

### <a name="type-identity"></a><span data-ttu-id="9334a-116">유형 id</span><span class="sxs-lookup"><span data-stu-id="9334a-116">Type identity</span></span>

<span data-ttu-id="9334a-117">두 형식은 해당 범위 및 ID가 일치할 때, 즉 각각 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성이 있고 두 특성에 일치하는 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 및 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> 속성이 있는 경우 ID가 같다고 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-117">Two types are determined to have the same identity when their scopes and identities match, in other words, if they each have the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute, and the two attributes have matching <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> and <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> properties.</span></span> <span data-ttu-id="9334a-118"><xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 비교는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-118">The comparison for <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> is case-insensitive.</span></span>

<span data-ttu-id="9334a-119">형식에 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성이 없는 경우 또는 범위 및 식별자를 지정하지 않는 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성이 있는 경우에도 다음과 같이 해당 형식의 동등을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-119">If a type does not have the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute, or if it has a <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute that does not specify scope and identifier, the type can still be considered for equivalence as follows:</span></span>

- <span data-ttu-id="9334a-120">인터페이스의 경우 <xref:System.Runtime.InteropServices.GuidAttribute> 값이 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> 속성 대신 사용되고, <xref:System.Type.FullName%2A?displayProperty=nameWithType> 속성(즉, 네임스페이스를 포함하는 형식 이름)이 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> 속성 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-120">For interfaces, the value of the <xref:System.Runtime.InteropServices.GuidAttribute> is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> property, and the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property (that is, the type name, including the namespace) is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="9334a-121">구조체, 열거형 및 대리자의 경우 포함하는 어셈블리의 <xref:System.Runtime.InteropServices.GuidAttribute>가 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> 속성 대신 사용되고, <xref:System.Type.FullName%2A?displayProperty=nameWithType> 속성이 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> 속성 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-121">For structures, enumerations, and delegates, the <xref:System.Runtime.InteropServices.GuidAttribute> of the containing assembly is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> property, and the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> property.</span></span>

### <a name="marking-com-types-for-type-equivalence"></a><span data-ttu-id="9334a-122">형식 동등성에 대 한 COM 형식을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-122">Marking COM types for type equivalence</span></span>

 <span data-ttu-id="9334a-123">다음 두 가지 방법으로 형식을 형식 동등에 적합한 것으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-123">You can mark a type as eligible for type equivalence in two ways:</span></span>

- <span data-ttu-id="9334a-124">형식에 <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-124">Apply the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute to the type.</span></span>

- <span data-ttu-id="9334a-125">형식을 COM 가져오기 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-125">Make the type a COM import type.</span></span> <span data-ttu-id="9334a-126"><xref:System.Runtime.InteropServices.ComImportAttribute> 특성이 있는 인터페이스는 COM 가져오기 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-126">An interface is a COM import type if it has the <xref:System.Runtime.InteropServices.ComImportAttribute> attribute.</span></span> <span data-ttu-id="9334a-127">인터페이스, 구조체, 열거형 또는 대리자가 정의되어 있는 어셈블리에 <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> 특성이 있는 경우 해당 항목은 COM 가져오기 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9334a-127">An interface, structure, enumeration, or delegate is a COM import type if the assembly in which it is defined has the <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="9334a-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="9334a-128">See also</span></span>

<xref:System.Type.IsEquivalentTo%2A>  
<span data-ttu-id="9334a-129">[관리 코드에서 COM 형식을 사용 하 여](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9334a-129">[Using COM Types in Managed Code](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span></span>  
[<span data-ttu-id="9334a-130">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="9334a-130">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)  
