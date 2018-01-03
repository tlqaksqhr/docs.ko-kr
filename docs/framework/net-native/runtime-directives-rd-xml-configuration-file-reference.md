---
title: "런타임 지시문(rd.xml) 구성 파일 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f452a32b209c30175f95aec7a8a90e0783c10086
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="86001-102">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="86001-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>
<span data-ttu-id="86001-103">런타임 지시문(.rd.xml) 파일은 지정된 프로그램 요소를 리플렉션에 사용할 수 있는지 여부를 지정하는 XML 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="86001-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="86001-104">런타임 지시문 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-104">Here’s an example of a runtime directives file:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
<Application>  
  <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />  
  <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />  
  <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />  
  <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />  
  
  <Namespace Name="System.Collections.ObjectModel" >  
    <TypeInstantiation Name="ObservableCollection"   
          Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />  
    <TypeInstantiation Name="ReadOnlyObservableCollection"   
          Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />  
  </Namespace>  
</Application>  
</Directives>  
```  
  
## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="86001-105">지시문 런타임 파일의 구조</span><span class="sxs-lookup"><span data-stu-id="86001-105">The structure of a runtime directives file</span></span>  
 <span data-ttu-id="86001-106">런타임 지시문 파일은 `http://schemas.microsoft.com/netfx/2013/01/metadata` 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>  
  
 <span data-ttu-id="86001-107">루트 요소는 [Directives](../../../docs/framework/net-native/directives-element-net-native.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="86001-107">The root element is the [Directives](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span> <span data-ttu-id="86001-108">이 요소는 다음 구조에 나와 있는 것처럼 [Library](../../../docs/framework/net-native/library-element-net-native.md) 요소와 [Application](../../../docs/framework/net-native/application-element-net-native.md) 요소를 포함하지 않을 수도 있고 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-108">It can contain zero or more [Library](../../../docs/framework/net-native/library-element-net-native.md) elements, and zero or one [Application](../../../docs/framework/net-native/application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="86001-109">[Application](../../../docs/framework/net-native/application-element-net-native.md) 요소의 특성은 응용 프로그램 전체 런타임 리플렉션 정책을 정의할 수도 있고 자식 요소의 컨테이너로 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-109">The attributes of the [Application](../../../docs/framework/net-native/application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="86001-110">반면 [Library](../../../docs/framework/net-native/library-element-net-native.md) 요소는 단순한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="86001-110">The [Library](../../../docs/framework/net-native/library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="86001-111">[Application](../../../docs/framework/net-native/application-element-net-native.md) 및 [Library](../../../docs/framework/net-native/library-element-net-native.md) 요소의 자식은 리플렉션에 사용할 수 있는 형식, 메서드, 필드, 속성 및 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-111">The children of the [Application](../../../docs/framework/net-native/application-element-net-native.md) and [Library](../../../docs/framework/net-native/library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>  
  
 <span data-ttu-id="86001-112">참조 정보를 확인하려면 다음 구조체의 요소를 선택하거나 [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86001-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](../../../docs/framework/net-native/runtime-directive-elements.md).</span></span> <span data-ttu-id="86001-113">다음 계층 구조에서 줄임표는 재귀 구조를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="86001-114">괄호 안의 정보는 해당 요소가 필수 항목인지 선택적 항목인지와 요소가 사용되는 경우 허용되는 인스턴스 수(하나 또는 여러 개)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86001-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>  
  
 <span data-ttu-id="86001-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="86001-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1]</span></span>  
 <span data-ttu-id="86001-116">[Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="86001-116">[Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1]</span></span>  
 <span data-ttu-id="86001-117">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-117">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-118">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-118">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-119">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-119">.</span></span> <span data-ttu-id="86001-120">.</span><span class="sxs-lookup"><span data-stu-id="86001-120">.</span></span> <span data-ttu-id="86001-121">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-121">.</span></span>  
 <span data-ttu-id="86001-122">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-122">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-123">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-123">.</span></span> <span data-ttu-id="86001-124">.</span><span class="sxs-lookup"><span data-stu-id="86001-124">.</span></span> <span data-ttu-id="86001-125">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-125">.</span></span>  
 <span data-ttu-id="86001-126">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-126">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-127">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-127">.</span></span> <span data-ttu-id="86001-128">.</span><span class="sxs-lookup"><span data-stu-id="86001-128">.</span></span> <span data-ttu-id="86001-129">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-129">.</span></span>  
 <span data-ttu-id="86001-130">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-130">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-131">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-131">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-132">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-132">.</span></span> <span data-ttu-id="86001-133">.</span><span class="sxs-lookup"><span data-stu-id="86001-133">.</span></span> <span data-ttu-id="86001-134">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-134">.</span></span>  
 <span data-ttu-id="86001-135">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-135">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-136">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-136">.</span></span> <span data-ttu-id="86001-137">.</span><span class="sxs-lookup"><span data-stu-id="86001-137">.</span></span> <span data-ttu-id="86001-138">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-138">.</span></span>  
 <span data-ttu-id="86001-139">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-139">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-140">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-140">.</span></span> <span data-ttu-id="86001-141">.</span><span class="sxs-lookup"><span data-stu-id="86001-141">.</span></span> <span data-ttu-id="86001-142">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-142">.</span></span>  
 <span data-ttu-id="86001-143">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-143">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-144">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md)(포함 형식의 하위 클래스) [O:1]</span><span class="sxs-lookup"><span data-stu-id="86001-144">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>  
 <span data-ttu-id="86001-145">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-145">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-146">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-146">.</span></span> <span data-ttu-id="86001-147">.</span><span class="sxs-lookup"><span data-stu-id="86001-147">.</span></span> <span data-ttu-id="86001-148">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-148">.</span></span>  
 <span data-ttu-id="86001-149">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-149">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-150">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-150">.</span></span> <span data-ttu-id="86001-151">.</span><span class="sxs-lookup"><span data-stu-id="86001-151">.</span></span> <span data-ttu-id="86001-152">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-152">.</span></span>  
 <span data-ttu-id="86001-153">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)(포함 형식이 특성임) [O:1]</span><span class="sxs-lookup"><span data-stu-id="86001-153">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>  
 <span data-ttu-id="86001-154">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-154">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-155">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-155">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-156">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-156">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-157">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-157">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-158">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-158">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-159">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(생성된 제네릭 메서드) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-159">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="86001-160">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-160">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-161">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-161">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-162">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-162">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-163">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-163">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-164">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-164">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-165">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-165">.</span></span> <span data-ttu-id="86001-166">.</span><span class="sxs-lookup"><span data-stu-id="86001-166">.</span></span> <span data-ttu-id="86001-167">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-167">.</span></span>  
 <span data-ttu-id="86001-168">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-168">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-169">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-169">.</span></span> <span data-ttu-id="86001-170">.</span><span class="sxs-lookup"><span data-stu-id="86001-170">.</span></span> <span data-ttu-id="86001-171">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-171">.</span></span>  
 <span data-ttu-id="86001-172">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-172">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-173">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-173">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-174">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-174">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-175">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-175">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-176">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(생성된 제네릭 메서드) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-176">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="86001-177">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-177">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-178">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-178">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-179">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-179">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-180">[Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-180">[Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-181">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-181">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-182">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-182">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-183">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-183">.</span></span> <span data-ttu-id="86001-184">.</span><span class="sxs-lookup"><span data-stu-id="86001-184">.</span></span> <span data-ttu-id="86001-185">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-185">.</span></span>  
 <span data-ttu-id="86001-186">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-186">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-187">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-187">.</span></span> <span data-ttu-id="86001-188">.</span><span class="sxs-lookup"><span data-stu-id="86001-188">.</span></span> <span data-ttu-id="86001-189">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-189">.</span></span>  
 <span data-ttu-id="86001-190">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-190">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-191">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-191">.</span></span> <span data-ttu-id="86001-192">.</span><span class="sxs-lookup"><span data-stu-id="86001-192">.</span></span> <span data-ttu-id="86001-193">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-193">.</span></span>  
 <span data-ttu-id="86001-194">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-194">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-195">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-195">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-196">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-196">.</span></span> <span data-ttu-id="86001-197">.</span><span class="sxs-lookup"><span data-stu-id="86001-197">.</span></span> <span data-ttu-id="86001-198">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-198">.</span></span>  
 <span data-ttu-id="86001-199">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-199">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-200">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-200">.</span></span> <span data-ttu-id="86001-201">.</span><span class="sxs-lookup"><span data-stu-id="86001-201">.</span></span> <span data-ttu-id="86001-202">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-202">.</span></span>  
 <span data-ttu-id="86001-203">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-203">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-204">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-204">.</span></span> <span data-ttu-id="86001-205">.</span><span class="sxs-lookup"><span data-stu-id="86001-205">.</span></span> <span data-ttu-id="86001-206">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-206">.</span></span>  
 <span data-ttu-id="86001-207">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-207">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-208">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md)(포함 형식의 하위 클래스) [O:1]</span><span class="sxs-lookup"><span data-stu-id="86001-208">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>  
 <span data-ttu-id="86001-209">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-209">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-210">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-210">.</span></span> <span data-ttu-id="86001-211">.</span><span class="sxs-lookup"><span data-stu-id="86001-211">.</span></span> <span data-ttu-id="86001-212">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-212">.</span></span>  
 <span data-ttu-id="86001-213">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-213">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-214">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-214">.</span></span> <span data-ttu-id="86001-215">.</span><span class="sxs-lookup"><span data-stu-id="86001-215">.</span></span> <span data-ttu-id="86001-216">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-216">.</span></span>  
 <span data-ttu-id="86001-217">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)(포함 형식이 특성임) [O:1]</span><span class="sxs-lookup"><span data-stu-id="86001-217">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>  
 <span data-ttu-id="86001-218">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-218">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-219">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-219">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-220">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(생성된 제네릭 메서드) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-220">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="86001-221">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-221">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-222">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-222">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-223">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-223">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-224">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-224">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-225">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-225">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-226">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-226">.</span></span> <span data-ttu-id="86001-227">.</span><span class="sxs-lookup"><span data-stu-id="86001-227">.</span></span> <span data-ttu-id="86001-228">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-228">.</span></span>  
 <span data-ttu-id="86001-229">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)(생성된 제네릭 형식) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-229">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="86001-230">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-230">.</span></span> <span data-ttu-id="86001-231">.</span><span class="sxs-lookup"><span data-stu-id="86001-231">.</span></span> <span data-ttu-id="86001-232">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-232">.</span></span>  
 <span data-ttu-id="86001-233">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-233">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-234">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)(생성된 제네릭 메서드) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-234">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="86001-235">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-235">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-236">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-236">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="86001-237">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="86001-237">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
  
 <span data-ttu-id="86001-238">[Application](../../../docs/framework/net-native/application-element-net-native.md) 요소는 특성을 포함할 수 없거나 [런타임 지시문 및 정책 섹션](#Directives)에서 설명하는 정책 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-238">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>  
  
 <span data-ttu-id="86001-239">[Library](../../../docs/framework/net-native/library-element-net-native.md) 요소는 파일 이름 확장명을 포함하지 않는 라이브러리나 어셈블리의 이름을 지정하는 단일 특성(`Name`)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-239">A [Library](../../../docs/framework/net-native/library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="86001-240">예를 들어 다음 [Library](../../../docs/framework/net-native/library-element-net-native.md) 요소는 Extensions.dll 어셈블리에 적용되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="86001-240">For example, the following [Library](../../../docs/framework/net-native/library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <!-- Child elements go here -->    
  </Application>  
  <Library Name="Extensions">  
     <!-- Child elements go here -->    
  </Library>  
</Directives>  
```  
  
<a name="Directives"></a>   
## <a name="runtime-directives-and-policy"></a><span data-ttu-id="86001-241">런타임 지시문 및 정책</span><span class="sxs-lookup"><span data-stu-id="86001-241">Runtime directives and policy</span></span>  
 <span data-ttu-id="86001-242">[Application](../../../docs/framework/net-native/application-element-net-native.md) 요소 자체와 [Library](../../../docs/framework/net-native/library-element-net-native.md) 및 [Application](../../../docs/framework/net-native/application-element-net-native.md) 요소의 자식 요소는 정책을 표현합니다. 즉, 앱이 프로그램 요소에 리플렉션을 적용할 수 있는 방식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-242">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element itself and the child elements of the [Library](../../../docs/framework/net-native/library-element-net-native.md) and [Application](../../../docs/framework/net-native/application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="86001-243">정책 형식은 요소의 특성에 의해 정의됩니다(예: `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="86001-243">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="86001-244">정책 값은 특성의 값으로 정의됩니다(예: `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="86001-244">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>  
  
 <span data-ttu-id="86001-245">요소의 특성으로 지정된 정책은 해당 정책에 대해 값을 지정하지 않는 모든 자식 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-245">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="86001-246">예를 들어 정책이 [Type](../../../docs/framework/net-native/type-element-net-native.md) 요소로 지정된 경우 정책이 명시적으로 지정되지 않은 모든 포함된 형식 및 멤버에 해당 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-246">For example, if a policy is specified by a [Type](../../../docs/framework/net-native/type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>  
  
 <span data-ttu-id="86001-247">[Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) 및 [Type](../../../docs/framework/net-native/type-element-net-native.md) 요소로 표현할 수 있는 정책은 [Method](../../../docs/framework/net-native/method-element-net-native.md), [Property](../../../docs/framework/net-native/property-element-net-native.md), [Field](../../../docs/framework/net-native/field-element-net-native.md) 및 [Event](../../../docs/framework/net-native/event-element-net-native.md) 요소로 개별 멤버에 대해 표현할 수 있는 정책과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="86001-247">The policy that can be expressed by the [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](../../../docs/framework/net-native/method-element-net-native.md), [Property](../../../docs/framework/net-native/property-element-net-native.md), [Field](../../../docs/framework/net-native/field-element-net-native.md), and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements).</span></span>  
  
### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="86001-248">어셈블리, 네임스페이스 및 형식에 대한 정책 지정</span><span class="sxs-lookup"><span data-stu-id="86001-248">Specifying policy for assemblies, namespaces, and types</span></span>  
 <span data-ttu-id="86001-249">[Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) 및 [Type](../../../docs/framework/net-native/type-element-net-native.md) 요소는 다음 정책 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-249">The [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="86001-250">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="86001-250">`Activate`.</span></span> <span data-ttu-id="86001-251">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-251">Controls runtime access to constructors, to enable activation of instances.</span></span>  
  
-   <span data-ttu-id="86001-252">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="86001-252">`Browse`.</span></span> <span data-ttu-id="86001-253">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-253">Controls querying for information about program elements but does not enable any runtime access.</span></span>  
  
-   <span data-ttu-id="86001-254">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="86001-254">`Dynamic`.</span></span> <span data-ttu-id="86001-255">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-255">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>  
  
-   <span data-ttu-id="86001-256">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="86001-256">`Serialize`.</span></span> <span data-ttu-id="86001-257">Newtonsoft JSON serializer 등의 타사 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-257">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>  
  
-   <span data-ttu-id="86001-258">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="86001-258">`DataContractSerializer`.</span></span> <span data-ttu-id="86001-259"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-259">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="86001-260">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="86001-260">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="86001-261"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-261">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="86001-262">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="86001-262">`XmlSerializer`.</span></span> <span data-ttu-id="86001-263"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-263">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="86001-264">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="86001-264">`MarshalObject`.</span></span> <span data-ttu-id="86001-265">WinRT 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-265">Controls policy for marshaling reference types to WinRT and COM.</span></span>  
  
-   <span data-ttu-id="86001-266">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="86001-266">`MarshalDelegate`.</span></span> <span data-ttu-id="86001-267">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-267">Controls policy for marshaling delegate types as function pointers to native code.</span></span>  
  
-   <span data-ttu-id="86001-268">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="86001-268">`MarshalStructure` .</span></span> <span data-ttu-id="86001-269">구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-269">Controls policy for marshaling structures to native code.</span></span>  
  
 <span data-ttu-id="86001-270">이러한 정책 형식과 연관된 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-270">The settings associated with these policy types are:</span></span>  
  
-   <span data-ttu-id="86001-271">`All`.</span><span class="sxs-lookup"><span data-stu-id="86001-271">`All`.</span></span> <span data-ttu-id="86001-272">도구 체인에서 제거하지 않는 모든 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-272">Enable the policy for all types and members that the tool chain does not remove.</span></span>  
  
-   <span data-ttu-id="86001-273">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="86001-273">`Auto`.</span></span> <span data-ttu-id="86001-274">기본 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-274">Use the default behavior.</span></span> <span data-ttu-id="86001-275">정책을 지정하지 않는 것은 부모 요소에 의해 정책이 재정의되는 등의 경우를 제외하면 해당 정책을 `Auto`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-275">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>  
  
-   <span data-ttu-id="86001-276">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="86001-276">`Excluded`.</span></span> <span data-ttu-id="86001-277">프로그램 요소에 대한 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-277">Disable the policy for the program element.</span></span>  
  
-   <span data-ttu-id="86001-278">`Public`.</span><span class="sxs-lookup"><span data-stu-id="86001-278">`Public`.</span></span> <span data-ttu-id="86001-279">도구 체인이 멤버를 불필요한 것으로 결정하여 제거하는 경우가 아니면 public 형식 또는 멤버에 대해서는 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-279">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="86001-280">멤버가 제거되는 경우에는 `Required Public`을 사용하여 멤버를 유지하고 리플렉션 기능이 포함되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-280">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>  
  
-   <span data-ttu-id="86001-281">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="86001-281">`PublicAndInternal`.</span></span> <span data-ttu-id="86001-282">도구 체인에서 제거하지 않는 public 및 내부 형식이나 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-282">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>  
  
-   <span data-ttu-id="86001-283">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="86001-283">`Required Public`.</span></span> <span data-ttu-id="86001-284">사용 여부에 관계없이 도구 체인이 public 형식과 멤버를 유지해야 하도록 지정하고 해당 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-284">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>  
  
-   <span data-ttu-id="86001-285">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="86001-285">`Required PublicAndInternal`.</span></span> <span data-ttu-id="86001-286">사용 여부에 관계없이 도구 체인이 public 및 내부 형식과 멤버를 모두 유지해야 하도록 지정하고 해당 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-286">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>  
  
-   <span data-ttu-id="86001-287">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="86001-287">`Required All`.</span></span> <span data-ttu-id="86001-288">사용 여부에 관계없이 도구 체인이 모든 형식과 멤버를 유지해야 하도록 지정하고 해당 형식과 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-288">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>  
  
 <span data-ttu-id="86001-289">예를 들어 다음 런타임 지시문 파일은 DataClasses.dll 어셈블리의 모든 형식과 멤버에 대한 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-289">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="86001-290">이 정책은 모든 public 속성의 serialization에 대해 리플렉션을 사용하도록 설정하고, 모든 형식 및 형식 멤버를 검색할 수 있도록 설정하고, `Dynamic` 특성을 통해 모든 형식을 활성화할 수 있도록 설정하고, 모든 public 형식 및 멤버에 대해 리플렉션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-290">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public"   
                Browse="All" Activate="PublicAndInternal"   
                Dynamic="Public"  />  
   </Application>  
   <Library Name="UtilityLibrary">  
     <!-- Child elements go here -->    
   </Library>  
</Directives>  
```  
  
### <a name="specifying-policy-for-members"></a><span data-ttu-id="86001-291">멤버에 대한 정책 지정</span><span class="sxs-lookup"><span data-stu-id="86001-291">Specifying policy for members</span></span>  
 <span data-ttu-id="86001-292">[Property](../../../docs/framework/net-native/property-element-net-native.md) 및 [Field](../../../docs/framework/net-native/field-element-net-native.md) 요소는 다음 정책 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-292">The [Property](../../../docs/framework/net-native/property-element-net-native.md) and [Field](../../../docs/framework/net-native/field-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="86001-293">`Browse` - 이 멤버에 대한 정보 쿼리는 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-293">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>  
  
-   <span data-ttu-id="86001-294">`Dynamic` - 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-294">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="86001-295">또한 포함 형식에 대한 정보 쿼리도 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-295">Also controls querying for information about the containing type.</span></span>  
  
-   <span data-ttu-id="86001-296">`Serialize` - Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-296">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="86001-297">이 정책은 생성자, 필드 및 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-297">This policy can be applied to constructors, fields, and properties.</span></span>  
  
 <span data-ttu-id="86001-298">[Method](../../../docs/framework/net-native/method-element-net-native.md) 및 [Event](../../../docs/framework/net-native/event-element-net-native.md) 요소는 다음 정책 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-298">The [Method](../../../docs/framework/net-native/method-element-net-native.md) and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="86001-299">`Browse` - 이 멤버에 대한 정보 쿼리는 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-299">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>  
  
-   <span data-ttu-id="86001-300">`Dynamic` - 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-300">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="86001-301">또한 포함 형식에 대한 정보 쿼리도 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-301">Also controls querying for information about the containing type.</span></span>  
  
 <span data-ttu-id="86001-302">이러한 정책 형식과 연관된 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-302">The settings associated with these policy types are:</span></span>  
  
-   <span data-ttu-id="86001-303">`Auto` - 기본 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-303">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="86001-304">특정 요소가 정책을 재정의하는 경우를 제외하면 정책을 지정하지 않는 것은 정책을 `Auto`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-304">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>  
  
-   <span data-ttu-id="86001-305">`Excluded` - 멤버에 대한 메타데이터를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-305">`Excluded` - Never include metadata for the member.</span></span>  
  
-   <span data-ttu-id="86001-306">`Included` - 출력에 부모 형식이 있으면 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-306">`Included` - Enable the policy if the parent type is present in the output.</span></span>  
  
-   <span data-ttu-id="86001-307">`Required` - 특정 멤버가 사용되지 않는 것으로 확인되더라도 도구 체인이 해당 멤버를 유지해야 하도록 지정하고 해당 멤버에 대해 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-307">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>  
  
## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="86001-308">런타임 지시문 파일 의미</span><span class="sxs-lookup"><span data-stu-id="86001-308">Runtime directives file semantics</span></span>  
 <span data-ttu-id="86001-309">상위 및 하위 요소 둘 다에 대해 정책을 동시에 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-309">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="86001-310">예를 들어 어셈블리 및 해당 어셈블리에 포함된 일부 형식에 대한 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-310">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="86001-311">표시되지 않는 특정 하위 요소는 부모의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-311">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="86001-312">예를 들어 `Assembly` 요소는 있는데 `Type` 요소는 없으면 `Assembly` 요소에 지정된 정책이 어셈블리의 각 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-312">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="86001-313">또한 여러 요소가 같은 프로그램 요소에 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-313">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="86001-314">예를 들어 개별 [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) 요소가 같은 어셈블리에 대해 같은 정책 요소를 각기 다르게 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-314">For example, separate [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="86001-315">다음 섹션에서는 이러한 경우 특정 형식에 대한 정책을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-315">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>  
  
 <span data-ttu-id="86001-316">제네릭 형식이나 메서드의 [Type](../../../docs/framework/net-native/type-element-net-native.md) 또는 [Method](../../../docs/framework/net-native/method-element-net-native.md) 요소는 자체 정책을 포함하지 않는 모든 인스턴스화에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-316">A [Type](../../../docs/framework/net-native/type-element-net-native.md) or [Method](../../../docs/framework/net-native/method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="86001-317">예를 들어 `Type`에 대해 정책을 지정하는 <xref:System.Collections.Generic.List%601> 요소는 해당 제네릭 형식의 생성된 모든 인스턴스에 적용됩니다. 단, `List<Int32>` 요소가 `TypeInstantiation`와 같은 생성된 특정 제네릭 형식에 대해 정책을 재정의하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="86001-317">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="86001-318">이러한 경우가 아니면 요소는 명명된 프로그램 요소에 대해 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-318">Otherwise, elements define policy for the program element named.</span></span>  
  
 <span data-ttu-id="86001-319">요소가 모호한 경우 엔진은 일치하는 항목을 찾으며 정확히 일치하는 항목이 발견되면 해당 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-319">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="86001-320">일치하는 항목이 여러 개이면 경고나 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-320">If it finds multiple matches, there will be a warning or error.</span></span>  
  
### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="86001-321">두 지시문이 같은 프로그램 요소에 정책을 적용하는 경우</span><span class="sxs-lookup"><span data-stu-id="86001-321">If two directives apply policy to the same program element</span></span>  
 <span data-ttu-id="86001-322">서로 다른 런타임 지시문 파일의 두 요소가 어셈블리나 형식 등의 같은 프로그램 요소에 대한 동일 정책 형식을 각기 다른 값으로 설정하려는 경우에는 다음과 같은 방법으로 충돌을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-322">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>  
  
1.  <span data-ttu-id="86001-323">`Excluded` 요소가 있으면 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-323">If the `Excluded` element is present, it has precedence.</span></span>  
  
2.  <span data-ttu-id="86001-324">`Required`인 항목이 `Required`가 아닌 항목보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-324">`Required` has precedence over not `Required`.</span></span>  
  
3.  <span data-ttu-id="86001-325">`All`, `PublicAndInternal`, `Public`이 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-325">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>  
  
4.  <span data-ttu-id="86001-326">명시적 설정이 `Auto`보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-326">Any explicit setting has precedence over `Auto`.</span></span>  
  
 <span data-ttu-id="86001-327">예를 들어 프로젝트 하나에 다음과 같은 두 런타임 지시문 파일이 포함되어 있으면 DataClasses.dll의 serialization 정책이 `Required Public` 및 `All` 둘 다로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-327">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="86001-328">이 경우 serialization 정책은 `Required All`로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-328">In this case, the serialization policy would be resolved as `Required All`.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public"/>  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="All" />  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
 <span data-ttu-id="86001-329">그러나 단일 런타임 지시문 파일의 두 지시문이 같은 프로그램 요소에 대해 같은 정책 형식을 설정하려고 하면 XML 스키마 정의 도구에 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-329">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>  
  
### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="86001-330">자식 및 부모 요소가 같은 정책 형식을 적용하는 경우</span><span class="sxs-lookup"><span data-stu-id="86001-330">If child and parent elements apply the same policy type</span></span>  
 <span data-ttu-id="86001-331">자식 요소는 `Excluded` 설정을 포함하여 부모 요소를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86001-331">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="86001-332">대개 이러한 재정의로 인해 `Auto`를 지정하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-332">Overriding is the main reason you would want to specify `Auto`.</span></span>  
  
 <span data-ttu-id="86001-333">다음 예에서는 `DataClasses`에 포함되어 있지 않은 `DataClasses.ViewModels`의 모든 항목에 대한 serialization 정책 설정은 `Required Public`이 되고 `DataClasses` 및 `DataClasses.ViewModels`에 모두 포함되어 있는 모든 항목에 대한 serialization 정책 설정은 `All`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-333">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public" >  
         <Namespace Name="DataClasses.ViewModels" Seralize="All" />  
      </Assembly>  
   </Appliction>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="86001-334">개방형 제네릭 및 인스턴스화된 요소 형식이 같은 정책을 적용하는 경우</span><span class="sxs-lookup"><span data-stu-id="86001-334">If open generics and instantiated elements apply the same policy type</span></span>  
 <span data-ttu-id="86001-335">다음 예제에서는 엔진이 다른 이유로 인해 `Dictionary<int,int>` 정책을 적용해야 하는 경우에만 `Browse`에 `Browse` 정책이 할당됩니다(그렇지 않으면 이 정책이 기본 동작임). <xref:System.Collections.Generic.Dictionary%602>의 다른 모든 인스턴스화에서는 모든 구성원을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-335">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public" >  
         <Namespace Name="DataClasses.ViewModels" Seralize="All" />  
      </Assembly>  
      <Namespace Name="DataClasses.Generics" />  
      <Type Name="Dictionary" Browse="All" />  
      <TypeInstantiation Name="Dictionary"   
                         Arguments="System.Int32,System.Int32" Browse="Auto" />  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
### <a name="how-policy-is-inferred"></a><span data-ttu-id="86001-336">정책을 유추하는 방법</span><span class="sxs-lookup"><span data-stu-id="86001-336">How policy is inferred</span></span>  
 <span data-ttu-id="86001-337">각 정책 형식에는 해당 정책 형식의 유무가 다른 구문에 주는 영향을 결정하는 여러 규칙 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-337">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>  
  
#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="86001-338">Browse 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="86001-338">The effect of Browse policy</span></span>  
 <span data-ttu-id="86001-339">형식에 `Browse` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-339">Applying the `Browse` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-340">해당 형식의 기본 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-340">The base type of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-341">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-341">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-342">형식이 대리자인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-342">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-343">형식의 각 인터페이스가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-343">Each interface of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-344">형식에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-344">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-345">형식이 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-345">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-346">형식이 제네릭이면 해당 형식이 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-346">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="86001-347">메서드에 `Browse` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-347">Applying the `Browse` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-348">메서드의 각 매개 변수 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-348">Each parameter type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-349">해당 메서드의 반환 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-349">The return type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-350">해당 메서드의 포함 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-350">The containing type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-351">메서드가 인스턴스화된 제네릭 메서드인 경우 인스턴스화되지 않은 제네릭 메서드가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-351">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-352">메서드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-352">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-353">메서드가 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-353">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-354">메서드가 제네릭이면 해당 메서드가 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-354">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="86001-355">필드에 `Browse` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-355">Applying the `Browse` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-356">필드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-356">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-357">필드의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-357">The type of the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-358">필드가 속하는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-358">The type to which the field belongs is marked with the `Browse` policy.</span></span>  
  
#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="86001-359">Dynamic 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="86001-359">The effect of Dynamic policy</span></span>  
 <span data-ttu-id="86001-360">형식에 `Dynamic` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-360">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-361">해당 형식의 기본 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-361">The base type of the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-362">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-362">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-363">형식이 대리자 형식인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-363">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-364">형식의 각 인터페이스가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-364">Each interface of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-365">형식에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-365">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-366">형식이 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-366">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-367">형식이 제네릭이면 해당 형식이 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-367">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="86001-368">메서드에 `Dynamic` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-368">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-369">메서드의 각 매개 변수 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-369">Each parameter type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-370">해당 메서드의 반환 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-370">The return type of the method is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-371">해당 메서드의 포함 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-371">The containing type of the method is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-372">메서드가 인스턴스화된 제네릭 메서드인 경우 인스턴스화되지 않은 제네릭 메서드가 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-372">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-373">메서드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-373">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-374">메서드가 제네릭인 경우 각 제약 조건 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-374">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-375">메서드가 제네릭이면 해당 메서드가 인스턴스화되는 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-375">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-376">`MethodInfo.Invoke`를 통해 메서드를 호출할 수 있으며 <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>를 통해 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-376">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="86001-377">필드에 `Dynamic` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-377">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-378">필드에 적용된 각 특성의 형식이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-378">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-379">필드의 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-379">The type of the field is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-380">필드가 속하는 형식이 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-380">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>  
  
#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="86001-381">Activation 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="86001-381">The effect of Activation policy</span></span>  
 <span data-ttu-id="86001-382">형식에 Activation 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-382">Applying the Activation policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-383">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-383">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-384">형식이 대리자 형식인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-384">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-385">형식의 생성자가 `Activation` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-385">Constructors of the type are marked with the `Activation` policy.</span></span>  
  
 <span data-ttu-id="86001-386">메서드에 `Activation` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-386">Applying the `Activation` policy to a method involves the following policy change:</span></span>  
  
-   <span data-ttu-id="86001-387"><xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> 및 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 메서드를 통해 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-387">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="86001-388">메서드의 경우에는 `Activation` 정책이 생성자에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-388">For methods, the `Activation` policy affects constructors only.</span></span>  
  
 <span data-ttu-id="86001-389">필드에는 `Activation` 정책을 적용해도 아무런 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-389">Applying the `Activation` policy to a field has no effect.</span></span>  
  
#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="86001-390">Serialize 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="86001-390">The effect of Serialize policy</span></span>  
 <span data-ttu-id="86001-391">`Serialize` 정책을 적용하면 일반적인 리플렉션 기반 serializer를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-391">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="86001-392">그러나 Microsoft는 타사 serializer의 정확한 리플렉션 액세스 패턴을 확인할 수 없으므로 이 정책이 완전히 적용되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-392">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>  
  
 <span data-ttu-id="86001-393">형식에 `Serialize` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-393">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-394">해당 형식의 기본 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-394">The base type of the type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-395">형식이 인스턴스화된 제네릭인 경우 인스턴스화되지 않은 형식 버전이 `Browse` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-395">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="86001-396">형식이 대리자 형식인 경우에는 형식의 `Invoke` 메서드가 `Dynamic` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-396">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="86001-397">형식이 열거형이면 해당 형식의 배열이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-397">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-398">형식이 <xref:System.Collections.Generic.IEnumerable%601>를 구현하는 경우 `T`가 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-398">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-399">형식이 <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> 또는 <xref:System.Collections.Generic.IReadOnlyList%601>이면 `T[]` 및 <xref:System.Collections.Generic.List%601>는 `Serialize` 정책으로 표시되지만 인터페이스 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-399">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-400">형식이 <xref:System.Collections.Generic.List%601>이면 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-400">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-401">형식이 <xref:System.Collections.Generic.IDictionary%602>이면 <xref:System.Collections.Generic.Dictionary%602>가 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-401">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="86001-402">그러나 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-402">but no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-403">형식이 <xref:System.Collections.Generic.Dictionary%602>이면 형식의 멤버는 `Serialize` 정책으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-403">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-404">형식이 <xref:System.Collections.Generic.IDictionary%602>를 구현하는 경우 `TKey` 및 `TValue`는 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-404">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-405">각 생성자, 각 속성 접근자 및 각 필드가 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-405">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>  
  
 <span data-ttu-id="86001-406">메서드에 `Serialize` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-406">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-407">포함 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-407">The containing type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-408">해당 메서드의 반환 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-408">The return type of the method is marked with the `Serialize` policy.</span></span>  
  
 <span data-ttu-id="86001-409">필드에 `Serialize` 정책을 적용하면 정책이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-409">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="86001-410">포함 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-410">The containing type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="86001-411">필드의 형식이 `Serialize` 정책으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-411">The type of the field is marked with the `Serialize` policy.</span></span>  
  
#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserialier-policies"></a><span data-ttu-id="86001-412">XmlSerializer, DataContractSerializer 및 DataContractJsonSerialier 정책의 영향</span><span class="sxs-lookup"><span data-stu-id="86001-412">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerialier policies</span></span>  
 <span data-ttu-id="86001-413">리플렉션 기반 serializer용인 `Serialize` 정책과는 달리 `XmlSerializer`, `DataContractSerializer` 및 `DataContractJsonSerializer` 정책은 serializer 집합([!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인)을 사용하도록 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-413">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the `XmlSerializer`, `DataContractSerializer`, and `DataContractJsonSerializer` policies are used to enable a set of serializers that are known to the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="86001-414">이러한 serializer는 리플렉션을 사용하여 구현되지 않으며 런타임에 serialize할 수 있는 형식 집합은 리플렉션 가능한 형식과 비슷한 방식으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="86001-414">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>  
  
 <span data-ttu-id="86001-415">이러한 정책 중 하나를 형식에 적용하면 일치하는 serializer를 사용하여 형식을 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-415">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="86001-416">또한 serialization 엔진이 serialization을 수행해야 한다고 정적으로 확인할 수 있는 모든 형식도 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-416">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>  
  
 <span data-ttu-id="86001-417">이러한 정책은 메서드 또는 필드에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86001-417">These policies have no effect on methods or fields.</span></span>  
  
 <span data-ttu-id="86001-418">자세한 내용은 [Windows 스토어 앱을 .NET 네이티브로 마이그레이션](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)에서 “직렬 변환기의 차이점” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86001-418">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86001-419">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86001-419">See Also</span></span>  
 [<span data-ttu-id="86001-420">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="86001-420">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="86001-421">리플렉션 및 .NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="86001-421">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)
