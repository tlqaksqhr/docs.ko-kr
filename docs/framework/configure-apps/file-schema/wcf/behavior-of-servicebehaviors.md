---
title: "&lt;serviceBehaviors&gt;의 &lt;behavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b86d685cd3b5fc26f2df2d3e722a908c04422d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt"></a><span data-ttu-id="5a810-102">&lt;serviceBehaviors&gt;의 &lt;behavior&gt;</span><span class="sxs-lookup"><span data-stu-id="5a810-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt;</span></span>
<span data-ttu-id="5a810-103">`behavior` 요소는 서비스의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="5a810-104">각 동작은 해당 `name`으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="5a810-105">서비스 사용 하 여이 이름을 통해 각 동작에 연결할 수는 `behaviorConfiguration` 특성에는 [ \<끝점 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="5a810-106">따라서 설정을 다시 정의하지 않고도 끝점에서 일반 동작 구성을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="5a810-107">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-107">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5a810-108">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a810-109">Windows 워크플로 활동에는 동작 요소와 같은 [ \<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) 요소는에 설명 되어는 [ \<동작 >의 \< serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) 페이지.</span><span class="sxs-lookup"><span data-stu-id="5a810-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
 <span data-ttu-id="5a810-110">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5a810-110">\<system.ServiceModel></span></span>  
<span data-ttu-id="5a810-111">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5a810-111">\<behaviors></span></span>  
<span data-ttu-id="5a810-112">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5a810-112">\<serviceBehaviors></span></span>  
<span data-ttu-id="5a810-113">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5a810-113">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a810-114">구문</span><span class="sxs-lookup"><span data-stu-id="5a810-114">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
       <behavior name="String" />  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a810-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5a810-115">Attributes and Elements</span></span>  
 <span data-ttu-id="5a810-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a810-117">특성</span><span class="sxs-lookup"><span data-stu-id="5a810-117">Attributes</span></span>  
  
|<span data-ttu-id="5a810-118">특성</span><span class="sxs-lookup"><span data-stu-id="5a810-118">Attribute</span></span>|<span data-ttu-id="5a810-119">설명</span><span class="sxs-lookup"><span data-stu-id="5a810-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a810-120">name</span><span class="sxs-lookup"><span data-stu-id="5a810-120">name</span></span>|<span data-ttu-id="5a810-121">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-121">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="5a810-122">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-122">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="5a810-123">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-123">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5a810-124">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-124">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a810-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5a810-125">Child Elements</span></span>  
  
|<span data-ttu-id="5a810-126">요소</span><span class="sxs-lookup"><span data-stu-id="5a810-126">Element</span></span>|<span data-ttu-id="5a810-127">설명</span><span class="sxs-lookup"><span data-stu-id="5a810-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a810-128">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="5a810-128">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|<span data-ttu-id="5a810-129">DataContractSerializer에 대한 구성 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-129">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="5a810-130">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="5a810-130">\<persistenceProvider></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|<span data-ttu-id="5a810-131">사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-131">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[<span data-ttu-id="5a810-132">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="5a810-132">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="5a810-133">라우팅 서비스에 대한 런타임 액세스를 제공하여 라우팅 구성의 동적 수정을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-133">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[<span data-ttu-id="5a810-134">\<a g e r ></span><span class="sxs-lookup"><span data-stu-id="5a810-134">\<serviceAuthenticationManager></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|<span data-ttu-id="5a810-135">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-135">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[<span data-ttu-id="5a810-136">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="5a810-136">\<serviceAuthorization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|<span data-ttu-id="5a810-137">서비스 작업에 대한 액세스 권한을 부여하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-137">Specifies settings that authorize access to service operations.</span></span>|  
|[<span data-ttu-id="5a810-138">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5a810-138">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="5a810-139">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-139">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[<span data-ttu-id="5a810-140">\<serviceDebug ></span><span class="sxs-lookup"><span data-stu-id="5a810-140">\<serviceDebug></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|<span data-ttu-id="5a810-141">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스의 디버깅 및 도움말 정보 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-141">Specifies debugging and help information features for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
|[<span data-ttu-id="5a810-142">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="5a810-142">\<serviceDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|<span data-ttu-id="5a810-143">서비스 끝점의 검색 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-143">Specifies the discoverability of service endpoints.</span></span>|  
|[<span data-ttu-id="5a810-144">\<serviceMetadata ></span><span class="sxs-lookup"><span data-stu-id="5a810-144">\<serviceMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|<span data-ttu-id="5a810-145">서비스 메타데이터 및 관련 정보의 게시를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-145">Specifies the publication of service metadata and associated information.</span></span>|  
|[<span data-ttu-id="5a810-146">\<serviceSecurityAudit ></span><span class="sxs-lookup"><span data-stu-id="5a810-146">\<serviceSecurityAudit></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|<span data-ttu-id="5a810-147">서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-147">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[<span data-ttu-id="5a810-148">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="5a810-148">\<serviceThrottling></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|<span data-ttu-id="5a810-149">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스의 스로틀 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-149">Specifies the throttling mechanism of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span>|  
|[<span data-ttu-id="5a810-150">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="5a810-150">\<serviceTimeouts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|<span data-ttu-id="5a810-151">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-151">Specifies the timeout for a service.</span></span>|  
|[<span data-ttu-id="5a810-152">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="5a810-152">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="5a810-153">워크플로 기반 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하기 위해 WorkflowRuntime의 인스턴스에 대한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-153">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span>|  
|[<span data-ttu-id="5a810-154">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="5a810-154">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="5a810-155">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-155">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a810-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5a810-156">Parent Elements</span></span>  
  
|<span data-ttu-id="5a810-157">요소</span><span class="sxs-lookup"><span data-stu-id="5a810-157">Element</span></span>|<span data-ttu-id="5a810-158">설명</span><span class="sxs-lookup"><span data-stu-id="5a810-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a810-159">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5a810-159">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="5a810-160">서비스 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5a810-160">A collection of service behavior elements.</span></span>|
