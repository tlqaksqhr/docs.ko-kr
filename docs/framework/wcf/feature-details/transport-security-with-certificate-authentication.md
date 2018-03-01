---
title: "인증서 인증을 사용하는 전송 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 632d4cc19c19342363228a1e86b1ba6445d14ac9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="bb7a4-102">인증서 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="bb7a4-102">Transport Security with Certificate Authentication</span></span>
<span data-ttu-id="bb7a4-103">이 항목에서는 전송 보안을 사용할 때 서버 및 클라이언트 인증에 X.509 인증서를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-103">This topic discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="bb7a4-104">인증서 참조 X.509에 대 한 자세한 내용은 [X.509 공개 키 인증서](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-104">For more information about X.509 certificates see [X.509 Public Key Certificates](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx).</span></span> <span data-ttu-id="bb7a4-105">인증서는 인증서의 타사 발급자 자주 변경 되는 인증 기관에서 발급 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="bb7a4-106">Windows Server 도메인의 경우 Active Directory 인증서 서비스를 사용하여 도메인에서 클라이언트 컴퓨터에 인증서를 발급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="bb7a4-107">자세한 내용은 참조 [Windows 2008 R2 인증서 서비스](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-107">For more information see [Windows 2008 R2 Certificate Services](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span></span> <span data-ttu-id="bb7a4-108">이 시나리오에서는 SSL(Secure Sockets Layer)을 사용하여 구성된 IIS(인터넷 정보 서비스)에서 서비스가 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-108">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="bb7a4-109">서비스는 클라이언트에서 서버의 ID를 확인할 수 있도록 SSL(X.509) 인증서를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-109">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="bb7a4-110">클라이언트도 서비스에서 클라이언트의 ID를 확인할 수 있는 X.509 인증서를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-110">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="bb7a4-111">서버 인증서는 클라이언트에 의해 신뢰되어야 하며 클라이언트 인증서는 서버에 의해 신뢰되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-111">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="bb7a4-112">서비스와 클라이언트가 서로 ID를 확인하는 방법의 실제 메커니즘은 이 항목에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-112">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this topic.</span></span> <span data-ttu-id="bb7a4-113">자세한 내용은 참조 [Wikipedia에서 디지털 서명을](http://go.microsoft.com/fwlink/?LinkId=253157)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-113">For more information see [Digital Signature on Wikipedia](http://go.microsoft.com/fwlink/?LinkId=253157).</span></span>  
  
 <span data-ttu-id="bb7a4-114">이 시나리오에서는 다음 다이어그램에서 보여 주는 것처럼 요청/회신 메시지 패턴을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-114">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="bb7a4-115">![인증서를 사용 하 여 전송을 보안](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="bb7a4-115">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="bb7a4-116">참조 된 서비스에서 인증서를 사용 하 여 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) 및 [하는 방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-116"> using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="bb7a4-117">다음 표에서는 시나리오의 다양한 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-117">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="bb7a4-118">특성</span><span class="sxs-lookup"><span data-stu-id="bb7a4-118">Characteristic</span></span>|<span data-ttu-id="bb7a4-119">설명</span><span class="sxs-lookup"><span data-stu-id="bb7a4-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bb7a4-120">보안 모드</span><span class="sxs-lookup"><span data-stu-id="bb7a4-120">Security Mode</span></span>|<span data-ttu-id="bb7a4-121">전송</span><span class="sxs-lookup"><span data-stu-id="bb7a4-121">Transport</span></span>|  
|<span data-ttu-id="bb7a4-122">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="bb7a4-122">Interoperability</span></span>|<span data-ttu-id="bb7a4-123">기존 웹 서비스 클라이언트 및 서비스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-123">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="bb7a4-124">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="bb7a4-124">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="bb7a4-125">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="bb7a4-125">Authentication (Client)</span></span>|<span data-ttu-id="bb7a4-126">예(SSL 인증서 사용)</span><span class="sxs-lookup"><span data-stu-id="bb7a4-126">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="bb7a4-127">예(X.509 인증서 사용)</span><span class="sxs-lookup"><span data-stu-id="bb7a4-127">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="bb7a4-128">데이터 무결성</span><span class="sxs-lookup"><span data-stu-id="bb7a4-128">Data Integrity</span></span>|<span data-ttu-id="bb7a4-129">예</span><span class="sxs-lookup"><span data-stu-id="bb7a4-129">Yes</span></span>|  
|<span data-ttu-id="bb7a4-130">데이터 기밀성</span><span class="sxs-lookup"><span data-stu-id="bb7a4-130">Data Confidentiality</span></span>|<span data-ttu-id="bb7a4-131">예</span><span class="sxs-lookup"><span data-stu-id="bb7a4-131">Yes</span></span>|  
|<span data-ttu-id="bb7a4-132">전송</span><span class="sxs-lookup"><span data-stu-id="bb7a4-132">Transport</span></span>|<span data-ttu-id="bb7a4-133">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bb7a4-133">HTTPS</span></span>|  
|<span data-ttu-id="bb7a4-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="bb7a4-134">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="bb7a4-135">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="bb7a4-135">Configure the Service</span></span>  
 <span data-ttu-id="bb7a4-136">이 시나리오에서는 서비스가 IIS에서 호스팅되므로 web.config 파일을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-136">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="bb7a4-137">다음 web.config에서는 전송 보안 및 X.509 클라이언트 자격 증명을 사용하도록 <xref:System.ServiceModel.WSHttpBinding>을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-137">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>              
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>            
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="bb7a4-138">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="bb7a4-138">Configure the Client</span></span>  
 <span data-ttu-id="bb7a4-139">클라이언트는 코드 또는 app.config 파일에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-139">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="bb7a4-140">다음 예제에서는 클라이언트를 코드에 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-140">The following example shows how to configure the client in code.</span></span>  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="bb7a4-141">또는 다음 예제와 같이 클라이언트를 App.config 파일에 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb7a4-141">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "   
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb7a4-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb7a4-142">See Also</span></span>  
 [<span data-ttu-id="bb7a4-143">보안 개요</span><span class="sxs-lookup"><span data-stu-id="bb7a4-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="bb7a4-144">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="bb7a4-144">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
