---
title: '&lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: d6690722f743c74ee9909f029133f506e05ecb1d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltdeclaredtypesgt"></a><span data-ttu-id="3b9de-102">&lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="3b9de-102">&lt;declaredTypes&gt;</span></span>
<span data-ttu-id="3b9de-103">deserialize할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-103">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="3b9de-104">데이터 계약 및 알려진된 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-104">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="3b9de-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="3b9de-105">system.runtime.serialization</span></span>  
<span data-ttu-id="3b9de-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3b9de-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="3b9de-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="3b9de-107">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b9de-108">구문</span><span class="sxs-lookup"><span data-stu-id="3b9de-108">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
                <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b9de-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3b9de-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3b9de-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b9de-111">특성</span><span class="sxs-lookup"><span data-stu-id="3b9de-111">Attributes</span></span>  
 <span data-ttu-id="3b9de-112">없음</span><span class="sxs-lookup"><span data-stu-id="3b9de-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3b9de-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3b9de-113">Child Elements</span></span>  
  
|<span data-ttu-id="3b9de-114">요소</span><span class="sxs-lookup"><span data-stu-id="3b9de-114">Element</span></span>|<span data-ttu-id="3b9de-115">설명</span><span class="sxs-lookup"><span data-stu-id="3b9de-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b9de-116">\<add></span><span class="sxs-lookup"><span data-stu-id="3b9de-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="3b9de-117">알려진 형식을 필요로 하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b9de-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3b9de-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3b9de-119">요소</span><span class="sxs-lookup"><span data-stu-id="3b9de-119">Element</span></span>|<span data-ttu-id="3b9de-120">설명</span><span class="sxs-lookup"><span data-stu-id="3b9de-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b9de-121">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3b9de-121">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="3b9de-122"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b9de-123">설명</span><span class="sxs-lookup"><span data-stu-id="3b9de-123">Remarks</span></span>  
 <span data-ttu-id="3b9de-124">알려진된 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-124">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b9de-125">예제</span><span class="sxs-lookup"><span data-stu-id="3b9de-125">Example</span></span>  
 <span data-ttu-id="3b9de-126">다음 XML 코드에서는 선언 된 형식 및 알려진된 형식에 추가 `DataContractSerializer` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="3b9de-127">예제에서는 추가되는 세 가지 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-127">The example shows three types being added.</span></span> <span data-ttu-id="3b9de-128">첫 번째는 "Item"이라는 알려진 형식을 사용하는 "Orders"라는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="3b9de-129">두 번째 선언된 형식은 <xref:System.Collections.Generic.List%601>을 알려진 형식으로 사용하는 `Item`입니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="3b9de-130">마지막으로 세 번째 선언된 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="3b9de-131"><xref:System.Collections.Generic.Dictionary%602> 클래스 형식은 두 개의 형식 매개 변수가 있는 제네릭 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="3b9de-132">첫 번째는 키를 나타내고 두 번째는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="3b9de-133">다음 예제에서는 알려진 형식 목록에 두 번째 형식(값)의 <xref:System.Collections.Generic.List%601>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="3b9de-134">`index` 특성을 사용하여 알려진 형식에 사용할 형식 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b9de-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="3b9de-135">이 경우 값 형식은 "1"로 설정된 index 특성으로 표시됩니다(컬렉션은 0부터 시작).</span><span class="sxs-lookup"><span data-stu-id="3b9de-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
            <parameter index="1"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b9de-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b9de-136">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="3b9de-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3b9de-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="3b9de-138">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="3b9de-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="3b9de-139">\<add></span><span class="sxs-lookup"><span data-stu-id="3b9de-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
