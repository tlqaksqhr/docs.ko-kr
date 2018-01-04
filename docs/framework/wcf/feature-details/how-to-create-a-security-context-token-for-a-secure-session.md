---
title: "방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기"
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
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3dc0e44e7f561e39128e32d3af5fbd495316fdd3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="41637-102">방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기</span><span class="sxs-lookup"><span data-stu-id="41637-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="41637-103">보안 세션에서 상태 저장 SCT(보안 컨텍스트 토큰)을 사용하면 세션에서 서비스 재활용의 영향을 받지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="41637-104">예를 들어, 상태 비저장 SCT를 보안 세션에서 사용할 때 IIS(인터넷 정보 서비스)를 다시 설정하면 서비스와 연결된 세션 데이터가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="41637-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="41637-105">이 세션 데이터에는 SCT 토큰 캐시가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="41637-106">따라서 클라이언트가 서비스에 상태 비저장 SCT를 다음에 보낼 때 SCT와 연결된 키를 검색할 수 없기 때문에 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="41637-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="41637-107">그러나 상태 저장 SCT를 사용하는 경우에는 SCT와 연결된 키가 SCT에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="41637-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="41637-108">키가 SCT에 포함되어 메시지에 포함되므로 서비스 재활용이 보안 세션에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="41637-109">기본적으로 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 보안 세션에서 상태 비저장 SCT를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-109">By default, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="41637-110">이 항목에서는 보안 세션에서 상태 저장 SCT를 사용하는 방법에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41637-111"><xref:System.ServiceModel.Channels.IDuplexChannel>에서 파생되는 계약을 포함하는 보안 세션에서는 상태 저장 SCT를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41637-112">보안 세션에서 상태 저장 SCT를 사용하는 응용 프로그램의 경우 서비스의 스레드 ID는 연결된 사용자 프로필이 있는 사용자 계정이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="41637-113">`Local Service`처럼 사용자 프로필이 없는 계정으로 서비스를 실행하면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41637-114">Windows XP에서 가장이 필요한 경우 상태 저장 SCT 없이 보안 세션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="41637-115">상태 저장 SCT가 가장과 함께 사용되는 경우 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="41637-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="41637-116">[지원 되지 않는 시나리오](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-116"> [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="41637-117">보안 세션에서 상태 저장 SCT를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="41637-117">To use stateful SCTs in a secure session</span></span>  
  
-   <span data-ttu-id="41637-118">상태 저장 SCT를 사용하는 보안 세션을 통해 SOAP 메시지를 보호하도록 지정하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41637-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1.  <span data-ttu-id="41637-119">추가 하 여 사용자 지정 바인딩을 정의 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 서비스에 대 한 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-119">Define a custom binding, by adding a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  <span data-ttu-id="41637-120">추가 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 자식 요소를는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-120">Add a [\<binding>](../../../../docs/framework/misc/binding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="41637-121">구성 파일에서 `name` 특성을 고유한 이름으로 설정하여 바인딩 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  <span data-ttu-id="41637-122">추가 하 여이 서비스에서 보내고 받는 메시지에 대 한 인증 모드를 지정 된 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 자식 요소를는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="41637-123">`authenticationMode` 특성을 `SecureConversation`으로 설정하여 보안 세션을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="41637-124">`requireSecurityContextCancellation` 특성을 `false`로 설정하여 상태 저장 SCT를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  <span data-ttu-id="41637-125">추가 하 여 보안 세션을 설정할 때 클라이언트에서 인증 하는 방법을 지정는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 자식 요소를는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="41637-126">`authenticationMode` 특성을 설정하여 클라이언트를 인증하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  <span data-ttu-id="41637-127">와 같은 인코딩 요소를 추가 하 여 메시지 인코딩을 지정 [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  <span data-ttu-id="41637-128">와 같은 전송 요소를 추가 하 여 전송을 지정는 [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="41637-129">다음 코드 예제에서는 구성을 사용하여 메시지가 보안 세션에서 상태 저장 SCT와 함께 사용할 수 있는 사용자 지정 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="41637-130">예</span><span class="sxs-lookup"><span data-stu-id="41637-130">Example</span></span>  
 <span data-ttu-id="41637-131">다음 코드 예제에서는 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 인증 모드를 사용하여 보안 세션을 부트스트랩하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41637-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="41637-132">Windows 인증을 상태 저장 SCT와 함께 사용할 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 속성에 실제 호출자의 ID를 채우지 않고 속성을 익명으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-132">When Windows authentication is used in combination with a stateful SCT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="41637-133">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안에서는 들어오는 SCT의 모든 요청에 대해 서비스 보안 컨텍스트 내용을 다시 만들어야 하기 때문에, 서버는 메모리에서 보안 세션을 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41637-133">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="41637-134"><xref:System.Security.Principal.WindowsIdentity> 인스턴스를 SCT로 serialize할 수 없기 때문에 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 속성은 익명 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41637-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="41637-135">다음 구성에서 이 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41637-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41637-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41637-136">See Also</span></span>  
 [<span data-ttu-id="41637-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="41637-137">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
