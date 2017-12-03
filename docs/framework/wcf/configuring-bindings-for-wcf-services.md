---
title: "Windows Communication Foundation 서비스에 대한 바인딩 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92fc3886f81ee401cbd3de2fb6ef251e4c340394
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a><span data-ttu-id="de068-102">Windows Communication Foundation 서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="de068-102">Configuring Bindings for Windows Communication Foundation Services</span></span>
<span data-ttu-id="de068-103">응용 프로그램을 만들 때 응용 프로그램의 배포 후 관리자에게 결정을 맡겨야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-103">When creating an application, you often want to defer decisions to the administrator after the deployment of the application.</span></span> <span data-ttu-id="de068-104">예를 들어, 서비스 주소 또는 URI(Uniform Resource Identifier)가 무엇인지 미리 알 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-104">For example, there is often no way of knowing in advance what a service address, or Uniform Resource Identifier (URI), will be.</span></span> <span data-ttu-id="de068-105">주소를 하드 코딩하는 대신 관리자가 서비스를 작성한 후에 이를 수행하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-105">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="de068-106">이러한 유연성은 구성을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-106">This flexibility is accomplished through configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de068-107">사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 와 `/config` 스위치를 신속 하 게 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de068-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config` switch to quickly create configuration files.</span></span>  
  
