---
title: WCF 보안 프로그래밍
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
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
caps.latest.revision: 25
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 6c8769511f608834c7539779d83977880e1d4093
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="programming-wcf-security"></a><span data-ttu-id="2a289-102">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2a289-102">Programming WCF Security</span></span>
<span data-ttu-id="2a289-103">이 항목에서는 보안 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 사용되는 기본 프로그래밍 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-103">This topic describes the fundamental programming tasks used to create a secure [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="2a289-104">이 항목에서는 인증, 기밀성 및 무결성을 이라고 통칭 *전송 보안*합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-104">This topic covers only authentication, confidentiality, and integrity, collectively known as *transfer security*.</span></span> <span data-ttu-id="2a289-105">이 항목에서는 권한 부여 (리소스 또는 서비스에 대 한 액세스 제어);를 설명 하지 권한 부여에 대 한 자세한 내용은 참조 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-105">This topic does not cover authorization (the control of access to resources or services); for information on authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a289-106">에 대 한 관계에서 특히 보안 개념에 대 한 중요 한 사항을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], msdn에서 집합의 패턴 및 실습 자습서를 참조 하십시오. [시나리오, 패턴 및 구현 지침에 대 한 향상 된 기능 WSE (Web Services) 3.0](http://go.microsoft.com/fwlink/?LinkID=88250).</span><span class="sxs-lookup"><span data-stu-id="2a289-106">For a valuable introduction to security concepts, especially in regard to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the set of patterns and practices tutorials on MSDN at [Scenarios, Patterns, and Implementation Guidance for Web Services Enhancements (WSE) 3.0](http://go.microsoft.com/fwlink/?LinkID=88250).</span></span>  
  
 <span data-ttu-id="2a289-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프로그래밍은 보안 모드, 클라이언트 자격 증명 형식 및 자격 증명 값을 설정하는 세 가지 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-107">Programming [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security is based on three steps setting the following: the security mode, a client credential type, and the credential values.</span></span> <span data-ttu-id="2a289-108">코드 또는 구성을 통해 이러한 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-108">You can perform these steps either through code or configuration.</span></span>  
  
## <a name="setting-the-security-mode"></a><span data-ttu-id="2a289-109">보안 모드 설정</span><span class="sxs-lookup"><span data-stu-id="2a289-109">Setting the Security Mode</span></span>  
 <span data-ttu-id="2a289-110">다음에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 보안 모드로 프로그래밍하는 일반 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-110">The following explains the general steps for programming with the security mode in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
1.  <span data-ttu-id="2a289-111">응용 프로그램 요구 사항에 적합한 미리 정의된 바인딩 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-111">Select one of the predefined bindings appropriate to your application requirements.</span></span> <span data-ttu-id="2a289-112">바인딩 선택 목록, 참조 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-112">For a list of the binding choices, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="2a289-113">기본적으로 거의 모든 바인딩에서 보안을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-113">By default, nearly every binding has security enabled.</span></span> <span data-ttu-id="2a289-114">한 가지 예외는는 <xref:System.ServiceModel.BasicHttpBinding> 클래스 (구성을 사용 하 여 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)).</span><span class="sxs-lookup"><span data-stu-id="2a289-114">The one exception is the <xref:System.ServiceModel.BasicHttpBinding> class (using configuration, the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)).</span></span>  
  
     <span data-ttu-id="2a289-115">선택한 바인딩에 따라 전송이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-115">The binding you select determines the transport.</span></span> <span data-ttu-id="2a289-116">예를 들어, <xref:System.ServiceModel.WSHttpBinding>에서는 HTTP를 전송으로 사용하고 <xref:System.ServiceModel.NetTcpBinding>에서는 TCP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-116">For example, <xref:System.ServiceModel.WSHttpBinding> uses HTTP as the transport; <xref:System.ServiceModel.NetTcpBinding> uses TCP.</span></span>  
  
2.  <span data-ttu-id="2a289-117">바인딩에 대한 보안 모드 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-117">Select one of the security modes for the binding.</span></span> <span data-ttu-id="2a289-118">선택한 바인딩에 따라 사용 가능한 모드 선택 사항이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-118">Note that the binding you select determines the available mode choices.</span></span> <span data-ttu-id="2a289-119">예를 들어, <xref:System.ServiceModel.WSDualHttpBinding>에서는 전송 보안을 허용하지 않으므로, 전송 보안은 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-119">For example, the <xref:System.ServiceModel.WSDualHttpBinding> does not allow transport security (it is not an option).</span></span> <span data-ttu-id="2a289-120">마찬가지로 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>과 <xref:System.ServiceModel.NetNamedPipeBinding>에서는 모두 메시지 보안을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-120">Similarly, neither the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> nor the <xref:System.ServiceModel.NetNamedPipeBinding> allows message security.</span></span>  
  
     <span data-ttu-id="2a289-121">다음과 같은 세 가지 선택 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-121">You have three choices:</span></span>  
  
    1.  `Transport`  
  
         <span data-ttu-id="2a289-122">전송 보안은 선택한 바인딩에서 사용하는 메커니즘에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-122">Transport security depends on the mechanism that the binding you have selected uses.</span></span> <span data-ttu-id="2a289-123">예를 들어, `WSHttpBinding`을 사용하는 경우 보안 메커니즘은 SSL(Secure Sockets Layer)(또한 HTTPS에 대한 메커니즘)입니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-123">For example, if you are using `WSHttpBinding` then the security mechanism is Secure Sockets Layer (SSL) (also the mechanism for the HTTPS protocol).</span></span> <span data-ttu-id="2a289-124">일반적으로 전송 보안의 주요 이점은 사용 중인 전송에 관계 없이 처리 능력이 우수하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-124">Generally speaking, the main advantage of transport security is that it delivers good throughput no matter which transport you are using.</span></span> <span data-ttu-id="2a289-125">그러나 두 가지 제한이 있습니다. 첫째, 전송 메커니즘이 사용자를 인증하는 데 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-125">However, it does have two limitations: The first is that the transport mechanism dictates the credential type used to authenticate a user.</span></span> <span data-ttu-id="2a289-126">이는 서비스가 다른 형식의 자격 증명을 요구하는 다른 서비스와 상호 작용해야 하는 경우에만 단점이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-126">This is a drawback only if a service needs to interoperate with other services that demand different types of credentials.</span></span> <span data-ttu-id="2a289-127">둘째는 메시지 수준에서 보안이 적용되지 않기 때문에 종단 간 방식 대신 hop-by-hop 방식으로 보안이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-127">The second is that, because the security is not applied at the message level, security is implemented in a hop-by-hop manner rather than end-to-end.</span></span> <span data-ttu-id="2a289-128">이 제한은 클라이언트와 서비스 사이의 메시지 경로에 매개자가 포함되어 있는 경우에만 문제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-128">This latter limitation is an issue only if the message path between client and service includes intermediaries.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="2a289-129"> 어떤 사용할 전송, 참조 [전송 선택](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-129"> which transport to use, see [Choosing a Transport](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="2a289-130"> 전송 보안을 사용 하 여 참조 [전송 보안 개요](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-130"> using transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
    2.  `Message`  
  
         <span data-ttu-id="2a289-131">메시지 보안은 모든 메시지에 메시지를 보안된 상태로 유지하는 데 필요한 헤더와 데이터가 포함되어 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-131">Message security means that every message includes the necessary headers and data to keep the message secure.</span></span> <span data-ttu-id="2a289-132">헤더의 구성이 다양하므로 여러 자격 증명을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-132">Because the composition of the headers varies, you can include any number of credentials.</span></span> <span data-ttu-id="2a289-133">이는 전송 메커니즘이 제공할 수 없는 특정 자격 증명 형식을 요구하는 다른 서비스와 상호 작용할 경우나 서비스마다 다른 자격 증명 형식을 요구하는 여러 서비스에서 메시지를 사용해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-133">This becomes a factor if you are interoperating with other services that demand a specific credential type that a transport mechanism can't supply, or if the message must be used with more than one service, where each service demands a different credential type.</span></span>  
  
         <span data-ttu-id="2a289-134">자세한 내용은 참조 [메시지 보안](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-134">For more information, see [Message Security](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
    3.  `TransportWithMessageCredential`  
  
         <span data-ttu-id="2a289-135">이 선택 옵션에서는 전송 계층을 사용하여 메시지 전송을 보안하지만, 모든 메시지에 다른 서비스에 필요한 풍부한 자격 증명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-135">This choice uses the transport layer to secure the message transfer, while every message includes the rich credentials other services need.</span></span> <span data-ttu-id="2a289-136">이 옵션은 전송 보안의 성능 이점과 메시지 보안의 풍부한 자격 증명 이점을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-136">This combines the performance advantage of transport security with the rich credentials advantage of message security.</span></span> <span data-ttu-id="2a289-137"><xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> 및 <xref:System.ServiceModel.WSHttpBinding> 바인딩에서 이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-137">This is available with the following bindings: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding>, and <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
3.  <span data-ttu-id="2a289-138">HTTP(HTTPS)에 대해 전송 보안을 사용하려면 SSL 인증서를 사용하여 호스트를 구성하고 포트에서 SSL을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-138">If you decide to use transport security for HTTP (in other words, HTTPS), you must also configure the host with an SSL certificate and enable SSL on a port.</span></span> <span data-ttu-id="2a289-139">자세한 내용은 참조 [HTTP 전송 보안](../../../../docs/framework/wcf/feature-details/http-transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-139">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
4.  <span data-ttu-id="2a289-140"><xref:System.ServiceModel.WSHttpBinding>을 사용하고 보안 세션을 설정할 필요가 없는 경우 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-140">If you are using the <xref:System.ServiceModel.WSHttpBinding> and do not need to establish a secure session, set the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="2a289-141">클라이언트와 서비스에서 대칭 키를 사용하여 채널을 만들 때(클라이언트와 서버가 대화 상자가 닫힐 때까지 대화 기간 동안 동일한 키를 사용), 보안 세션이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-141">A secure session occurs when a client and service create a channel using a symmetric key (both client and server use the same key for the length of a conversation, until the dialog is closed).</span></span>  
  
## <a name="setting-the-client-credential-type"></a><span data-ttu-id="2a289-142">클라이언트 자격 증명 형식 설정</span><span class="sxs-lookup"><span data-stu-id="2a289-142">Setting the Client Credential Type</span></span>  
 <span data-ttu-id="2a289-143">클라이언트 자격 증명 형식을 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-143">Select a client credential type as appropriate.</span></span> <span data-ttu-id="2a289-144">자세한 내용은 참조 [자격 증명 유형을 선택 하면](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-144">For more information, see [Selecting a Credential Type](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).</span></span> <span data-ttu-id="2a289-145">다음과 같은 클라이언트 자격 증명 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-145">The following client credential types are available:</span></span>  
  
-   `Windows`  
  
-   `Certificate`  
  
-   `Digest`  
  
-   `Basic`  
  
-   `UserName`  
  
-   `NTLM`  
  
-   `IssuedToken`  
  
 <span data-ttu-id="2a289-146">모드 설정 방법에 따라 자격 증명 형식을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-146">Depending on how you set the mode, you must set the credential type.</span></span> <span data-ttu-id="2a289-147">다음 구성 예제에 표시된 것처럼 `wsHttpBinding`을 선택하고 모드를 "Message"로 설정한 경우 메시지 요소의 `clientCredentialType` 특성 값을 `None`, `Windows`, `UserName`, `Certificate`, `IssuedToken` 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-147">For example, if you have selected the `wsHttpBinding`, and have set the mode to "Message," then you can also set the `clientCredentialType` attribute of the Message element to one of the following values: `None`, `Windows`, `UserName`, `Certificate`, and `IssuedToken`, as shown in the following configuration example.</span></span>  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>  
</bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="2a289-148">코드</span><span class="sxs-lookup"><span data-stu-id="2a289-148">Or in code:</span></span>  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a><span data-ttu-id="2a289-149">서비스 자격 증명 값 설정</span><span class="sxs-lookup"><span data-stu-id="2a289-149">Setting Service Credential Values</span></span>  
 <span data-ttu-id="2a289-150">클라이언트 자격 증명 형식을 선택한 경우 사용할 서비스 및 클라이언트에 대한 실제 자격 증명을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-150">Once you select a client credential type, you must set the actual credentials for the service and client to use.</span></span> <span data-ttu-id="2a289-151">서비스에서 자격 증명은 <xref:System.ServiceModel.Description.ServiceCredentials> 클래스를 사용하여 설정하고 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 클래스의 <xref:System.ServiceModel.ServiceHostBase> 속성에 의해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-151">On the service, credentials are set using the <xref:System.ServiceModel.Description.ServiceCredentials> class and returned by the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property of the <xref:System.ServiceModel.ServiceHostBase> class.</span></span> <span data-ttu-id="2a289-152">사용 중인 바인딩은 서비스 자격 증명 형식, 선택한 보안 모드 및 클라이언트 자격 증명 형식을 함축합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-152">The binding in use implies the service credential type, the security mode chosen, and the type of the client credential.</span></span> <span data-ttu-id="2a289-153">다음 코드에서는 서비스 자격 증명에 대한 인증서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-153">The following code sets a certificate for a service credential.</span></span>  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a><span data-ttu-id="2a289-154">클라이언트 자격 증명 값 설정</span><span class="sxs-lookup"><span data-stu-id="2a289-154">Setting Client Credential Values</span></span>  
 <span data-ttu-id="2a289-155">클라이언트에서 클라이언트 자격 증명 값은 <xref:System.ServiceModel.Description.ClientCredentials> 클래스를 사용하여 설정하고 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성에 의해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-155">On the client, set client credential values using the <xref:System.ServiceModel.Description.ClientCredentials> class and returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class.</span></span> <span data-ttu-id="2a289-156">다음 코드에서는 TCP 프로토콜을 사용하여 인증서를 클라이언트에 대한 자격 증명으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a289-156">The following code sets a certificate as a credential on a client using the TCP protocol.</span></span>  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2a289-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a289-157">See Also</span></span>  
 [<span data-ttu-id="2a289-158">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2a289-158">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="2a289-159">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="2a289-159">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
