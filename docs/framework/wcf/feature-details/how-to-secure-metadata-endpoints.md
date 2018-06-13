---
title: '방법: 메타데이터 끝점 보안 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 659291975902ec78c1484ac77f898b4486000e8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497180"
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="a18d2-102">방법: 메타데이터 끝점 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a18d2-102">How to: Secure Metadata Endpoints</span></span>
<span data-ttu-id="a18d2-103">서비스의 메타데이터에는 악의적인 사용자가 활용할 수 있는 응용 프로그램에 대한 중요한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="a18d2-104">또한 서비스의 소비자는 서비스의 메타데이터를 가져오기 위한 보안 메커니즘이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="a18d2-105">따라서 보안 끝점을 사용하여 메타데이터를 게시해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>  
  
 <span data-ttu-id="a18d2-106">메타 데이터 끝점은 일반적으로 응용 프로그램 끝점을 보호 하기 위한 Windows Communication Foundation (WCF)에 정의 된 표준 보안 메커니즘을 사용 하 여 보안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-106">Metadata endpoints are generally secured using the standard security mechanisms defined in Windows Communication Foundation (WCF) for securing application endpoints.</span></span> <span data-ttu-id="a18d2-107">(자세한 내용은 참조 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="a18d2-107">(For more information, see [Security Overview](../../../../docs/framework/wcf/feature-details/security-overview.md).)</span></span>  
  
 <span data-ttu-id="a18d2-108">이 항목에서는 SSL(Secure Sockets Layer) 인증서 즉, HTTPS 끝점으로 보안되는 끝점을 만드는 방법에 대해 단계별로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>  
  
### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="a18d2-109">코드에 보안 HTTPS GET 메타데이터 끝점을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a18d2-109">To create a secure HTTPS GET metadata endpoint in code</span></span>  
  
1.  <span data-ttu-id="a18d2-110">적절한 X.509 인증서를 사용하여 포트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="a18d2-111">인증서는 신뢰할 수 있는 기관에서 가져와야 하며 "서비스 인증"의 용도로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="a18d2-112">HttpCfg.exe 도구를 사용하여 인증서를 포트에 첨부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="a18d2-113">참조 [하는 방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-113">See [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a18d2-114">인증서의 주체 또는 인증서의 DNS(Domain Name System)는 컴퓨터의 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="a18d2-115">이는 HTTPS 메커니즘에서 수행하는 첫 번째 단계 중 하나로서 인증서가 호출된 주소와 동일한 URI(Uniform Resource Identifier)에 발급되었는지 확인하는 단계이므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>  
  
2.  <span data-ttu-id="a18d2-116"><xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>  
  
3.  <span data-ttu-id="a18d2-117"><xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 클래스의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>  
  
4.  <span data-ttu-id="a18d2-118"><xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> 속성을 적절한 URL로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="a18d2-119">절대 주소를 지정하는 경우 URL은 "https://" 스키마로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-119">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="a18d2-120">상대 주소를 지정하는 경우 서비스 호스트의 HTTPS 기본 주소를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="a18d2-121">이 속성을 설정하지 않으면 기본 주소는 ""이거나 바로 서비스의 HTTPS 기본 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>  
  
5.  <span data-ttu-id="a18d2-122">다음 코드에서처럼 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 클래스의 <xref:System.ServiceModel.Description.ServiceDescription> 속성이 반환하는 동작 컬렉션에 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
     [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]  
  
### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="a18d2-123">구성에 보안 HTTPS GET 메타데이터 끝점을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a18d2-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>  
  
1.  <span data-ttu-id="a18d2-124">추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소는 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 서비스에 대 한 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-124">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>  
  
2.  <span data-ttu-id="a18d2-125">추가 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 요소는 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-125">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="a18d2-126">추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소는 `<serviceBehaviors>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-126">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>  
  
4.  <span data-ttu-id="a18d2-127">`name` 요소의 `<behavior>` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="a18d2-128">`name` 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-128">The `name` attribute is required.</span></span> <span data-ttu-id="a18d2-129">아래 예제에서는 `mySvcBehavior` 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-129">The example below uses the value `mySvcBehavior`.</span></span>  
  
5.  <span data-ttu-id="a18d2-130">추가 [ \<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) 에 `<behavior>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-130">Add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>  
  
6.  <span data-ttu-id="a18d2-131">`httpsGetEnabled` 요소의 `<serviceMetadata>` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>  
  
7.  <span data-ttu-id="a18d2-132">`httpsGetUrl` 요소의 `<serviceMetadata>` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="a18d2-133">절대 주소를 지정하는 경우 URL은 "https://" 스키마로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-133">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="a18d2-134">상대 주소를 지정하는 경우 서비스 호스트의 HTTPS 기본 주소를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="a18d2-135">이 속성을 설정하지 않으면 기본 주소는 ""이거나 바로 서비스의 HTTPS 기본 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>  
  
8.  <span data-ttu-id="a18d2-136">서비스와 동작을 사용 하도록 설정는 `behaviorConfiguration` 특성에는 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) 요소 동작 요소의 name 특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="a18d2-137">다음 구성 코드에서는 자세한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-137">The following configuration code shows a complete example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="mySvcBehavior">  
         <serviceMetadata httpsGetEnabled="true"   
              httpsGetUrl="https://localhost:8036/calcMetadata" />  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
     <services>  
      <service behaviorConfiguration="mySvcBehavior"   
            name="Microsoft.Security.Samples.Calculator">  
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"  
       binding="wsHttpBinding" bindingConfiguration=""     
       contract="Microsoft.Security.Samples.ICalculator" />  
      </service>  
     </services>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="a18d2-138">예제</span><span class="sxs-lookup"><span data-stu-id="a18d2-138">Example</span></span>  
 <span data-ttu-id="a18d2-139">다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들고 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="a18d2-140">그런 다음 코드는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 인스턴스를 만들고, 속성을 설정하여 보안 메타데이터 교환 지점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>  
  
 [!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
 [!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a18d2-141">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a18d2-141">Compiling the Code</span></span>  
 <span data-ttu-id="a18d2-142">코드 예제에서는 다음 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a18d2-142">The code example uses the following namespaces:</span></span>  
  
-   <xref:System.ServiceModel?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Description?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="a18d2-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a18d2-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>  
 [<span data-ttu-id="a18d2-144">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="a18d2-144">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="a18d2-145">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="a18d2-145">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a18d2-146">메타데이터 관련 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="a18d2-146">Security Considerations with Metadata</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)  
 [<span data-ttu-id="a18d2-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a18d2-147">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
