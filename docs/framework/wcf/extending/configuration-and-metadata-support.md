---
title: "구성 및 메타데이터 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d22beac94d6055350961f62e43071b54a4916f04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-and-metadata-support"></a><span data-ttu-id="06417-102">구성 및 메타데이터 지원</span><span class="sxs-lookup"><span data-stu-id="06417-102">Configuration and Metadata Support</span></span>
<span data-ttu-id="06417-103">이 항목에서는 바인딩 및 바인딩 요소에 대한 구성 및 메타데이터 지원을 사용하도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-103">This topic describes how to enable configuration and metadata support for bindings and binding elements.</span></span>  
  
## <a name="overview-of-configuration-and-metadata"></a><span data-ttu-id="06417-104">구성 및 메타데이터 개요</span><span class="sxs-lookup"><span data-stu-id="06417-104">Overview of Configuration and Metadata</span></span>  
 <span data-ttu-id="06417-105">이 항목에서는 다음과 같은 작업을 1, 2 및 4 옵션 항목 설명에 [개발 채널](../../../../docs/framework/wcf/extending/developing-channels.md) 작업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-105">This topic discusses the following tasks, which are optional items 1, 2, and 4 in the [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md) task list.</span></span>  
  
-   <span data-ttu-id="06417-106">바인딩 요소에 대해 구성 파일 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-106">Enabling configuration file support for a binding element.</span></span>  
  
-   <span data-ttu-id="06417-107">바인딩에 대해 구성 파일 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-107">Enabling configuration file support for a binding.</span></span>  
  
-   <span data-ttu-id="06417-108">바인딩 요소에 대해 WSDL 및 정책 어설션을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="06417-108">Exporting WSDL and policy assertions for a binding element.</span></span>  
  
-   <span data-ttu-id="06417-109">바인딩 또는 바인딩 요소를 삽입하고 구성하기 위해 WSDL 및 정책 어설션을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-109">Identifying WSDL and policy assertions to insert and configure your binding or binding element.</span></span>  
  
 <span data-ttu-id="06417-110">사용자 정의 바인딩 및 바인딩 요소를 만드는 방법은 참조 [Creating User-Defined 바인딩](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) 및 [BindingElement 만들기](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md)각각.</span><span class="sxs-lookup"><span data-stu-id="06417-110">For information about creating user-defined bindings and binding elements, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) and [Creating a BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), respectively.</span></span>  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="06417-111">구성 지원 추가</span><span class="sxs-lookup"><span data-stu-id="06417-111">Adding Configuration Support</span></span>  
 <span data-ttu-id="06417-112">채널에 대해 구성 파일 지원을 사용하도록 설정하려면 두 개의 구성 섹션, 즉, 바인딩 요소에 대해 구성 지원을 사용하도록 설정하는 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>와 바인딩에 대해 구성 지원을 사용하도록 설정하는 <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> 및 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-112">To enable configuration file support for a channel, you must implement two configuration sections, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, which enables configuration support for binding elements, and the <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> and <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, which enable configuration support for bindings.</span></span>  
  
 <span data-ttu-id="06417-113">이 작업을 수행 하는 편리한 방법을 사용 하는 것은 [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) 샘플 도구 바인딩 및 바인딩 요소에 대 한 구성 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-113">An easier way to do this is to use the [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) sample tool to generate configuration code for your bindings and binding elements.</span></span>  
  
