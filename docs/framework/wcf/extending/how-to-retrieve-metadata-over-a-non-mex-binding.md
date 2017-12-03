---
title: "방법: MEX가 아닌 바인딩을 통해 메타데이터 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1f2fe2b7634b57e424773c16023fb657f09f23a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="c9a0c-102">방법: MEX가 아닌 바인딩을 통해 메타데이터 검색</span><span class="sxs-lookup"><span data-stu-id="c9a0c-102">How to: Retrieve Metadata Over a non-MEX Binding</span></span>
<span data-ttu-id="c9a0c-103">이 항목에서는 MEX가 아닌 바인딩을 통해 MEX 끝점으로부터 메타데이터를 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-103">This topic describes how to retrieve metadata from a MEX endpoint over a non-MEX binding.</span></span> <span data-ttu-id="c9a0c-104">이 샘플의 코드 기반는 [메타 데이터 끝점을 보호 하는 사용자 지정](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-104">The code in this sample is based on the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample.</span></span>  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="c9a0c-105">MEX가 아닌 바인딩을 통해 메타데이터를 검색하려면</span><span class="sxs-lookup"><span data-stu-id="c9a0c-105">To retrieve metadata over a non-MEX binding</span></span>  
  
1.  <span data-ttu-id="c9a0c-106">MEX 끝점에서 사용하는 바인딩을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-106">Determine the binding used by the MEX endpoint.</span></span> <span data-ttu-id="c9a0c-107">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스의 경우, 서비스의 구성 파일에 액세스함으로써 MEX 바인딩을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-107">For [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services, you can determine the MEX binding by accessing the service's configuration file.</span></span> <span data-ttu-id="c9a0c-108">이 경우에는 MEX 바인딩이 다음 서비스 구성에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-108">In this case, the MEX binding is defined in the following service configuration.</span></span>  
  
    ```xml  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2.  <span data-ttu-id="c9a0c-109">클라이언트 구성 파일에서는 동일한 사용자 지정 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-109">In the client configuration file, configure the same custom binding.</span></span> <span data-ttu-id="c9a0c-110">여기서는 클라이언트가 MEX 끝점으로부터 메타데이터를 요청할 때 인증에 사용할 인증서를 서비스에 제공하기 위해 `clientCredentials` 동작도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-110">Here the client also defines a `clientCredentials` behavior to provide a certificate to use to authenticate to the service when requesting metadata from the MEX endpoint.</span></span> <span data-ttu-id="c9a0c-111">사용자 지정 바인딩을 통해 메타데이터를 요청하기 위해 Svcutil.exe를 사용할 경우 다음 코드와 같이 MEX 끝점 구성을 Svcutil.exe의 구성 파일(Svcutil.exe.config)에 추가해야 하며, 끝점 구성의 이름은 MEX 끝점 주소의 URI 체계와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-111">When using Svcutil.exe to request metadata over a custom binding, you should add the MEX endpoint configuration to the configuration file for Svcutil.exe (Svcutil.exe.config), and the name of the endpoint configuration should match the URI scheme of the address of the MEX endpoint, as shown in the following code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>    
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="c9a0c-112">`MetadataExchangeClient`를 만들고 `GetMetadata`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-112">Create a `MetadataExchangeClient` and call `GetMetadata`.</span></span> <span data-ttu-id="c9a0c-113">이 작업을 수행하려면 두 가지 방법을 사용할 수 있습니다. 사용자 지정 바인딩을 구성에서 지정할 수도 있고, 다음 예제와 같이 코드에서 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-113">There are two ways to do this: you can specify the custom binding in configuration, or you can specify the custom binding in code, as shown in the following example.</span></span>  
  
    ```  
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4.  <span data-ttu-id="c9a0c-114">다음 코드에 표시된 것처럼 `WsdlImporter`를 만들고 `ImportAllEndpoints`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-114">Create a `WsdlImporter` and call `ImportAllEndpoints`, as shown in the following code.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  <span data-ttu-id="c9a0c-115">이제 서비스 끝점의 컬렉션을 가지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-115">At this point, you have a collection of service endpoints.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c9a0c-116">참조 메타 데이터를 가져오는 [하는 방법: 서비스 끝점으로 메타 데이터 가져오기](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a0c-116"> importing metadata, see [How to: Import Metadata into Service Endpoints](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a0c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9a0c-117">See Also</span></span>  
 [<span data-ttu-id="c9a0c-118">메타 데이터</span><span class="sxs-lookup"><span data-stu-id="c9a0c-118">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
