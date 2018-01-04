---
title: "익명 클라이언트를 사용하는 메시지 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e8c10c9d4838a2b6c9d3a021d22d2dfd4dc865da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="64944-102">익명 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="64944-102">Message Security with an Anonymous Client</span></span>
<span data-ttu-id="64944-103">다음 시나리오에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 메시지 보안에 의해 보호되는 클라이언트와 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64944-103">The following scenario shows a client and service secured by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] message security.</span></span> <span data-ttu-id="64944-104">이 디자인은 전송 보안 대신 메시지 보안을 사용하여 나중에 보다 다양한 클레임 기반 모델을 지원할 수 있도록 하는 것을 목적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="64944-105">권한 부여에 대 한 다양 한 클레임을 사용 하 여, 참조 [관리 클레임 및 권한 부여 Id 모델](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-105"> using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="64944-106">샘플 응용 프로그램에 대 한 참조 [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>  
  
 <span data-ttu-id="64944-107">![메시지 보안 익명 클라이언트를](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="64944-107">![Message security with an anynymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>  
  
|<span data-ttu-id="64944-108">특성</span><span class="sxs-lookup"><span data-stu-id="64944-108">Characteristic</span></span>|<span data-ttu-id="64944-109">설명</span><span class="sxs-lookup"><span data-stu-id="64944-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="64944-110">보안 모드</span><span class="sxs-lookup"><span data-stu-id="64944-110">Security Mode</span></span>|<span data-ttu-id="64944-111">메시지</span><span class="sxs-lookup"><span data-stu-id="64944-111">Message</span></span>|  
|<span data-ttu-id="64944-112">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="64944-112">Interoperability</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="64944-113">에만 해당</span><span class="sxs-lookup"><span data-stu-id="64944-113"> only</span></span>|  
|<span data-ttu-id="64944-114">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="64944-114">Authentication (Server)</span></span>|<span data-ttu-id="64944-115">초기 협상에 서버 인증이 필요하지만 클라이언트 인증은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64944-115">Initial negotiation requires server authentication, but not client authentication</span></span>|  
|<span data-ttu-id="64944-116">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="64944-116">Authentication (Client)</span></span>|<span data-ttu-id="64944-117">없음</span><span class="sxs-lookup"><span data-stu-id="64944-117">None</span></span>|  
|<span data-ttu-id="64944-118">무결성</span><span class="sxs-lookup"><span data-stu-id="64944-118">Integrity</span></span>|<span data-ttu-id="64944-119">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="64944-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="64944-120">기밀성</span><span class="sxs-lookup"><span data-stu-id="64944-120">Confidentiality</span></span>|<span data-ttu-id="64944-121">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="64944-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="64944-122">전송</span><span class="sxs-lookup"><span data-stu-id="64944-122">Transport</span></span>|<span data-ttu-id="64944-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="64944-123">HTTP</span></span>|  
  
## <a name="service"></a><span data-ttu-id="64944-124">서비스</span><span class="sxs-lookup"><span data-stu-id="64944-124">Service</span></span>  
 <span data-ttu-id="64944-125">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="64944-126">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-126">Do one of the following:</span></span>  
  
-   <span data-ttu-id="64944-127">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64944-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="64944-128">제공된 구성을 사용하여 서비스를 만들지만 끝점을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64944-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="64944-129">코드</span><span class="sxs-lookup"><span data-stu-id="64944-129">Code</span></span>  
 <span data-ttu-id="64944-130">다음 코드에서는 메시지 보안을 사용하는 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64944-130">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
 [!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]  
  
### <a name="configuration"></a><span data-ttu-id="64944-131">구성</span><span class="sxs-lookup"><span data-stu-id="64944-131">Configuration</span></span>  
 <span data-ttu-id="64944-132">코드 대신 다음 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64944-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="64944-133">서비스 동작 요소를 사용하여 서비스를 클라이언트에 인증하는 데 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="64944-134">서비스 요소는 `behaviorConfiguration` 특성을 사용하여 동작을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="64944-135">바인딩 요소는 클라이언트 자격 증명 형식을 `None`으로 지정하여 익명 클라이언트가 서비스를 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="CalculatorService"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="64944-136">클라이언트</span><span class="sxs-lookup"><span data-stu-id="64944-136">Client</span></span>  
 <span data-ttu-id="64944-137">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="64944-138">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-138">Do one of the following:</span></span>  
  
-   <span data-ttu-id="64944-139">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64944-139">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="64944-140">끝점 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64944-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="64944-141">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="64944-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64944-142">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="64944-143">코드</span><span class="sxs-lookup"><span data-stu-id="64944-143">Code</span></span>  
 <span data-ttu-id="64944-144">다음 코드에서는 클라이언트 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64944-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="64944-145">바인딩은 메시지 모드 보안을 사용하며 클라이언트 자격 증명 형식은 none으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="64944-145">The binding uses message mode security, and the client credential type is set to none.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
 [!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]  
  
### <a name="configuration"></a><span data-ttu-id="64944-146">구성</span><span class="sxs-lookup"><span data-stu-id="64944-146">Configuration</span></span>  
 <span data-ttu-id="64944-147">다음 코드에서는 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="64944-147">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_ICalculator"   
        contract="ICalculator"  
        name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64944-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64944-148">See Also</span></span>  
 [<span data-ttu-id="64944-149">보안 개요</span><span class="sxs-lookup"><span data-stu-id="64944-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="64944-150">분산 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="64944-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="64944-151">메시지 보안 익명</span><span class="sxs-lookup"><span data-stu-id="64944-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 [<span data-ttu-id="64944-152">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="64944-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="64944-153">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="64944-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
