---
title: '&lt;netHttpBinding&gt;의 &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 6e4cd2c000d577e26b54e09f24279e0fd74afcf1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagegt-of-ltnethttpbindinggt"></a><span data-ttu-id="95c3f-102">&lt;netHttpBinding&gt;의 &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="95c3f-102">&lt;message&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="95c3f-103">메시지 수준 보안 설정을 정의 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="95c3f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="95c3f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="95c3f-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="95c3f-105">\<bindings></span></span>  
<span data-ttu-id="95c3f-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="95c3f-106">\<netHttpBinding></span></span>  
<span data-ttu-id="95c3f-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="95c3f-107">\<binding></span></span>  
<span data-ttu-id="95c3f-108">\<security></span><span class="sxs-lookup"><span data-stu-id="95c3f-108">\<security></span></span>  
<span data-ttu-id="95c3f-109">\<message></span><span class="sxs-lookup"><span data-stu-id="95c3f-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c3f-110">구문</span><span class="sxs-lookup"><span data-stu-id="95c3f-110">Syntax</span></span>  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95c3f-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="95c3f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="95c3f-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95c3f-113">특성</span><span class="sxs-lookup"><span data-stu-id="95c3f-113">Attributes</span></span>  
  
|<span data-ttu-id="95c3f-114">특성</span><span class="sxs-lookup"><span data-stu-id="95c3f-114">Attribute</span></span>|<span data-ttu-id="95c3f-115">설명</span><span class="sxs-lookup"><span data-stu-id="95c3f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95c3f-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="95c3f-116">algorithmSuite</span></span>|<span data-ttu-id="95c3f-117">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="95c3f-118">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식이며 알고리즘 및 키 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="95c3f-119">이러한 알고리즘은 WS-SecurityPolicy(Security Policy Language) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="95c3f-120">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="95c3f-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="95c3f-121">clientCredentialType</span></span>|<span data-ttu-id="95c3f-122">메시지 기반 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="95c3f-123">기본값은 `UserName`입니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="95c3f-124">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="95c3f-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="95c3f-125">값</span><span class="sxs-lookup"><span data-stu-id="95c3f-125">Value</span></span>|<span data-ttu-id="95c3f-126">설명</span><span class="sxs-lookup"><span data-stu-id="95c3f-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95c3f-127">UserName</span><span class="sxs-lookup"><span data-stu-id="95c3f-127">UserName</span></span>|<span data-ttu-id="95c3f-128">-UserName 자격 증명으로 서버에 클라이언트를 인증 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="95c3f-129">이 자격 증명은 <`clientCredentials`> 요소를 사용하여 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-129">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="95c3f-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 암호 다이제스트를 보내거나 암호를 사용 하 고 메시지 보안에 이러한 키를 사용 하 여 키를 파생 하는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="95c3f-131">따라서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 UserName 자격 증명을 사용할 때 전송에 보안을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-131">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="95c3f-132">`basicHttpBinding`의 경우 SSL 채널을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="95c3f-133">인증서</span><span class="sxs-lookup"><span data-stu-id="95c3f-133">Certificate</span></span>|<span data-ttu-id="95c3f-134">클라이언트가 인증서를 사용하여 서버의 인증을 받도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="95c3f-135">이 경우 <`clientCredentials`> 및 <`clientCertificate`>를 사용하여 클라이언트 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-135">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="95c3f-136">또한 메시지 보안 모드를 사용하는 경우 서비스 인증서를 사용하여 클라이언트를 구축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="95c3f-137">서비스 자격 증명을이 예에서 사용 하 여 지정 해야 <xref:System.ServiceModel.Description.ClientCredentials> 클래스 또는 `ClientCredentials` 동작 요소는 서비스를 지정 하 고 인증서를 사용 하는 \<serviceCertificate > serviceCredentials의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95c3f-138">자식 요소</span><span class="sxs-lookup"><span data-stu-id="95c3f-138">Child Elements</span></span>  
 <span data-ttu-id="95c3f-139">없음</span><span class="sxs-lookup"><span data-stu-id="95c3f-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95c3f-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="95c3f-140">Parent Elements</span></span>  
  
|<span data-ttu-id="95c3f-141">요소</span><span class="sxs-lookup"><span data-stu-id="95c3f-141">Element</span></span>|<span data-ttu-id="95c3f-142">설명</span><span class="sxs-lookup"><span data-stu-id="95c3f-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95c3f-143"><`security`> 요소의 <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="95c3f-143"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="95c3f-144"><`netHttpBinding`> 요소의 보안 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-144">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95c3f-145">예제</span><span class="sxs-lookup"><span data-stu-id="95c3f-145">Example</span></span>  
 <span data-ttu-id="95c3f-146">이 샘플에서는 basicHttpBinding 및 메시지 보안을 사용하는 응용 프로그램을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="95c3f-147">다음 서비스 구성 예제에서 끝점 정의는 basicHttpBinding을 지정하고 `Binding1`이라는 바인딩 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="95c3f-148">서비스가 클라이언트에게 자신을 인증하는 데 사용하는 인증서는 구성 파일의 `behaviors` 섹션에 있는 `serviceCredentials` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="95c3f-149">클라이언트가 서비스에 자신을 인증하는 데 사용하는 인증서에 적용되는 유효성 검사 모드 또한 `behaviors` 섹션에서 `clientCertificate` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="95c3f-150">동일한 바인딩 및 보안 세부 정보가 클라이언트 구성 파일에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c3f-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <basicHttpBinding>  
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95c3f-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95c3f-151">See Also</span></span>  
 [<span data-ttu-id="95c3f-152">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="95c3f-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="95c3f-153">바인딩</span><span class="sxs-lookup"><span data-stu-id="95c3f-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="95c3f-154">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="95c3f-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="95c3f-155">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="95c3f-155">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="95c3f-156">\<binding></span><span class="sxs-lookup"><span data-stu-id="95c3f-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
