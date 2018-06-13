---
title: '방법: 클라이언트 자격 증명 값 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 9625400b855492ead12a5a2f1fa74f10164f6cdd
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806651"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="d24b5-102">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="d24b5-102">How to: Specify Client Credential Values</span></span>
<span data-ttu-id="d24b5-103">Windows Communication Foundation (WCF)를 사용 하 여 서비스 클라이언트가 서비스에 인증 하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-103">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="d24b5-104">예를 들면 서비스는 클라이언트가 인증서를 사용하여 인증하도록 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>  
  
### <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="d24b5-105">클라이언트 자격 증명 형식을 결정하려면</span><span class="sxs-lookup"><span data-stu-id="d24b5-105">To determine the client credential type</span></span>  
  
1.  <span data-ttu-id="d24b5-106">서비스의 메타데이터 끝점에서 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="d24b5-107">메타데이터는 보통 사용자가 선택한 프로그래밍 언어로 된 클라이언트 코드(기본적으로 Visual C#)와 XML 구성 파일의 두 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="d24b5-108">메타데이터를 검색하는 방법 중 하나는 Svcutil.exe 도구를 사용해 클라이언트 코드와 클라이언트 구성을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="d24b5-109">자세한 내용은 참조 [메타 데이터 가져오기](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) 및 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-109">For more information, see [Retrieving Metadata](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
2.  <span data-ttu-id="d24b5-110">XML 구성 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-110">Open the XML configuration file.</span></span> <span data-ttu-id="d24b5-111">Svcutil.exe 도구를 사용하는 경우 이 파일의 기본 이름은 Output.config입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>  
  
3.  <span data-ttu-id="d24b5-112">찾을  **\<보안 >** 인 요소는 **모드** 특성 (**< 보안 모드 =** `MessageOrTransport` **>** 여기서 `MessageOrTransport` 보안 모드 중 하나로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-112">Find the **\<security>** element with the **mode** attribute (**<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>  
  
4.  <span data-ttu-id="d24b5-113">모드 값과 일치하는 자식 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="d24b5-114">예를 들어,는 모드가 설정 되어 있으면 **메시지**, 찾을  **\<메시지 >** 에 포함 된 요소는  **\<보안 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>  
  
5.  <span data-ttu-id="d24b5-115">에 할당 된 값을 확인는 **clientCredentialType** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="d24b5-116">실제 값은 사용하는 모드(Transport/Message)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-116">The actual value depends on which mode is used, transport or message.</span></span>  
  
 <span data-ttu-id="d24b5-117">다음 XML 코드는 메시지 보안을 사용하며 인증서를 사용해 클라이언트를 인증하도록 하는 클라이언트의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="d24b5-118">예제: 인증서를 클라이언트 자격 증명으로 사용하는 TCP Transport 모드</span><span class="sxs-lookup"><span data-stu-id="d24b5-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>  
 <span data-ttu-id="d24b5-119">이 예제에서는 보안 모드를 Transport 모드로 설정하고 클라이언트 자격 증명 값을 X.509 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="d24b5-120">다음 절차에서는 코드와 구성에 클라이언트에 대한 클라이언트 자격 증명 값을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="d24b5-121">이 사용 했다고 가정는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스에서 메타 데이터가 (코드 및 구성)를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="d24b5-122">자세한 내용은 참조 [하는 방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-122">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="d24b5-123">코드에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="d24b5-123">To specify the client credential value on the client in code</span></span>  
  
1.  <span data-ttu-id="d24b5-124">사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 서비스에서 코드 및 구성을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>  
  
2.  <span data-ttu-id="d24b5-125">생성된 된 코드를 사용 하 여 WCF 클라이언트의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-125">Create an instance of the WCF client using the generated code.</span></span>  
  
3.  <span data-ttu-id="d24b5-126">클라이언트 클래스에서 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="d24b5-127">이 예제에서는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 클래스의 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> 메서드를 사용하여 속성을 X.509 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <span data-ttu-id="d24b5-128"><xref:System.Security.Cryptography.X509Certificates.X509FindType> 클래스의 열거를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="d24b5-129">주체 이름은 만료 날짜로 인해 인증서가 변경된 경우 여기서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="d24b5-130">주체 이름을 사용하면 인프라에서 인증서를 다시 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="d24b5-131">구성에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="d24b5-131">To specify the client credential value on the client in configuration</span></span>  
  
1.  <span data-ttu-id="d24b5-132">추가 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소는 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-132">Add a [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
2.  <span data-ttu-id="d24b5-133">추가 [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소는 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-133">Add a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="d24b5-134">필수 `name` 특성을 적절한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="d24b5-135">추가 [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) 요소는 [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-135">Add a [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
4.  <span data-ttu-id="d24b5-136">다음 코드에서처럼 `storeLocation`, `storeName`, `x509FindType` 및 `findValue` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="d24b5-137">자세한 내용은 [인증서 작업](../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d24b5-137">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  <span data-ttu-id="d24b5-138">클라이언트를 구성할 때 다음 코드에서처럼 `behaviorConfiguration` 요소의 `<endpoint>` 특성을 설정하여 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="d24b5-139">자식인 끝점 요소는 [ \<클라이언트 >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-139">The endpoint element is a child of the [\<client>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="d24b5-140">또한 `bindingConfiguration` 특성을 클라이언트에 대한 바인딩으로 설정하여 바인딩 구성 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="d24b5-141">생성된 구성 파일을 사용하는 경우 바인딩의 이름이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="d24b5-142">이 예제에서 이름은 `"tcpBindingWithCredential"`입니다.</span><span class="sxs-lookup"><span data-stu-id="d24b5-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d24b5-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d24b5-143">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="d24b5-144">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d24b5-144">Programming WCF Security</span></span>](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [<span data-ttu-id="d24b5-145">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="d24b5-145">Selecting a Credential Type</span></span>](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="d24b5-146">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="d24b5-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="d24b5-147">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="d24b5-147">Working with Certificates</span></span>](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="d24b5-148">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="d24b5-148">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="d24b5-149">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d24b5-149">\<netTcpBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [<span data-ttu-id="d24b5-150">\<security></span><span class="sxs-lookup"><span data-stu-id="d24b5-150">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [<span data-ttu-id="d24b5-151">\<message></span><span class="sxs-lookup"><span data-stu-id="d24b5-151">\<message></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [<span data-ttu-id="d24b5-152">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d24b5-152">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [<span data-ttu-id="d24b5-153">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d24b5-153">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [<span data-ttu-id="d24b5-154">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="d24b5-154">\<clientCertificate></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [<span data-ttu-id="d24b5-155">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d24b5-155">\<clientCredentials></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
