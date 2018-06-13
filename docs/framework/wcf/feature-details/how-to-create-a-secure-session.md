---
title: '방법: 보안 세션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ce351a87e70b09a2f68654af817e28fa3145d79d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493222"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="bab74-102">방법: 보안 세션 만들기</span><span class="sxs-lookup"><span data-stu-id="bab74-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="bab74-103">제외 된 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 바인딩, Windows Communication Foundation (WCF)의 시스템 제공 바인딩을 자동으로 사용 하 여 메시지 보안을 사용 하는 경우 보안 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="bab74-104">기본적으로 보안 세션은 재생된 웹 서버에 남지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="bab74-105">보안 세션이 설정되면 클라이언트와 서비스에서 보안 세션과 연결된 키를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="bab74-106">메시지를 교환하면 캐시된 키의 식별자만 교환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="bab74-107">웹 서버가 재생되면 캐시도 재생되며, 이 때 웹 서버는 식별자의 캐시된 키를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="bab74-108">이런 경우가 발생하면 클라이언트로 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="bab74-109">상태 저장 SCT(보안 컨텍스트 토큰)을 사용하는 보안 세션은 웹 서버가 재생되는 동안 보안 세션을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="bab74-110">보안 세션에서 상태 저장 SCT 사용에 대 한 자세한 내용은 참조 [하는 방법: 보안 세션에 대 한 보안 컨텍스트 토큰 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="bab74-111">서비스에서 시스템에서 제공되는 바인딩 중 하나를 사용하여 보안 세션을 사용하도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="bab74-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="bab74-112">메시지 보안을 지원하는 시스템 제공 바인딩을 사용하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="bab74-113">제외 된 [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 바인딩의 보안 세션을 사용 하는 시스템 제공 바인딩은 메시지 보안을 WCF를 자동으로 사용 하도록 구성 된 경우.</span><span class="sxs-lookup"><span data-stu-id="bab74-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="bab74-114">다음 표에는 메시지 보안을 지원하는 시스템 제공 바인딩과 메시지 보안이 기본 보안 메커니즘인지 여부가 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="bab74-115">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="bab74-115">System-provided binding</span></span>|<span data-ttu-id="bab74-116">구성 요소</span><span class="sxs-lookup"><span data-stu-id="bab74-116">Configuration element</span></span>|<span data-ttu-id="bab74-117">기본적으로 메시지 보안 사용</span><span class="sxs-lookup"><span data-stu-id="bab74-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="bab74-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bab74-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="bab74-119">아니요</span><span class="sxs-lookup"><span data-stu-id="bab74-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="bab74-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bab74-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="bab74-121">예</span><span class="sxs-lookup"><span data-stu-id="bab74-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="bab74-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bab74-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="bab74-123">예</span><span class="sxs-lookup"><span data-stu-id="bab74-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="bab74-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bab74-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="bab74-125">예</span><span class="sxs-lookup"><span data-stu-id="bab74-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="bab74-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="bab74-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="bab74-127">아니요</span><span class="sxs-lookup"><span data-stu-id="bab74-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="bab74-128">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="bab74-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="bab74-129">아니요</span><span class="sxs-lookup"><span data-stu-id="bab74-129">No</span></span>|  
  
     <span data-ttu-id="bab74-130">다음 코드 예제에서는 구성을 사용 하 여 명명 된 바인딩 지정 `wsHttpBinding_Calculator` 를 사용 하는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), 보안, 메시지 및 보안 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="bab74-131">지정 하는 다음 코드 예제는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), 보안, 메시지 및 보안 세션은 보안에 사용 되는 `secureCalculator` 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="bab74-132">에 대 한 보안 세션을 끌 수는 [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 설정 하 여는 `establishSecurityContext` 특성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="bab74-133">다른 시스템 제공 바인딩의 경우 사용자 지정 바인딩을 만들어야만 보안 세션을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="bab74-134">사용자 지정 바인딩을 사용하여 서비스에서 보안 세션을 사용하도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="bab74-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="bab74-135">보안 세션을 통해 SOAP 메시지를 보호하도록 지정하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="bab74-136">사용자 지정 바인딩을 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: 시스템 제공 바인딩 사용자 지정](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="bab74-137">다음 코드 예제에서는 구성을 사용하여 보안 세션을 통해 메시지를 전송하는 사용자 지정 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="bab74-138">다음 코드 예제에서는 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 인증 모드를 사용하여 보안 세션을 부트스트랩하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bab74-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bab74-139">See Also</span></span>  
 [<span data-ttu-id="bab74-140">WCF 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="bab74-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
