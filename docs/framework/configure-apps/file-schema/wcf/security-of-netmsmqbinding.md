---
title: "&lt;netMsmqBinding&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 15ebbd1f0f139ef0d66ed802b990876735074485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a>&lt;netMsmqBinding&gt;의 &lt;security&gt;
MSMQ 바인딩에 대한 보안 설정을 정의합니다. 이 클래스는 전송 또는 SOAP 보안의 사용 여부 그리고 보안이 사용된다면 어떤 인증 모드 및 보호 수준을 사용하는지를 지정합니다.  
  
 \<시스템입니다. ServiceModel >  
\<바인딩 >  
\<netMsmqBinding >  
\<바인딩 >  
\<보안 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|모드|무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -None: 보안이 해제 합니다.<br />-Transport: 보호 및 인증이 전송에 의해 제공 됩니다. 이는 두 큐 관리자 간의 메시지 보안에 적용됩니다. 응용 프로그램 및 큐 관리자 간에는 제공되는 보안이 없습니다. 기존 Msmq 응용 프로그램이 이러한 보안 모드 형식과 동일한 기능입니다.<br />-메시지: 종단 간 응용 프로그램 보안을 지정합니다. 전송 계층에는 제공되는 보안이 없습니다. 이는 다른 표준 바인딩에 의해 제공되는 보안과 비슷합니다.<br />-Both: 전송 및 SOAP 메시징 계층 모두에 보안을 제공 합니다. 두 수준 모두에서 동일한 자격 증명이 필요합니다.<br /><br /> 기본값은 Transport입니다. 이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<메시지 >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|SOAP 메시지 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.|  
|[\<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|MSMQ 전송의 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|바인딩|바인딩 요소는 [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [서비스 및 클라이언트 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<바인딩 >](../../../../../docs/framework/misc/binding.md)  
 [WCF의 큐](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
