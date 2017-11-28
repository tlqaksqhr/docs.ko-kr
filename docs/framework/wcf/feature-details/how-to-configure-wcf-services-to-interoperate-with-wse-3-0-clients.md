---
title: "방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 099fb059e375e0e76cffb5389191011d866b2d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="50b22-102">방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="50b22-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="50b22-103"> 서비스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 2004년 8월 버전의 WS-Addressing 사양을 사용하도록 구성된 경우 Microsoft .NET 클라이언트용 WSE(Web Services Enhancements) 3.0과 유선 수준으로 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-103"> services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="50b22-104">WCF 서비스가 WSE 3.0 클라이언트와 상호 운용하도록 하려면</span><span class="sxs-lookup"><span data-stu-id="50b22-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1.  <span data-ttu-id="50b22-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-105">Define a custom binding for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
     <span data-ttu-id="50b22-106">2004년 8월 버전의 WS-Addressing 사양을 메시지 인코딩에 사용하도록 지정하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="50b22-107">자식을 추가할 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 서비스의 구성 파일의 합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="50b22-108">바인딩에 대 한 이름을 추가 하 여 지정는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 에 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 설정는 `name` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="50b22-109">인증 모드와 자식 추가 하 여 WSE 3.0과 호환 되는 메시지 보안을 유지 하는 데 사용 되는 Ws-security 사양 버전 지정 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 에 [ \<바인딩 >](../../../../docs/framework/misc/binding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="50b22-110">인증 모드를 설정 하려면 설정는 `authenicationMode` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="50b22-111">인증 모드는 대체로 WSE 3.0의 턴키 보안 어설션에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="50b22-112">다음 표에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인증 모드와 WSE 3.0 턴키 보안 어설션이 매핑되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-112">The following table maps authentication modes in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="50b22-113">WCF 인증 모드</span><span class="sxs-lookup"><span data-stu-id="50b22-113">WCF Authentication Mode</span></span>|<span data-ttu-id="50b22-114">WSE 3.0 턴키 보안 어설션</span><span class="sxs-lookup"><span data-stu-id="50b22-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="50b22-115">\*기본 차이점 중 하나는 `mutualCertificate10Security` 및 `mutualCertificate11Security` 턴키 보안 어설션은 SOAP 메시지 보안을 위해 WSE에서 사용 하는 Ws-security 사양 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="50b22-116">`mutualCertificate10Security`에는 WS-Security 1.0이 사용되는 반면, `mutualCertificate11Security`에는 WS-Security 1.1이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="50b22-117">에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], Ws-security 사양 버전에 지정 된는 `messageSecurityVersion` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-117">For [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="50b22-118">SOAP 메시지 보안을 유지 하는 데 사용 되는 Ws-security 사양 버전을 설정 하려면 설정는 `messageSecurityVersion` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="50b22-119">WSE 3.0과 상호 운용하려면 `messageSecurityVersion` 특성의 값을 <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="50b22-120">2004 년 8 월 버전의 Ws-addressing 사양 사용 되도록 지정 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추가 하 여 한 [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) 설정 하 고는 `messageVersion` 하려면 해당 값으로 <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-120">Specify that the August 2004 version of the WS-Addressing specification is used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="50b22-121">SOAP 1.2를 사용할 경우에는 `messageVersion` 특성을 <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2.  <span data-ttu-id="50b22-122">서비스에서 사용자 지정 바인딩이 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="50b22-123">설정의 `binding` 특성에는 [ \<끝점 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소를 `customBinding`합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="50b22-124">설정는 `bindingConfiguration` 특성의는 [ \<끝점 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소에 지정 된 값으로는 `name` 특성의는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 사용자 지정 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50b22-125">예제</span><span class="sxs-lookup"><span data-stu-id="50b22-125">Example</span></span>  
 <span data-ttu-id="50b22-126">다음은 `Service.HelloWorldService`에서 사용자 지정 바인딩을 사용하여 WSE 3.0 클라이언트와 상호 운용하도록 지정하는 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="50b22-127">사용자 지정 바인딩에서는 교환되는 메시지를 인코딩하는 데 2004년 8월 버전의 WS-Addressing과 WS-Security 1.1을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="50b22-128">메시지 보안은 <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 인증 모드를 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="50b22-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50b22-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50b22-129">See Also</span></span>  
 [<span data-ttu-id="50b22-130">방법: 시스템 제공 바인딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="50b22-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
