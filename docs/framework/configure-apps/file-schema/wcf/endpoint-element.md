---
title: "&lt;endpoint&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 937819fabc50d4a0a43c6a3168e6d8a77bf4ceca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltendpointgt-element"></a><span data-ttu-id="0c334-102">&lt;endpoint&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="0c334-102">&lt;endpoint&gt; element</span></span>
<span data-ttu-id="0c334-103">서비스 공개에 사용되는 서비스 끝점에 대한 바인딩, 계약 및 주소 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="0c334-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0c334-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c334-105">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="0c334-105">\<service></span></span>  
<span data-ttu-id="0c334-106">\<끝점 ></span><span class="sxs-lookup"><span data-stu-id="0c334-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c334-107">구문</span><span class="sxs-lookup"><span data-stu-id="0c334-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   bindingName="String"  
   bindingNamespace="String"  
   contract="String"  
   endpointConfiguration="String"   isSystemEndpoint="Boolean"   kind="String"   listenUriMode="Explicit/Unique"  
   listenUri="Uri"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c334-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c334-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0c334-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c334-110">특성</span><span class="sxs-lookup"><span data-stu-id="0c334-110">Attributes</span></span>  
  
|<span data-ttu-id="0c334-111">특성</span><span class="sxs-lookup"><span data-stu-id="0c334-111">Attribute</span></span>|<span data-ttu-id="0c334-112">설명</span><span class="sxs-lookup"><span data-stu-id="0c334-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c334-113">address</span><span class="sxs-lookup"><span data-stu-id="0c334-113">address</span></span>|<span data-ttu-id="0c334-114">끝점의 주소를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="0c334-115">주소는 절대 주소 또는 상대 주소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="0c334-116">상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="0c334-117">주소가 구성되지 않으면 해당 끝점의 주소를 기본 주소로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="0c334-118">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="0c334-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c334-119">behaviorConfiguration</span></span>|<span data-ttu-id="0c334-120">끝점에 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="0c334-121">바인딩</span><span class="sxs-lookup"><span data-stu-id="0c334-121">binding</span></span>|<span data-ttu-id="0c334-122">사용할 바인딩 형식을 지정하는 필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="0c334-123">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="0c334-124">이 형식은 바인딩의 형식 이름이 아니라 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="0c334-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c334-125">bindingConfiguration</span></span>|<span data-ttu-id="0c334-126">끝점이 인스턴스화될 때 사용하는 바인딩의 바인딩 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="0c334-127">바인딩 이름은 끝점이 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="0c334-128">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="0c334-129">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="0c334-130">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="0c334-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="0c334-131">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="0c334-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="0c334-132">bindingName</span></span>|<span data-ttu-id="0c334-133">WSDL을 통해 정의를 내보내기 위한 바인딩의 정규화된 고유 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="0c334-134">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="0c334-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="0c334-135">bindingNamespace</span></span>|<span data-ttu-id="0c334-136">WSDL을 통해 정의를 내보내기 위한 바인딩 네임스페이스의 정규화된 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="0c334-137">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="0c334-138">계약(contract)</span><span class="sxs-lookup"><span data-stu-id="0c334-138">contract</span></span>|<span data-ttu-id="0c334-139">이 끝점이 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="0c334-140">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="0c334-141">서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="0c334-142">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="0c334-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c334-143">endpointConfiguration</span></span>|<span data-ttu-id="0c334-144">이 표준 끝점의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 끝점의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="0c334-145">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="0c334-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="0c334-146">isSystemEndpoint</span></span>|<span data-ttu-id="0c334-147">끝점이 인프라 끝점인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="0c334-148">kind</span><span class="sxs-lookup"><span data-stu-id="0c334-148">kind</span></span>|<span data-ttu-id="0c334-149">적용되는 표준 끝점의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="0c334-150">이 형식이 `<extensions>` 섹션 또는 machine.config에 등록되어야 합니다. 지정하지 않으면 일반 서비스 끝점이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="0c334-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="0c334-151">listenUriMode</span></span>|<span data-ttu-id="0c334-152">서비스에서 수신하도록 제공된 `ListenUri`를 전송에서 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="0c334-153">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-153">Valid values are</span></span><br /><br /> <span data-ttu-id="0c334-154">명시적</span><span class="sxs-lookup"><span data-stu-id="0c334-154">-   Explicit</span></span><br /><span data-ttu-id="0c334-155">고유</span><span class="sxs-lookup"><span data-stu-id="0c334-155">-   Unique</span></span><br /><br /> <span data-ttu-id="0c334-156">기본값은 Explicit입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="0c334-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="0c334-157">listenUri</span></span>|<span data-ttu-id="0c334-158">서비스 끝점이 수신하는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="0c334-159">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="0c334-160">name</span><span class="sxs-lookup"><span data-stu-id="0c334-160">name</span></span>|<span data-ttu-id="0c334-161">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-161">Optional attribute.</span></span> <span data-ttu-id="0c334-162">서비스 끝점의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="0c334-163">기본값은 바인딩 이름과 계약 설명 이름을 연결한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="0c334-164">서비스에 끝점이 여러 개일 수 있으므로 끝점의 `name` 특성은 서비스 이름과 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c334-165">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c334-165">Child Elements</span></span>  
  
|<span data-ttu-id="0c334-166">요소</span><span class="sxs-lookup"><span data-stu-id="0c334-166">Element</span></span>|<span data-ttu-id="0c334-167">설명</span><span class="sxs-lookup"><span data-stu-id="0c334-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c334-168">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="0c334-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="0c334-169">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="0c334-170">\<identity ></span><span class="sxs-lookup"><span data-stu-id="0c334-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0c334-171">한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c334-172">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c334-172">Parent Elements</span></span>  
  
|<span data-ttu-id="0c334-173">요소</span><span class="sxs-lookup"><span data-stu-id="0c334-173">Element</span></span>|<span data-ttu-id="0c334-174">설명</span><span class="sxs-lookup"><span data-stu-id="0c334-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c334-175">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="0c334-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="0c334-176">클라이언트가 연결할 수 있는 끝점의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0c334-177">예제</span><span class="sxs-lookup"><span data-stu-id="0c334-177">Example</span></span>  
 <span data-ttu-id="0c334-178">서비스 끝점 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0c334-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint   
    address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    bindingName="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
    <Headers>  
       <Region xmlns="http://tempuri.org/">EastCoast</Region>  
       <Member xmlns="http://tempuri.org/">Gold</Member>  
    </Headers>  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c334-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c334-179">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.Description.ServiceEndpoint>  
 [<span data-ttu-id="0c334-180">끝점: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="0c334-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="0c334-181">방법: 구성에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="0c334-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