## <a name="major-sections"></a><span data-ttu-id="de068-108">주요 섹션</span><span class="sxs-lookup"><span data-stu-id="de068-108">Major Sections</span></span>  
 <span data-ttu-id="de068-109">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 구성 체계에는 `serviceModel`, `bindings` 및 `services`의 세 가지 주요 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-109">The [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] configuration scheme includes the following three major sections (`serviceModel`, `bindings`, and `services`):</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a><span data-ttu-id="de068-110">ServiceModel Elements</span><span class="sxs-lookup"><span data-stu-id="de068-110">ServiceModel Elements</span></span>  
 <span data-ttu-id="de068-111">에 의해 제한 섹션을 사용할 수 있습니다는 `system.ServiceModel` 서비스 종류를 하나 이상의 끝점 뿐만 아니라 서비스에 대 한 설정을 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="de068-111">You can use the section bounded by the `system.ServiceModel` element to configure a service type with one or more endpoints, as well as settings for a service.</span></span> <span data-ttu-id="de068-112">각 끝점은 주소, 계약 및 바인딩과 함께 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-112">Each endpoint can then be configured with an address, a contract, and a binding.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="de068-113">끝점, 참조 [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-113"> endpoints, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="de068-114">끝점이 지정되지 않으면 런타임에서 기본 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-114">If no endpoints are specified, the runtime adds default endpoints.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="de068-115"> , [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) 및 [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="de068-115"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="de068-116">바인딩은 전송(HTTP, TCP, 파이프, 메시지 큐) 및 프로토콜(보안, 안전성, 트랜잭션 흐름)을 지정하며, 끝점이 외부와 통신하는 방법을 지정하는 각각의 바인딩 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-116">A binding specifies transports (HTTP, TCP, pipes, Message Queuing) and protocols (Security, Reliability, Transaction flows) and consists of binding elements, each of which specifies an aspect of how an endpoint communicates with the world.</span></span>  
  
 <span data-ttu-id="de068-117">예를 들어 지정 하는 [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소는 끝점에 대 한 HTTP를 전송으로 사용 하도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de068-117">For example, specifying the [\<basicHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element indicates to use HTTP as the transport for an endpoint.</span></span> <span data-ttu-id="de068-118">이 끝점을 사용하는 서비스가 열려 있는 경우 이 요소는 런타임에 끝점을 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-118">This is used to wire up the endpoint at run time when the service using this endpoint is opened.</span></span>  
  
 <span data-ttu-id="de068-119">바인딩에는 미리 정의된 바인딩 및 사용자 지정 바인딩의 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-119">There are two kinds of bindings: predefined and custom.</span></span> <span data-ttu-id="de068-120">미리 정의된 바인딩에는 일반적인 시나리오에서 사용되는 유용한 요소의 조합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-120">Predefined bindings contain useful combinations of elements that are used in common scenarios.</span></span> <span data-ttu-id="de068-121">미리 정의 된 바인딩 목록을 형식에 대해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 제공 참조 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-121">For a list of predefined binding types that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provides, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="de068-122">서비스 응용 프로그램에서 필요로 하는 올바른 기능의 조합을 가진 미리 정의된 바인딩 컬렉션이 없는 경우 사용자 지정 바인딩을 만들어 응용 프로그램의 요구 사항을 충족시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-122">If no predefined binding collection has the correct combination of features that a service application needs, you can construct custom bindings to meet the application's requirements.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="de068-123">사용자 지정 바인딩을 참조 [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-123"> custom bindings, see [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
 <span data-ttu-id="de068-124">다음 4개의 예제에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 설정하는 데 사용되는 가장 일반적인 바인딩 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de068-124">The following four examples illustrate the most common binding configurations used for setting up a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span>  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a><span data-ttu-id="de068-125">끝점을 지정하여 바인딩 형식 사용</span><span class="sxs-lookup"><span data-stu-id="de068-125">Specifying an Endpoint to Use a Binding Type</span></span>  
 <span data-ttu-id="de068-126">첫 번째 예제에서는 주소, 계약 및 바인딩으로 구성된 끝점을 지정하는 방법에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de068-126">The first example illustrates how to specify an endpoint configured with an address, a contract, and a binding.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
```  
  
 <span data-ttu-id="de068-127">이 예제에서 `name` 특성은 구성의 서비스 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de068-127">In this example, the `name` attribute indicates which service type the configuration is for.</span></span> <span data-ttu-id="de068-128">`HelloWorld` 계약을 사용하여 코드에 서비스를 만드는 경우 서비스는 예제 구성에 정의된 모든 끝점으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-128">When you create a service in your code with the `HelloWorld` contract, it is initialized with all of the endpoints defined in the example configuration.</span></span> <span data-ttu-id="de068-129">어셈블리에는 하나의 서비스 계약을 구현 하는 경우는 `name` 특성을 생략 하는 서비스 에서만 사용할 수 있는 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-129">If the assembly implements only one service contract, the `name` attribute can be omitted because the service uses the only available type.</span></span> <span data-ttu-id="de068-130">특성에는 `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null` 형식으로 된 문자열만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-130">The attribute takes a string, which must be in the format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>  
  
 <span data-ttu-id="de068-131">`address` 특성은 다른 끝점이 서비스와 통신하는 데 사용하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-131">The `address` attribute specifies the URI that other endpoints use to communicate to the service.</span></span> <span data-ttu-id="de068-132">URI는 절대 경로 또는 상대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-132">The URI can be either an absolute or relative path.</span></span> <span data-ttu-id="de068-133">상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-133">If a relative address is provided, the host is expected to provide a base address that is appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="de068-134">주소가 구성되지 않으면 해당 끝점의 주소를 기본 주소로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-134">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span>  
  
 <span data-ttu-id="de068-135">`contract` 특성은 이 끝점이 공개하는 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-135">The `contract` attribute specifies the contract this endpoint is exposing.</span></span> <span data-ttu-id="de068-136">서비스 구현 형식은 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-136">The service implementation type must implement the contract type.</span></span> <span data-ttu-id="de068-137">서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-137">If a service implementation implements a single contract type, then this property can be omitted.</span></span>  
  
 <span data-ttu-id="de068-138">`binding` 특성은 이 특정 끝점에 사용할 미리 정의된 바인딩 또는 사용자 지정 바인딩을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-138">The `binding` attribute selects a predefined or custom binding to use for this specific endpoint.</span></span> <span data-ttu-id="de068-139">바인딩을 명시적으로 선택하지 않는 끝점에서는 기본 바인딩 선택인 `BasicHttpBinding`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-139">An endpoint that does not explicitly select a binding uses the default binding selection, which is `BasicHttpBinding`.</span></span>  
  
#### <a name="modifying-a-predefined-binding"></a><span data-ttu-id="de068-140">미리 정의된 바인딩 수정</span><span class="sxs-lookup"><span data-stu-id="de068-140">Modifying a Predefined Binding</span></span>  
 <span data-ttu-id="de068-141">다음 예제에서는 미리 정의된 바인딩을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-141">In the following example, a predefined binding is modified.</span></span> <span data-ttu-id="de068-142">그런 다음 서비스에서 끝점을 구성하는 데 해당 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-142">It can then be used to configure any endpoint in the service.</span></span> <span data-ttu-id="de068-143">바인딩은 <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> 값을 1초로 설정하여 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-143">The binding is modified by setting the <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> value to 1 second.</span></span> <span data-ttu-id="de068-144">속성은 <xref:System.TimeSpan> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-144">Note that the property returns a <xref:System.TimeSpan> object.</span></span>  
  
 <span data-ttu-id="de068-145">이 변경된 바인딩은 바인딩 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-145">That altered binding is found in the bindings section.</span></span> <span data-ttu-id="de068-146">끝점을 만들 때 `binding` 요소에 있는 `endpoint` 특성을 설정하면 변경된 이 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-146">This altered binding can now be used when creating any endpoint by setting the `binding` attribute in the `endpoint` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de068-147">바인딩에 특정 이름을 지정하는 경우 서비스 끝점에 지정된 `bindingConfiguration`이 해당 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-147">If you give a particular name to the binding, the `bindingConfiguration` specified in the service endpoint must match with it.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a><span data-ttu-id="de068-148">서비스에 적용할 동작 구성</span><span class="sxs-lookup"><span data-stu-id="de068-148">Configuring a Behavior to Apply to a Service</span></span>  
 <span data-ttu-id="de068-149">다음 예제에서는 특정 동작이 서비스 형식에 맞게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-149">In the following example, a specific behavior is configured for the service type.</span></span> <span data-ttu-id="de068-150">`ServiceMetadataBehavior` 요소는 사용 하도록 설정 하는 데 사용 됩니다는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스를 쿼리하고 메타 데이터에서 서비스 설명 언어 WSDL (웹) 문서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-150">The `ServiceMetadataBehavior` element is used to enable the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to query the service and generate Web Services Description Language (WSDL) documents from the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de068-151">동작에 특정 이름을 지정하는 경우 서비스 또는 끝점 섹션에 지정된 `behaviorConfiguration`이 해당 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de068-151">If you give a particular name to the behavior, the `behaviorConfiguration` specified in the service or endpoint section must match it.</span></span>  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />  
       </endpoint>  
    </service>  
</services>  
```  
  
 <span data-ttu-id="de068-152">위의 구성을 사용하면 클라이언트가 “HelloWorld” 형식이 지정된 서비스를 호출하고 해당 메타데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-152">The preceding configuration enables a client to call and get the metadata of the "HelloWorld" typed service.</span></span>  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a><span data-ttu-id="de068-153">다른 바인딩 값을 사용하는 두 개의 끝점으로 서비스 지정</span><span class="sxs-lookup"><span data-stu-id="de068-153">Specifying a Service with Two Endpoints Using Different Binding Values</span></span>  
 <span data-ttu-id="de068-154">마지막 이 예제에서는 두 개의 끝점이 `HelloWorld` 서비스 형식에 맞게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="de068-154">In this last example, two endpoints are configured for the `HelloWorld` service type.</span></span> <span data-ttu-id="de068-155">각 끝점은 서로 다른 사용자 지정 사용 `bindingConfiguration` 동일한 바인딩 유형의 특성입니다 (수정 각는 `basicHttpBinding`).</span><span class="sxs-lookup"><span data-stu-id="de068-155">Each endpoint uses a different customized  `bindingConfiguration` attribute of the same binding type (each modifies the `basicHttpBinding`).</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout"  
    </endpoint>  
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure"  
     </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
 <span data-ttu-id="de068-156">다음 예제와 같이 `protocolMapping` 섹션을 추가하고 바인딩을 구성하면 기본 구성을 사용하여 같은 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de068-156">You can get the same behavior using the default configuration by adding a `protocolMapping` section and configuring the bindings as demonstrated in the following example.</span></span>  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de068-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de068-157">See Also</span></span>  
 [<span data-ttu-id="de068-158">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="de068-158">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="de068-159">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="de068-159">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="de068-160">끝점 만들기 개요</span><span class="sxs-lookup"><span data-stu-id="de068-160">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="de068-161">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="de068-161">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
