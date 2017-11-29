---
title: "Windows 클라이언트를 사용하는 메시지 보안"
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
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f2a9f2f44f5dfd44f00ae580423b1d2781ae5bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="45753-102">Windows 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="45753-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="45753-103">이 시나리오에서는 메시지 보안 모드를 통해 보호되는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트와 서버를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45753-103">This scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and server secured by message security mode.</span></span> <span data-ttu-id="45753-104">클라이언트와 서비스는 Windows 자격 증명을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="45753-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="45753-105">![메시지 보안 Windows 클라이언트와](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="45753-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="45753-106">특성</span><span class="sxs-lookup"><span data-stu-id="45753-106">Characteristic</span></span>|<span data-ttu-id="45753-107">설명</span><span class="sxs-lookup"><span data-stu-id="45753-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="45753-108">보안 모드</span><span class="sxs-lookup"><span data-stu-id="45753-108">Security Mode</span></span>|<span data-ttu-id="45753-109">메시지</span><span class="sxs-lookup"><span data-stu-id="45753-109">Message</span></span>|  
|<span data-ttu-id="45753-110">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="45753-110">Interoperability</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45753-111">에만 해당</span><span class="sxs-lookup"><span data-stu-id="45753-111"> Only</span></span>|  
|<span data-ttu-id="45753-112">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="45753-112">Authentication (Server)</span></span>|<span data-ttu-id="45753-113">서버와 클라이언트의 상호 인증</span><span class="sxs-lookup"><span data-stu-id="45753-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="45753-114">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="45753-114">Authentication (Client)</span></span>|<span data-ttu-id="45753-115">서버와 클라이언트의 상호 인증</span><span class="sxs-lookup"><span data-stu-id="45753-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="45753-116">무결성</span><span class="sxs-lookup"><span data-stu-id="45753-116">Integrity</span></span>|<span data-ttu-id="45753-117">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="45753-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="45753-118">기밀성</span><span class="sxs-lookup"><span data-stu-id="45753-118">Confidentiality</span></span>|<span data-ttu-id="45753-119">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="45753-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="45753-120">전송</span><span class="sxs-lookup"><span data-stu-id="45753-120">Transport</span></span>|<span data-ttu-id="45753-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="45753-121">NET.TCP</span></span>|  
|<span data-ttu-id="45753-122">바인딩</span><span class="sxs-lookup"><span data-stu-id="45753-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="45753-123">서비스</span><span class="sxs-lookup"><span data-stu-id="45753-123">Service</span></span>  
 <span data-ttu-id="45753-124">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45753-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="45753-125">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45753-125">Do one of the following:</span></span>  
  
-   <span data-ttu-id="45753-126">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45753-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="45753-127">제공된 구성을 사용하여 서비스를 만들지만 끝점을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45753-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45753-128">코드</span><span class="sxs-lookup"><span data-stu-id="45753-128">Code</span></span>  
 <span data-ttu-id="45753-129">다음 코드에서는 Windows 컴퓨터의 안전한 컨텍스트를 설정하기 위해 메시지 보안을 사용하는 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45753-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="45753-130">구성</span><span class="sxs-lookup"><span data-stu-id="45753-130">Configuration</span></span>  
 <span data-ttu-id="45753-131">다음 구성은 서비스를 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45753-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="45753-132">클라이언트</span><span class="sxs-lookup"><span data-stu-id="45753-132">Client</span></span>  
 <span data-ttu-id="45753-133">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45753-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="45753-134">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45753-134">Do one of the following:</span></span>  
  
-   <span data-ttu-id="45753-135">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45753-135">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="45753-136">끝점 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45753-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="45753-137">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45753-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="45753-138">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="45753-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="45753-139">코드</span><span class="sxs-lookup"><span data-stu-id="45753-139">Code</span></span>  
 <span data-ttu-id="45753-140">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45753-140">The following code creates a client.</span></span> <span data-ttu-id="45753-141">바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `Windows`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="45753-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="45753-142">구성</span><span class="sxs-lookup"><span data-stu-id="45753-142">Configuration</span></span>  
 <span data-ttu-id="45753-143">다음 구성은 클라이언트 속성을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45753-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45753-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45753-144">See Also</span></span>  
 [<span data-ttu-id="45753-145">보안 개요</span><span class="sxs-lookup"><span data-stu-id="45753-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="45753-146">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="45753-146">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
