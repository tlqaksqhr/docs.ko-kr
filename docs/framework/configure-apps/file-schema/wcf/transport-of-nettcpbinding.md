---
title: "&lt;netTcpBinding&gt;의 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 273d467df5ee97b4803a1843a0b0d86f7244feae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a>&lt;netTcpBinding&gt;의 &lt;transport&gt;
구성 된 끝점에 대 한 메시지 수준 보안 요구 사항 형식을 정의 하는 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.  
  
 \<시스템입니다. ServiceModel >  
\<바인딩 >  
\<netTcpBinding >  
\<바인딩 >  
\<보안 >  
\<전송 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"             sslProtocols="Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|clientCredentialType|선택 사항입니다. 전송 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.<br /><br /> -기본값은 `Windows`합니다.<br />-이 특성은 형식 <xref:System.ServiceModel.TcpClientCredentialType>합니다.|  
|protectionLevel|선택 사항입니다. TCP 전송의 수준에 보안을 정의합니다. 메시지 서명은 메시지 전송 과정에서 제3자가 메시지를 위조할 수 있는 위험을 줄입니다. 암호화는 전송 과정에서 데이터 수준의 개인 정보 보호를 제공합니다.<br /><br /> 기본값은 `EncryptAndSign`입니다.|  
|sslProtocols|지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다. 기본값은 Tls &#124; Tls11 &#124; t l s 12입니다.|  
|policyEnforcement|이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.<br /><br /> 1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).<br />2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.<br />3.  Always – 정책이 항상 적용됩니다. 확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType 특성  
  
|값|설명|  
|-----------|-----------------|  
|없음|클라이언트는 익명입니다. 여기에는 서비스 인증서가 필요합니다.|  
|Windows|SP 협상(Kerberos 협상)을 사용하는 클라이언트의 Windows 인증을 지정합니다.|  
|인증서|클라이언트는 인증서를 사용하여 인증됩니다. 클라이언트에서는 SSL 협상을 사용하며 서비스 인증서가 필요합니다.|  
  
## <a name="protectionlevel-attribute"></a>protectionLevel 특성  
  
|값|설명|  
|-----------|-----------------|  
|없음|보호되지 않습니다.|  
|Sign|메시지가 서명됩니다.|  
|EncryptAndSign|-메시지가 암호화 되 고 서명 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|보안 기능을 지정 된 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.|  
  
## <a name="remarks"></a>설명  
 SOAP 메시지의 무결성 및 기밀성과 상호 인증을 위해 전송 보안을 사용합니다. 바인딩에서 이 보안 모드를 선택하면 보안 전송을 사용하여 채널 스택이 구성되고 Windows(협상) 또는 SSL over TCP 같은 전송 보안을 사용하여 SOAP 메시지가 보안됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.TcpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<바인딩 >](../../../../../docs/framework/misc/binding.md)
