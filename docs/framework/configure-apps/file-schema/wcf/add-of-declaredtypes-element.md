---
title: '&lt;declaredTypes&gt; 요소의 &lt;add&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 90eaf11ce8b9e3675a23ed3875680b03f149b56b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="abb75-102">&lt;declaredTypes&gt; 요소의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="abb75-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="abb75-103">deserialization을 수행하는 동안 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="abb75-104">선언된 각 형식에는 선언된 형식의 필드 또는 속성으로 반환되는 알려진 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="abb75-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="abb75-105">system.runtime.serialization</span></span>  
<span data-ttu-id="abb75-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="abb75-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="abb75-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="abb75-107">\<declaredTypes></span></span>  
<span data-ttu-id="abb75-108">\<추가 >의 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="abb75-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abb75-109">구문</span><span class="sxs-lookup"><span data-stu-id="abb75-109">Syntax</span></span>  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abb75-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="abb75-110">Attributes and Elements</span></span>  
 <span data-ttu-id="abb75-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abb75-112">특성</span><span class="sxs-lookup"><span data-stu-id="abb75-112">Attributes</span></span>  
  
|<span data-ttu-id="abb75-113">특성</span><span class="sxs-lookup"><span data-stu-id="abb75-113">Attribute</span></span>|<span data-ttu-id="abb75-114">설명</span><span class="sxs-lookup"><span data-stu-id="abb75-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abb75-115">형식</span><span class="sxs-lookup"><span data-stu-id="abb75-115">type</span></span>|<span data-ttu-id="abb75-116">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="abb75-117">형식 이름(네임스페이스 포함), 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abb75-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="abb75-118">Child Elements</span></span>  
  
|<span data-ttu-id="abb75-119">요소</span><span class="sxs-lookup"><span data-stu-id="abb75-119">Element</span></span>|<span data-ttu-id="abb75-120">설명</span><span class="sxs-lookup"><span data-stu-id="abb75-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abb75-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="abb75-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="abb75-122">추가 중인 선언된 형식에 대해 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="abb75-123">선언된 형식이 제네릭 형식이면 매개 변수 요소를 `<knownType>` 요소에 추가하여 알려진 형식을 반환하는 데 사용되는 제네릭 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="abb75-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="abb75-124">Parent Elements</span></span>  
  
|<span data-ttu-id="abb75-125">요소</span><span class="sxs-lookup"><span data-stu-id="abb75-125">Element</span></span>|<span data-ttu-id="abb75-126">설명</span><span class="sxs-lookup"><span data-stu-id="abb75-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abb75-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="abb75-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="abb75-128"><xref:System.Runtime.Serialization.DataContractSerializer>에서 deserialization을 수행하는 동안 알려진 형식이 필요한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abb75-129">설명</span><span class="sxs-lookup"><span data-stu-id="abb75-129">Remarks</span></span>  
 <span data-ttu-id="abb75-130">알려진된 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="abb75-131">참조는 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 이 요소를 사용 하는 예제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abb75-132"><xref:System.Object> 형식을 `<declaredType>`으로 추가하면 <xref:System.Configuration.ConfigurationErrorsException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="abb75-133">이는 <xref:System.Object> 형식은 구성에서 선언된 형식으로 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="abb75-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abb75-134">예제</span><span class="sxs-lookup"><span data-stu-id="abb75-134">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="abb75-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abb75-135">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="abb75-136">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="abb75-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="abb75-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="abb75-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="abb75-138">\<추가 >의 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="abb75-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
