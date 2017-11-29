---
title: "데이터 계약 이름"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data contracts [WCF], naming
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a52deae243e4f28e82eebd99e926ac8aeba4f02d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-contract-names"></a><span data-ttu-id="047b9-102">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="047b9-102">Data Contract Names</span></span>
<span data-ttu-id="047b9-103">때때로 클라이언트와 서비스는 동일한 형식을 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-103">Sometimes a client and a service do not share the same types.</span></span> <span data-ttu-id="047b9-104">그래도 양쪽의 데이터 계약이 동일하면 서로 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-104">They can still pass data to each other as long as the data contracts are equivalent on both sides.</span></span> <span data-ttu-id="047b9-105">[데이터 계약 동등성](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md) 데이터 계약 및 데이터 멤버 이름에 따라 및 따라서 메커니즘은 형식 및 멤버 이름에 매핑할 수 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-105">[Data Contract Equivalence](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md) is based on data contract and data member names, and therefore a mechanism is provided to map types and members to those names.</span></span> <span data-ttu-id="047b9-106">이 항목에서는 이름을 만들 때 데이터 계약의 이름 지정 규칙 및 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 인프라의 기본 동작 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-106">This topic explains the rules for naming data contracts as well as the default behavior of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] infrastructure when creating names.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="047b9-107">기본 규칙</span><span class="sxs-lookup"><span data-stu-id="047b9-107">Basic Rules</span></span>  
 <span data-ttu-id="047b9-108">데이터 계약 이름 지정과 관련된 기본 규칙에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-108">Basic rules regarding naming data contracts include:</span></span>  
  
-   <span data-ttu-id="047b9-109">정규화된 데이터 계약 이름은 네임스페이스와 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-109">A fully-qualified data contract name consists of a namespace and a name.</span></span>  
  
-   <span data-ttu-id="047b9-110">데이터 멤버에는 이름만 있으며, 네임스페이스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-110">Data members have only names, but no namespaces.</span></span>  
  
-   <span data-ttu-id="047b9-111">데이터 계약을 처리할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라는 데이터 계약 및 데이터 멤버의 네임스페이스와 이름 모두에 대해 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-111">When processing data contracts, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure is case-sensitive to both the namespaces and the names of data contracts and data members.</span></span>  
  
## <a name="data-contract-namespaces"></a><span data-ttu-id="047b9-112">데이터 계약 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="047b9-112">Data Contract Namespaces</span></span>  
 <span data-ttu-id="047b9-113">데이터 계약 네임스페이스는 URI(Uniform Resource Identifier)의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-113">A data contract namespace takes the form of a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="047b9-114">절대 URI나 상대 URI일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-114">The URI can be either absolute or relative.</span></span> <span data-ttu-id="047b9-115">기본적으로 특정 형식에 대한 데이터 계약은 해당 형식의 CLR(공용 언어 런타임) 네임스페이스로부터 가져오는 네임스페이스에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-115">By default, data contracts for a particular type are assigned a namespace that comes from the common language runtime (CLR) namespace of that type.</span></span>  
  
 <span data-ttu-id="047b9-116">기본적으로 모든 주어진된 CLR 네임 스페이스 (형식에서 *Clr.Namespace*) "http://schemas.datacontract.org/2004/07/Clr.Namespace" 네임 스페이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-116">By default, any given CLR namespace (in the format *Clr.Namespace*) is mapped to the namespace "http://schemas.datacontract.org/2004/07/Clr.Namespace".</span></span> <span data-ttu-id="047b9-117">이 기본값을 재정의하려면 전체 모듈 또는 어셈블리에 <xref:System.Runtime.Serialization.ContractNamespaceAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-117">To override this default, apply the <xref:System.Runtime.Serialization.ContractNamespaceAttribute> attribute to the entire module or assembly.</span></span> <span data-ttu-id="047b9-118">또는 각 형식에 대해 데이터 계약 네임스페이스를 제어하려면 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>의 <xref:System.Runtime.Serialization.DataContractAttribute> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-118">Alternatively, to control the data contract namespace for each type, set the <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> property of the <xref:System.Runtime.Serialization.DataContractAttribute>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="047b9-119">"http://schemas.microsoft.com/2003/10/Serialization" 네임스페이스가 예약되며, 데이터 계약 네임스페이스로 사용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-119">The "http://schemas.microsoft.com/2003/10/Serialization"namespace is reserved and cannot be used as a data contract namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="047b9-120">`delegate` 선언을 포함하는 데이터 계약 형식에서 기본 네임스페이스를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-120">You cannot override the default namespace in data contract types that contain `delegate` declarations.</span></span>  
  