### <a name="extending-bindingelementextensionelement"></a><span data-ttu-id="06417-114">BindingElementExtensionElement 확장명</span><span class="sxs-lookup"><span data-stu-id="06417-114">Extending BindingElementExtensionElement</span></span>  
 <span data-ttu-id="06417-115">다음 예제 코드에서 가져온 것은 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="06417-115">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="06417-116">`UdpTransportElement`는 구성 시스템에 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>를 노출하는 `UdpTransportBindingElement`입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-116">The `UdpTransportElement` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="06417-117">샘플에서는 몇 가지 기본 재정의를 통해 구성 섹션 이름, 바인딩 요소의 형식 및 바인딩 요소를 만드는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-117">With a few basic overrides, the sample defines the configuration section name, the type of the binding element and how to create the binding element.</span></span> <span data-ttu-id="06417-118">그러면 사용자는 다음과 같이 구성 파일에서 확장 섹션을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06417-118">Users can then register the extension section in a configuration file as follows.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="06417-119">사용자 지정 바인딩에서는 UDP를 전송으로 사용하기 위해 확장을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06417-119">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="adding-configuration-for-a-binding"></a><span data-ttu-id="06417-120">바인딩에 대해 구성 추가</span><span class="sxs-lookup"><span data-stu-id="06417-120">Adding Configuration for a Binding</span></span>  
 <span data-ttu-id="06417-121">`SampleProfileUdpBindingCollectionElement` 섹션은 구성 시스템에 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>을 노출하는 `SampleProfileUdpBinding`입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-121">The section `SampleProfileUdpBindingCollectionElement` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="06417-122">대량의 구현은 `SampleProfileUdpBindingConfigurationElement`로부터 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="06417-122">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="06417-123">`SampleProfileUdpBindingConfigurationElement` 에 속성에 해당 하는 속성이 `SampleProfileUdpBinding`, 및 매핑하는 함수가 `ConfigurationElement` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="06417-123">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="06417-124">마지막으로 `OnApplyConfiguration` 메서드는 다음 샘플 코드에서처럼 `SampleProfileUdpBinding`에서 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="06417-124">Finally, the `OnApplyConfiguration` method is overridden in the `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```  
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,  
                    "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",  
                    typeof(SampleProfileUdpBinding).AssemblyQualifiedName,  
                    binding.GetType().AssemblyQualifiedName));  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 <span data-ttu-id="06417-125">구성 시스템을 사용하여 이 처리기를 등록하려면 관련 구성 파일에 다음 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-125">To register this handler with the configuration system, add the following section to the relevant configuration file.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="06417-126">다음에서 참조할 수는 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-126">It can then be referenced from the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) configuration section.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"   
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"   
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="adding-metadata-support-for-a-binding-element"></a><span data-ttu-id="06417-127">바인딩 요소에 대해 메타데이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="06417-127">Adding Metadata Support for a Binding Element</span></span>  
 <span data-ttu-id="06417-128">채널을 메타데이터 시스템으로 통합하려면 채널이 정책 가져오기와 내보내기를 모두 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-128">To integrate a channel into the metadata system, it must support both the import and export of policy.</span></span> <span data-ttu-id="06417-129">와 같은 도구를 통해이 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 의 바인딩 요소는 클라이언트를 생성 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-129">This allows tools such as [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate clients of the binding element.</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="06417-130">WSDL 지원 추가</span><span class="sxs-lookup"><span data-stu-id="06417-130">Adding WSDL Support</span></span>  
 <span data-ttu-id="06417-131">바인딩의 전송 바인딩 요소는 메타데이터에서 주소 지정 정보를 내보내고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06417-131">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="06417-132">또한 전송 바인딩 요소는 SOAP 바인딩을 사용할 때 메타데이터에서 올바른 전송 URI을 내보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-132">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span> <span data-ttu-id="06417-133">다음 예제 코드에서 가져온 것은 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="06417-133">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="06417-134">WSDL 내보내기</span><span class="sxs-lookup"><span data-stu-id="06417-134">WSDL Export</span></span>  
 <span data-ttu-id="06417-135">주소 지정 정보를 내보내려면는 `UdpTransportBindingElement` 구현 하는 <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-135">To export addressing information, the `UdpTransportBindingElement` implements the <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="06417-136"><xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> 메서드는 WSDL 포트에 올바른 주소 지정 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-136">The <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> method adds the correct addressing information to the WSDL port.</span></span>  
  
```  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="06417-137">끝점이 SOAP 바인딩을 사용할 때 `UdpTransportBindingElement` 메서드의 <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> 구현이 전송 URI도 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="06417-137">The `UdpTransportBindingElement` implementation of the <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> method also exports a transport URI when the endpoint uses a SOAP binding:</span></span>  
  
```  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="06417-138">WSDL 가져오기</span><span class="sxs-lookup"><span data-stu-id="06417-138">WSDL Import</span></span>  
 <span data-ttu-id="06417-139">주소 가져오기를 처리하기 위해 WSDL 가져오기 시스템을 확장하려면 Svcutil.exe.config 파일에서처럼 Svcutil.exe에 대한 구성 파일에 다음 구성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-139">To extend the WSDL import system to handle importing the addresses, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="06417-140">Svcutil.exe를 실행하는 경우 Svcutil.exe에서 WSDL 가져오기 확장을 로드하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06417-140">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1.  <span data-ttu-id="06417-141">Svcutil.exe는 /SvcutilConfig을 사용 하 여 구성 파일에:\<파일 > 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-141">Point Svcutil.exe to the configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2.  <span data-ttu-id="06417-142">Svcutil.exe와 동일한 디렉터리에 있는 Svcutil.exe.config에 구성 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-142">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="06417-143">`UdpBindingElementImporter` 형식은 <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-143">The `UdpBindingElementImporter` type implements the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="06417-144">`ImportEndpoint` 메서드는 WSDL 포트로부터 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06417-144">The `ImportEndpoint` method imports the address from the WSDL port:</span></span>  
  
```  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="06417-145">정책 지원 추가</span><span class="sxs-lookup"><span data-stu-id="06417-145">Adding Policy Support</span></span>  
 <span data-ttu-id="06417-146">사용자 지정 바인딩 요소는 서비스 끝점이 해당 바인딩 요소의 기능을 표현하도록 WSDL 바인딩에서 정책 어설션을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06417-146">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span> <span data-ttu-id="06417-147">다음 예제 코드에서 가져온 것은 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="06417-147">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="06417-148">정책 내보내기</span><span class="sxs-lookup"><span data-stu-id="06417-148">Policy Export</span></span>  
 <span data-ttu-id="06417-149">`UdpTransportBindingElement` 구현 형식 '<xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 정책을 내보낼 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-149">The `UdpTransportBindingElement` type implements``<xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> to add support for exporting policy.</span></span> <span data-ttu-id="06417-150">그 결과, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>는 이를 포함하는 모든 바인딩에 대한 정책 생성에 `UdpTransportBindingElement`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-150">As a result, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="06417-151"><xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>에서는 채널이 멀티캐스트 모드인 경우 UDP용 어설션 및 다른 어설션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, add an assertion for UDP and another assertion if the channel is in multicast mode.</span></span> <span data-ttu-id="06417-152">이는 멀티캐스트 모드가 통신 스택의 구성 방법에 영향을 주므로 양쪽 모두에서 조정되어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-152">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="06417-153">사용자 지정 전송 바인딩 요소가 주소 지정을 처리하기 때문에 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>에서의 `UdpTransportBindingElement` 구현 역시 사용 중인 WS-Addressing의 버전을 나타내기 위해 적절한 WS-Addressing 정책 어설션 내보내기를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-153">Because custom transport binding elements are responsible for handling addressing, the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="06417-154">정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="06417-154">Policy Import</span></span>  
 <span data-ttu-id="06417-155">정책 가져오기 시스템을 확장하려면 Svcutil.exe.config 파일에서처럼 Svcutil.exe에 대한 구성 파일에 다음 구성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-155">To extend the policy import system, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="06417-156">그런 다음 등록된 클래스(<xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>)로부터 `UdpBindingElementImporter`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-156">Then we implement <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="06417-157"><xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>에서는 적절한 네임스페이스에서 어설션을 검사하고, 어셜션 중 하나를 처리하여 전송을 생성하고 멀티캐스트인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine the assertions in the appropriate namespace and process the ones for generating the transport and checking if it is multicast.</span></span> <span data-ttu-id="06417-158">또한 가져오기가 바인딩 어설션 목록으로부터 처리하는 어설션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-158">In addition, remove the assertions that the importer handles from the list of binding assertions.</span></span> <span data-ttu-id="06417-159">다시 한 번 말하지만 Svcutil.exe를 실행할 때 통합하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06417-159">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1.  <span data-ttu-id="06417-160">Svcutil.exe를는 /SvcutilConfig을 사용 하 여 구성 파일:\<파일 > 합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-160">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2.  <span data-ttu-id="06417-161">Svcutil.exe와 동일한 디렉터리에 있는 Svcutil.exe.config에 구성 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-161">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="06417-162">사용자 지정 표준 바인딩 가져오기 추가</span><span class="sxs-lookup"><span data-stu-id="06417-162">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="06417-163">기본적으로 Svcutil.exe 및 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> 형식은 시스템 제공 바인딩을 인식하고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06417-163">Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> type, by default, recognize and import system-provided bindings.</span></span> <span data-ttu-id="06417-164">그렇지 않을 경우, 해당 바인딩을 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> 인스턴스로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06417-164">Otherwise, the binding gets imported as a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="06417-165">Svcutil.exe 및 <xref:System.ServiceModel.Description.WsdlImporter>를 사용하도록 설정하여 `SampleProfileUdpBinding`을 가져오기 위해 `UdpBindingElementImporter`가 사용자 지정 표준 바인딩 가져오기도 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="06417-165">To enable Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter> to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="06417-166">사용자 지정 표준 바인딩 가져오기를 구현는 `ImportEndpoint` 에서 메서드는 <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> 를 검사 하는 인터페이스는 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> 경우 것 생성 되었는지 특정 표준 바인딩에 의해 참조에 대 한 메타 데이터에서 가져온 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="06417-166">A custom standard binding importer implements the `ImportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface to examine the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance imported from metadata to see if it could have been generated by specific standard binding.</span></span>  
  
```  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="06417-167">일반적으로 사용자 지정 표준 바인딩 가져오기를 구현하면 가져온 바인딩 요소의 속성을 확인하여 표준 바인딩에 의해 설정될 수 있는 속성만 변경되고, 다른 모든 속성은 기본값인지를 확인하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="06417-167">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="06417-168">표준 바인딩 가져오기를 구현하기 위한 기본 전략은 표준 바인딩의 인스턴스를 만들고, 바인딩 요소의 속성을 표준 바인딩이 지원하는 표준 바인딩 인스턴스로 전파하고, 가져온 바인딩 요소를 표준 바인딩의 바인딩 요소와 비교하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06417-168">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>
