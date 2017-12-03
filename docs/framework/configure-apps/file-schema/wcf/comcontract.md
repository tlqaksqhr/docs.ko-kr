---
title: '&lt;comContract&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f4fb83478ef7061a4b14e87d2dce7f9cd9bbf8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="40ab9-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="40ab9-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="40ab9-103">COM+ 통합 서비스 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="40ab9-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="40ab9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="40ab9-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="40ab9-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40ab9-106">구문</span><span class="sxs-lookup"><span data-stu-id="40ab9-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40ab9-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="40ab9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="40ab9-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40ab9-109">특성</span><span class="sxs-lookup"><span data-stu-id="40ab9-109">Attributes</span></span>  
  
|<span data-ttu-id="40ab9-110">특성</span><span class="sxs-lookup"><span data-stu-id="40ab9-110">Attribute</span></span>|<span data-ttu-id="40ab9-111">설명</span><span class="sxs-lookup"><span data-stu-id="40ab9-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40ab9-112">계약(contract)</span><span class="sxs-lookup"><span data-stu-id="40ab9-112">contract</span></span>|<span data-ttu-id="40ab9-113">계약 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="40ab9-114">name</span><span class="sxs-lookup"><span data-stu-id="40ab9-114">name</span></span>|<span data-ttu-id="40ab9-115">계약 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="40ab9-116">namespace</span><span class="sxs-lookup"><span data-stu-id="40ab9-116">namespace</span></span>|<span data-ttu-id="40ab9-117">계약 네임스페이스를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="40ab9-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="40ab9-118">requiresSession</span></span>|<span data-ttu-id="40ab9-119">계약을 세션 바인딩에서만 사용할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="40ab9-120">서비스가 초기화될 때 통합 런타임에서는 사용될 바인딩 형식과 이 설정이 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="40ab9-121">계약의 바인딩 중 하나 이상이 충돌할 경우 예외가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="40ab9-122">이 속성이 `false`이고 단방향 채널을 사용하며 [out] 매개 변수가 있을 경우에도 예외가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40ab9-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="40ab9-123">Child Elements</span></span>  
  
|<span data-ttu-id="40ab9-124">요소</span><span class="sxs-lookup"><span data-stu-id="40ab9-124">Element</span></span>|<span data-ttu-id="40ab9-125">설명</span><span class="sxs-lookup"><span data-stu-id="40ab9-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40ab9-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="40ab9-126">persistableTypes</span></span>|<span data-ttu-id="40ab9-127">모든 지속 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-127">All the persistable types.</span></span>|  
|<span data-ttu-id="40ab9-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="40ab9-128">userDefinedTypes</span></span>|<span data-ttu-id="40ab9-129">서비스 계약에 포함될 UDT(사용자 정의 형식) 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="40ab9-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="40ab9-130">exposedMethods</span></span>|<span data-ttu-id="40ab9-131">COM+ 구성 요소의 인터페이스가 웹 서비스로 공개될 때 노출되는 COM+ 메서드 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40ab9-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="40ab9-132">Parent Elements</span></span>  
  
|<span data-ttu-id="40ab9-133">요소</span><span class="sxs-lookup"><span data-stu-id="40ab9-133">Element</span></span>|<span data-ttu-id="40ab9-134">설명</span><span class="sxs-lookup"><span data-stu-id="40ab9-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40ab9-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="40ab9-135">comContracts</span></span>|<span data-ttu-id="40ab9-136">`comContract` 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40ab9-137">설명</span><span class="sxs-lookup"><span data-stu-id="40ab9-137">Remarks</span></span>  
 <span data-ttu-id="40ab9-138">COM + 통합 서비스 계약은 현재 "http://tempuri.org" 네임 스페이스로 제한 되며와 계약 이름은 지원 COM 인터페이스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-138">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="40ab9-139">그러나 구성 파일에서`comContracts` 섹션 및 `comContract` 요소를 사용하여 대안을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="40ab9-140">예를 들어 다음 구성을 사용하여 포함시킬 네임스페이스, 계약 이름, 사용자 정의 형식 및 서비스 계약의 기타 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="40ab9-141">지정된 네임스페이스와 계약 이름은 서비스가 초기화될 때 생성된 서비스 설명에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ab9-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ab9-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40ab9-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="40ab9-143">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="40ab9-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="40ab9-144">COM + 응용 프로그램과 통합</span><span class="sxs-lookup"><span data-stu-id="40ab9-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="40ab9-145">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="40ab9-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