## <a name="data-contract-names"></a><span data-ttu-id="047b9-121">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="047b9-121">Data Contract Names</span></span>  
 <span data-ttu-id="047b9-122">주어진 형식에 대한 데이터 계약의 기본 이름은 해당 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-122">The default name of a data contract for a given type is the name of that type.</span></span> <span data-ttu-id="047b9-123">기본값을 재정의하려면 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>의 <xref:System.Runtime.Serialization.DataContractAttribute> 속성을 대체 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-123">To override the default, set the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataContractAttribute> to an alternative name.</span></span> <span data-ttu-id="047b9-124">제네릭 형식에 대한 특정 규칙은 이 항목의 뒷부분에 있는 "제네릭 형식에 대한 데이터 계약 이름"에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-124">Special rules for generic types are described in "Data Contract Names for Generic Types" later in this topic.</span></span>  
  
## <a name="data-member-names"></a><span data-ttu-id="047b9-125">데이터 멤버 이름</span><span class="sxs-lookup"><span data-stu-id="047b9-125">Data Member Names</span></span>  
 <span data-ttu-id="047b9-126">주어진 필드 또는 속성에 대한 데이터 멤버의 기본 이름은 해당 필드 또는 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-126">The default name of a data member for a given field or property is the name of that field or property.</span></span> <span data-ttu-id="047b9-127">기본값을 재정의하려면 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 대체 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-127">To override the default, set the <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to an alternative value.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="047b9-128">예제</span><span class="sxs-lookup"><span data-stu-id="047b9-128">Examples</span></span>  
 <span data-ttu-id="047b9-129">다음 예제에서는 데이터 계약 및 데이터 멤버의 기본 이름 지정 동작을 재정의할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-129">The following example shows how you can override the default naming behavior of data contracts and data members.</span></span>  
  
 [!code-csharp[C_DataContractNames#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
 [!code-vb[C_DataContractNames#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]  
  
## <a name="data-contract-names-for-generic-types"></a><span data-ttu-id="047b9-130">제네릭 형식에 대한 데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="047b9-130">Data Contract Names for Generic Types</span></span>  
 <span data-ttu-id="047b9-131">제네릭 형식에 대한 데이터 계약 이름을 결정하는 데 특별한 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-131">Special rules exist for determining data contract names for generic types.</span></span> <span data-ttu-id="047b9-132">이러한 규칙은 동일한 제네릭 형식의 폐쇄형 두 개의 제네릭 형식 간에 데이터 계약 이름이 충돌하는 것을 막도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-132">These rules help avoid data contract name collisions between two closed generics of the same generic type.</span></span>  
  
 <span data-ttu-id="047b9-133">기본적으로 데이터 계약 이름은 다음 "의" 문자열 형식의 이름인 제네릭 형식에 대 한 제네릭 매개 변수 뒤의 데이터 계약 이름 뒤에 *해시* 데이터 계약 네임 스페이스를 사용 하 여 계산 제네릭 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-133">By default, the data contract name for a generic type is the name of the type, followed by the string "Of", followed by the data contract names of the generic parameters, followed by a *hash* computed using the data contract namespaces of the generic parameters.</span></span> <span data-ttu-id="047b9-134">해시는 데이터 조각을 고유하게 식별하는 "지문"의 역할을 하는 수학 함수의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-134">A hash is the result of a mathematical function that acts as a "fingerprint" that uniquely identifies a piece of data.</span></span> <span data-ttu-id="047b9-135">모든 제네릭 매개 변수가 기본 형식인 경우 해시는 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-135">When all of the generic parameters are primitive types, the hash is omitted.</span></span>  
  
 <span data-ttu-id="047b9-136">예를 들어 다음 예제의 형식을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="047b9-136">For example, see the types in the following example.</span></span>  
  
 [!code-csharp[C_DataContractNames#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
 [!code-vb[C_DataContractNames#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]  
  
 <span data-ttu-id="047b9-137">이 예제에서 `Drawing<Square,RegularRedBrush>` 형식의 데이터 계약 이름은 "DrawingOfSquareRedBrush5HWGAU6h"이며, 여기서 "5HWGAU6h"는 "urn:shapes" 및 "urn:default" 네임스페이스의 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-137">In this example, the type `Drawing<Square,RegularRedBrush>` has the data contract name "DrawingOfSquareRedBrush5HWGAU6h", where "5HWGAU6h" is a hash of the "urn:shapes" and "urn:default" namespaces.</span></span> <span data-ttu-id="047b9-138">`Drawing<Square,SpecialRedBrush>` 형식의 데이터 계약 이름은 "DrawingOfSquareRedBrushjpB5LgQ_S"이며, 여기서 "jpB5LgQ_S"는 "urn:shapes" 및 "urn:special" 네임스페이스의 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-138">The type `Drawing<Square,SpecialRedBrush>` has the data contract name "DrawingOfSquareRedBrushjpB5LgQ_S", where "jpB5LgQ_S" is a hash of the "urn:shapes" and the "urn:special" namespaces.</span></span> <span data-ttu-id="047b9-139">해시를 사용하지 않으면 두 이름이 동일하므로 이름이 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-139">Note that if the hash is not used, the two names are identical, and thus a name collision occurs.</span></span>  
  
## <a name="customizing-data-contract-names-for-generic-types"></a><span data-ttu-id="047b9-140">제네릭 형식에 대해 데이터 계약 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="047b9-140">Customizing Data Contract Names for Generic Types</span></span>  
 <span data-ttu-id="047b9-141">위에서 설명한 것과 같이 제네릭 형식에 대해 생성된 데이터 계약 이름이 허용되지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-141">Sometimes, the data contract names generated for generic types, as described previously, are unacceptable.</span></span> <span data-ttu-id="047b9-142">예를 들어 이름 충돌이 발생하지 않도록 하려면 해시를 제거해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-142">For example, you may know in advance that you will not run into name collisions and may want to remove the hash.</span></span> <span data-ttu-id="047b9-143">이 경우에는 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 특성의 `DataContractAttribute` 속성을 사용하여 이름을 생성하는 여러 가지 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-143">In this case, you can use the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property of the `DataContractAttribute` attribute to specify a different way to generate names.</span></span> <span data-ttu-id="047b9-144">제네릭 매개 변수의 데이터 계약 이름을 참조하기 위해 `Name` 속성 내에서 중괄호 안에 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-144">You can use numbers in curly braces inside of the `Name` property to refer to data contract names of the generic parameters.</span></span> <span data-ttu-id="047b9-145">예를 들어 0은 첫 번째 매개 변수를 참조하고, 1은 두 번째 매개 변수를 참조합니다. 해시를 참조하기 위해 중괄호 안에 숫자(#) 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-145">(0 refers to the first parameter, 1 refers to the second, and so on.) You can use a number (#) sign inside curly braces to refer to the hash.</span></span> <span data-ttu-id="047b9-146">이러한 각각의 참조를 여러 번 사용하거나 전혀 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-146">You can use each of these references multiple times or not at all.</span></span>  
  
 <span data-ttu-id="047b9-147">예를 들어 이전 제네릭 `Drawing` 형식은 다음 예제와 같이 선언되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-147">For example, the preceding generic `Drawing` type could have been declared as shown in the following example.</span></span>  
  
 [!code-csharp[c_DataContractNames#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
 [!code-vb[c_DataContractNames#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]  
  
 <span data-ttu-id="047b9-148">이 경우에는 `Drawing<Square,RegularRedBrush>` 형식의 데이터 계약 이름이 "Drawing_using_RedBrush_brush_and_Square_shape"입니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-148">In this case, the type `Drawing<Square,RegularRedBrush>` has the data contract name "Drawing_using_RedBrush_brush_and_Square_shape".</span></span> <span data-ttu-id="047b9-149"><xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 속성에 "{#}"이 있으면 해시가 이름의 일부가 아니므로 형식의 이름을 지정할 때 충돌이 발생하기 쉽습니다. 예를 들어 `Drawing<Square,SpecialRedBrush>` 형식의 데이터 계약 이름이 동일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="047b9-149">Note that because there is a "{#}" in the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property, the hash is not a part of the name, and thus the type is susceptible to naming collisions; for example, the type `Drawing<Square,SpecialRedBrush>` would have exactly the same data contract name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047b9-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="047b9-150">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Runtime.Serialization.ContractNamespaceAttribute>  
 [<span data-ttu-id="047b9-151">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="047b9-151">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="047b9-152">데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="047b9-152">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="047b9-153">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="047b9-153">Data Contract Names</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-names.md)  
 [<span data-ttu-id="047b9-154">데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="047b9-154">Data Contract Versioning</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)
