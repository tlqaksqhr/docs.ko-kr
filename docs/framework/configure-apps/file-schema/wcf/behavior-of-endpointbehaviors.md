---
title: "&lt;endpointBehaviors&gt;의 &lt;behavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bef07c6cdd80874bfa17994dffafe4d3f2cfc5a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltbehaviorgt-of-ltendpointbehaviorsgt"></a><span data-ttu-id="2df22-102">&lt;endpointBehaviors&gt;의 &lt;behavior&gt;</span><span class="sxs-lookup"><span data-stu-id="2df22-102">&lt;behavior&gt; of &lt;endpointBehaviors&gt;</span></span>
<span data-ttu-id="2df22-103">`behavior` 요소는 끝점의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="2df22-104">각 동작은 해당 `name`으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="2df22-105">끝점은 이 이름을 통해 각 동작에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="2df22-106">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2df22-107">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="2df22-108">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2df22-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="2df22-109">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="2df22-109">\<behaviors></span></span>  
<span data-ttu-id="2df22-110">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2df22-110">\<endpointBehaviors></span></span>  
<span data-ttu-id="2df22-111">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="2df22-111">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df22-112">구문</span><span class="sxs-lookup"><span data-stu-id="2df22-112">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2df22-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2df22-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2df22-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2df22-115">특성</span><span class="sxs-lookup"><span data-stu-id="2df22-115">Attributes</span></span>  
  
|<span data-ttu-id="2df22-116">특성</span><span class="sxs-lookup"><span data-stu-id="2df22-116">Attribute</span></span>|<span data-ttu-id="2df22-117">설명</span><span class="sxs-lookup"><span data-stu-id="2df22-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2df22-118">name</span><span class="sxs-lookup"><span data-stu-id="2df22-118">name</span></span>|<span data-ttu-id="2df22-119">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="2df22-120">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="2df22-121">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-121">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2df22-122">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-122">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2df22-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2df22-123">Child Elements</span></span>  
  
|<span data-ttu-id="2df22-124">요소</span><span class="sxs-lookup"><span data-stu-id="2df22-124">Element</span></span>|<span data-ttu-id="2df22-125">설명</span><span class="sxs-lookup"><span data-stu-id="2df22-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2df22-126">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="2df22-126">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="2df22-127">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-127">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="2df22-128">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="2df22-128">\<callbackDebug></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|<span data-ttu-id="2df22-129">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 콜백 개체의 서비스 디버깅을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-129">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>|  
|[<span data-ttu-id="2df22-130">\<callbackTimeouts ></span><span class="sxs-lookup"><span data-stu-id="2df22-130">\<callbackTimeouts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|<span data-ttu-id="2df22-131">클라이언트 콜백에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-131">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="2df22-132">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="2df22-132">\<clientVia></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|<span data-ttu-id="2df22-133">메시지가 이동할 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-133">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="2df22-134">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="2df22-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|<span data-ttu-id="2df22-135">DataContractSerializer에 대한 구성 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-135">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="2df22-136">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="2df22-136">\<dispatcherSynchronization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|<span data-ttu-id="2df22-137">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-137">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="2df22-138">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="2df22-138">\<enableWebScript></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|<span data-ttu-id="2df22-139">ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 끝점 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-139">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="2df22-140">동작만 함께 사용 하 여 사용할는 \<webHttpBinding > 표준 바인딩 또는 \<webMessageEncoding > 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-140">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="2df22-141">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="2df22-141">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="2df22-142">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장명 등 끝점에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-142">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="2df22-143">\<soapProcessing ></span><span class="sxs-lookup"><span data-stu-id="2df22-143">\<soapProcessing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|<span data-ttu-id="2df22-144">서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 끝점 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-144">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="2df22-145">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="2df22-145">\<synchronousReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|<span data-ttu-id="2df22-146">서비스 또는 클라이언트 응용 프로그램에서 메시지 수신을 위한 런타임 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-146">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="2df22-147">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-147">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="2df22-148">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="2df22-148">\<transactedBatching></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|<span data-ttu-id="2df22-149">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-149">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="2df22-150">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="2df22-150">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|<span data-ttu-id="2df22-151">구성을 통해 끝점에서 WebHttpBehavior를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-151">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="2df22-152">이 동작을 함께 사용 하는 경우는 \<webHttpBinding > 표준 바인딩 웹 프로그래밍 모델을 사용 하면 한 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-152">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2df22-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2df22-153">Parent Elements</span></span>  
  
|<span data-ttu-id="2df22-154">요소</span><span class="sxs-lookup"><span data-stu-id="2df22-154">Element</span></span>|<span data-ttu-id="2df22-155">설명</span><span class="sxs-lookup"><span data-stu-id="2df22-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2df22-156">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2df22-156">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="2df22-157">끝점 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2df22-157">A collection of endpoint behavior elements.</span></span>|
