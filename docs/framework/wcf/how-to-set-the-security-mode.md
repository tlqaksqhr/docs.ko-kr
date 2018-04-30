---
title: '방법: 보안 모드 설정'
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
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
caps.latest.revision: 22
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: bdfd273f7a541cac4f1fd8a03a976d73e997b718
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="27230-102">방법: 보안 모드 설정</span><span class="sxs-lookup"><span data-stu-id="27230-102">How to: Set the Security Mode</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="27230-103"> 보안에는 대부분의 미리 정의된 바인딩에서 발견되는 전송, 메시지, "메시지 자격 증명을 사용한 전송"의 세 가지 일반 보안 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27230-103"> security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="27230-104">두 개의 추가 모드는 두 바인딩에만 해당됩니다. 즉, "전송-자격 증명만" 모드는 <xref:System.ServiceModel.BasicHttpBinding>에서 사용되고, "모두" 모드는 <xref:System.ServiceModel.NetMsmqBinding>에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27230-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="27230-105">그러나 이 항목에서는 세 가지 일반 보안 모드(<xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>)에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
 <span data-ttu-id="27230-106">모든 미리 정의된 바인딩이 이러한 모드를 모두 지원하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="27230-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="27230-107">이 항목에서는 <xref:System.ServiceModel.WSHttpBinding> 및 <xref:System.ServiceModel.NetTcpBinding> 클래스를 사용하여 모드를 설정하고 프로그래밍 방식과 구성을 통한 모드 설정 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>  
  
 <span data-ttu-id="27230-108">자세한 내용은 참조 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 보안 참조 [보안 개요](../../../docs/framework/wcf/feature-details/security-overview.md), [Services에 보안 설정](../../../docs/framework/wcf/securing-services.md), 및 [보안 서비스와 클라이언트](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-108">For more information, see [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] security, see [Security Overview](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), and [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="27230-109">전송 모드 및 메시지에 대 한 자세한 내용은 참조 [전송 보안](../../../docs/framework/wcf/feature-details/transport-security.md) 및 [메시지 보안](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-109">For more information about transport mode and message, see [Transport Security](../../../docs/framework/wcf/feature-details/transport-security.md) and [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
### <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="27230-110">코드에서 보안 모드를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="27230-110">To set the security mode in code</span></span>  
  
1.  <span data-ttu-id="27230-111">사용 중인 바인딩 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27230-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="27230-112">미리 정의 된 바인딩 목록, 참조 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-112">For a list of predefined bindings, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="27230-113">이 예제에서는 <xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27230-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
2.  <span data-ttu-id="27230-114">`Mode` 속성에서 반환하는 개체의 `Security` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     <span data-ttu-id="27230-115">또는 다음 코드에 표시된 것처럼 모드를 메시지로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-115">Alternatively, set the mode to message, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     <span data-ttu-id="27230-116">또는 다음 코드에 표시된 것처럼 모드를 메시지 자격 증명을 사용한 전송으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  <span data-ttu-id="27230-117">다음 코드에 표시된 것처럼 바인딩의 생성자에서 모드를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27230-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="27230-118">ClientCredentialType 속성 설정</span><span class="sxs-lookup"><span data-stu-id="27230-118">Setting the ClientCredentialType Property</span></span>  
 <span data-ttu-id="27230-119">모드를 세 값 중 하나로 설정하면 `ClientCredentialType` 속성을 설정하는 방법이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="27230-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="27230-120">예를 들어, <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하여 모드를 `Transport`로 설정할 경우 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> 클래스의 <xref:System.ServiceModel.HttpTransportSecurity> 속성을 적절한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>  
  
#### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="27230-121">전송 모드에 대해 ClientCredentialType 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="27230-121">To set the ClientCredentialType property for Transport mode</span></span>  
  
1.  <span data-ttu-id="27230-122">바인딩의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27230-122">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="27230-123">`Mode` 속성을 `Transport`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-123">Set the `Mode` property to `Transport`.</span></span>  
  
3.  <span data-ttu-id="27230-124">`ClientCredential` 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="27230-125">다음 코드에서는 속성을 `Windows`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-125">The following code sets the property to `Windows`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="27230-126">메시지 모드에 대해 ClientCredentialType 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="27230-126">To set the ClientCredentialType property for Message mode</span></span>  
  
1.  <span data-ttu-id="27230-127">바인딩의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27230-127">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="27230-128">`Mode` 속성을 `Message`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-128">Set the `Mode` property to `Message`.</span></span>  
  
3.  <span data-ttu-id="27230-129">`ClientCredential` 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="27230-130">다음 코드에서는 속성을 `Certificate`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-130">The following code sets the property to `Certificate`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="27230-131">구성에서 모드 및 ClientCredentialType 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="27230-131">To set the Mode and ClientCredentialType property in configuration</span></span>  
  
1.  <span data-ttu-id="27230-132">적절 한 바인딩 요소를 추가할는 [ \<바인딩 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="27230-132">Add an appropriate binding element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="27230-133">다음 예제에서는 추가 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="27230-133">The following example adds a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
2.  <span data-ttu-id="27230-134">추가 `<binding>` 요소 집합과 해당 `name` 특성을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27230-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="27230-135">`<security>` 요소를 추가하고 `mode` 특성을 `Message`, `Transport` 또는 `TransportWithMessageCredential`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="27230-136">모드를 `Transport`로 설정한 경우 `<transport>` 요소를 추가하고 `clientCredential` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>  
  
     <span data-ttu-id="27230-137">다음 예제에서는 모드를 "`Transport"`로 설정한 다음 `clientCredentialType` 요소의 `<transport>` 특성을 "`Windows"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="27230-138">또는 `security mode`를 "`Message"`로 설정한 다음 `<"message">` 요소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="27230-139">이 예제에서는 `clientCredentialType`을 "`Certificate"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="27230-140"><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> 값은 특별한 경우에 사용되며 이에 대해서는 아래에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27230-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>  
  
### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="27230-141">TransportWithMessageCredential 사용</span><span class="sxs-lookup"><span data-stu-id="27230-141">Using TransportWithMessageCredential</span></span>  
 <span data-ttu-id="27230-142">보안 모드를 `TransportWithMessageCredential`로 설정하면 전송에서 전송 수준 보안을 제공하는 실제 메커니즘을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="27230-143">예를 들어, HTTP 프로토콜에서는 HTTP를 통한 SSL(Secure Sockets Layer)(HTTPS)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="27230-144">따라서 전송 보안 개체(예: `ClientCredentialType`)의 <xref:System.ServiceModel.HttpTransportSecurity> 속성 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27230-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="27230-145">즉, 메시지 보안 개체(`ClientCredentialType` 바인딩의 경우 `WSHttpBinding` 개체)의 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27230-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>  
  
 <span data-ttu-id="27230-146">자세한 내용은 참조 [하는 방법: 전송 보안과 메시지 자격 증명을 사용 하 여](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27230-146">For more information, see [How to: Use Transport Security and Message Credentials](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27230-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27230-147">See Also</span></span>  
 [<span data-ttu-id="27230-148">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="27230-148">How to: Configure a Port with an SSL Certificate</span></span>](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="27230-149">방법: 전송 보안 및 메시지 자격 증명 사용</span><span class="sxs-lookup"><span data-stu-id="27230-149">How to: Use Transport Security and Message Credentials</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)  
 [<span data-ttu-id="27230-150">전송 보안</span><span class="sxs-lookup"><span data-stu-id="27230-150">Transport Security</span></span>](../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="27230-151">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="27230-151">Message Security</span></span>](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="27230-152">보안 개요</span><span class="sxs-lookup"><span data-stu-id="27230-152">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="27230-153">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="27230-153">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="27230-154">\<security></span><span class="sxs-lookup"><span data-stu-id="27230-154">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)  
 [<span data-ttu-id="27230-155">\<security></span><span class="sxs-lookup"><span data-stu-id="27230-155">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)  
 [<span data-ttu-id="27230-156">\<security></span><span class="sxs-lookup"><span data-stu-id="27230-156">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
