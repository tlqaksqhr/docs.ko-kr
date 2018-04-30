---
title: 익명 클라이언트를 사용하는 전송 보안
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 2b52a32db1f1ac02f9204198a4cda5d4cb157486
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="f3657-102">익명 클라이언트를 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="f3657-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="f3657-103">이 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 시나리오에서는 기밀성 및 무결성 확보를 위해 전송 보안(HTTPS)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-103">This [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="f3657-104">서버는 SSL(Secure Sockets Layer) 인증서로 인증되어야 하며 클라이언트는 서버의 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="f3657-105">클라이언트는 어떤 메커니즘으로도 인증되지 않는 익명 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="f3657-106">샘플 응용 프로그램에 대 한 참조 [WS 전송 보안](../../../../docs/framework/wcf/samples/ws-transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> <span data-ttu-id="f3657-107">전송 보안에 대 한 자세한 내용은 참조 [전송 보안 개요](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-107">For more information about transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 <span data-ttu-id="f3657-108">서비스에 인증서를 사용 하는 방법에 대 한 자세한 내용은 참조 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) 및 [하는 방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-108">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="f3657-109">![익명 클라이언트를 사용한 전송 보안을 사용 하 여](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="f3657-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="f3657-110">특성</span><span class="sxs-lookup"><span data-stu-id="f3657-110">Characteristic</span></span>|<span data-ttu-id="f3657-111">설명</span><span class="sxs-lookup"><span data-stu-id="f3657-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f3657-112">보안 모드</span><span class="sxs-lookup"><span data-stu-id="f3657-112">Security Mode</span></span>|<span data-ttu-id="f3657-113">전송</span><span class="sxs-lookup"><span data-stu-id="f3657-113">Transport</span></span>|  
|<span data-ttu-id="f3657-114">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f3657-114">Interoperability</span></span>|<span data-ttu-id="f3657-115">기존 웹 서비스 및 클라이언트와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f3657-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="f3657-116">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="f3657-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="f3657-117">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="f3657-117">Authentication (Client)</span></span>|<span data-ttu-id="f3657-118">예</span><span class="sxs-lookup"><span data-stu-id="f3657-118">Yes</span></span><br /><br /> <span data-ttu-id="f3657-119">응용 프로그램 수준([!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 지원 없음)</span><span class="sxs-lookup"><span data-stu-id="f3657-119">Application level (no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] support)</span></span>|  
|<span data-ttu-id="f3657-120">무결성</span><span class="sxs-lookup"><span data-stu-id="f3657-120">Integrity</span></span>|<span data-ttu-id="f3657-121">예</span><span class="sxs-lookup"><span data-stu-id="f3657-121">Yes</span></span>|  
|<span data-ttu-id="f3657-122">기밀성</span><span class="sxs-lookup"><span data-stu-id="f3657-122">Confidentiality</span></span>|<span data-ttu-id="f3657-123">예</span><span class="sxs-lookup"><span data-stu-id="f3657-123">Yes</span></span>|  
|<span data-ttu-id="f3657-124">전송</span><span class="sxs-lookup"><span data-stu-id="f3657-124">Transport</span></span>|<span data-ttu-id="f3657-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f3657-125">HTTPS</span></span>|  
|<span data-ttu-id="f3657-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="f3657-126">Binding</span></span>|<span data-ttu-id="f3657-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="f3657-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="f3657-128">서비스</span><span class="sxs-lookup"><span data-stu-id="f3657-128">Service</span></span>  
 <span data-ttu-id="f3657-129">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f3657-130">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f3657-131">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="f3657-132">제공된 구성을 사용하여 서비스를 만들지만 끝점을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f3657-133">코드</span><span class="sxs-lookup"><span data-stu-id="f3657-133">Code</span></span>  
 <span data-ttu-id="f3657-134">다음 코드는 전송 보안을 사용하여 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="f3657-135">구성</span><span class="sxs-lookup"><span data-stu-id="f3657-135">Configuration</span></span>  
 <span data-ttu-id="f3657-136">다음 코드에서는 구성을 사용하여 동일한 끝점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="f3657-137">클라이언트는 어떤 메커니즘으로도 인증되지 않는 익명 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="f3657-138">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f3657-138">Client</span></span>  
 <span data-ttu-id="f3657-139">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f3657-140">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f3657-141">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="f3657-142">끝점 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="f3657-143">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="f3657-144">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="f3657-145">코드</span><span class="sxs-lookup"><span data-stu-id="f3657-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="f3657-146">구성</span><span class="sxs-lookup"><span data-stu-id="f3657-146">Configuration</span></span>  
 <span data-ttu-id="f3657-147">다음 구성은 서비스 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3657-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3657-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3657-148">See Also</span></span>  
 [<span data-ttu-id="f3657-149">보안 개요</span><span class="sxs-lookup"><span data-stu-id="f3657-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="f3657-150">WS 전송 보안</span><span class="sxs-lookup"><span data-stu-id="f3657-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="f3657-151">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="f3657-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="f3657-152">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="f3657-152">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
