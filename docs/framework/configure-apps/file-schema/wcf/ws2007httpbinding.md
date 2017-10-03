---
title: '&lt;ws2007HttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
caps.latest.revision: 14
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4eff0a30723d8122e895b73b106c136724c7a7d7
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="ltws2007httpbindinggt"></a>&lt;ws2007HttpBinding&gt;
올바른 버전의 <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> 및 <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> 바인딩 요소를 지원하는 상호 운용 가능한 바인딩을 정의합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<ws2007HttpBinding >  
  
## <a name="syntax"></a>구문  
  
```xml  
<ws2007HttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
  
textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
        <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string"   
                                />  
          <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"  
           negotiateServiceCredential="Boolean"  
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
           establishSecurityContext="Boolean"   
           negotiateServiceCredential="Boolean"/>  
        </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</ws2007HttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`allowCookies`|클라이언트가 쿠키를 수락하고 그러한 쿠키를 이후 요청에 전파할지 여부를 나타내는 값입니다. 기본값은 `false`입니다.<br /><br /> 쿠키를 사용하는 ASP.NET 웹 서비스(ASMX)와 상호 작용할 때 이 속성을 사용할 수 있습니다. 이 속성을 사용하면 서버에서 반환하는 쿠키가 해당 서비스에 대한 이후의 모든 클라이언트 요청에 자동으로 복사됩니다.|  
|`bypassProxyOnLocal`|로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다. 기본값은 `false`입니다.|  
|`closeTimeout`|닫기 작업을 완료하기 위한 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
|`hostnameComparisonMode`|URI(Uniform Resource Identifier) 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다. 이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다. 기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.|  
|`maxBufferPoolSize`|이 바인딩에 대한 최대 버퍼 풀 크기입니다. 기본값은 524,288바이트(512 x 1,024)입니다. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 많은 부분에서 버퍼를 사용합니다. 버퍼가 필요할 때마다 버퍼를 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 비용도 무시할 수 없습니다. 버퍼 풀이 있으면 이 풀에서 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다. 따라서 버퍼를 만들고 삭제하는 오버헤드를 피할 수 있습니다.|  
|`maxReceivedMessageSize`|이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(헤더 포함)로 단위는 바이트입니다. 이 한도를 초과하는 메시지를 보낸 발신자는 SOAP 오류를 받습니다. 수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다. 기본값은 65536입니다.|  
|`messageEncoding`|메시지를 인코딩하는 데 사용되는 인코더를 정의합니다. 유효한 값은 다음과 같습니다.<br /><br /> -   `Text`: 텍스트 메시지 인코더를 사용 합니다.<br />-   `Mtom`: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.<br /><br /> 기본값은 `Text`입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.|  
|`name`|바인딩의 구성 이름입니다. 이 값은 바인딩의 ID로 사용되므로 고유해야 합니다. [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다. 기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.|  
|`openTimeout`|열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
|`proxyAddress`|HTTP 프록시의 주소를 지정하는 URI입니다. `useSystemWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다. 기본값은 `null`입니다.|  
|`receiveTimeout`|받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
|`sendTimeout`|보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
|`textEncoding`|바인딩에서 메시지를 내보내는 데 사용할 문자 집합 인코딩을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -   `UnicodeFffeTextEncoding`: 유니코드 Big Endian 인코딩.<br />-   `Utf16TextEncoding`: 16 비트 인코딩입니다.<br />-   `Utf8TextEncoding`: 8 비트 인코딩입니다.<br /><br /> 기본값은 `Utf8TextEncoding`입니다.<br /><br /> 이 특성은 <xref:System.Text.Encoding> 형식입니다.|  
|`transactionFlow`|바인딩에서 WS-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다. 기본값은 `false`입니다.|  
|`useDefaultWebProxy`|시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 값입니다. 기본값은 `true`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|바인딩에 대한 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 형식입니다.|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.|  
|[reliableSession](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|채널 끝점 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<바인딩 >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.|  
  
## <a name="remarks"></a>설명  
 `WS2007HttpBinding`은 `WSHttpBinding`과 비슷한 시스템 제공 바인딩을 추가하지만, OASIS(Organization for the Advancement of Structured Information Standards) 표준 버전의 ReliableSession, Security 및 TransactionFlow 프로토콜을 사용합니다. 이 바인딩을 사용할 때는 개체 모델이나 기본 설정을 변경할 필요가 없습니다.  
  
## <a name="example"></a>예제  
  
```xml  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <ws2007HttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://www.contoso.com"  
                    textEncoding="utf-16"  
                    useDefaultWebProxy="false">  
                    <reliableSession ordered="false"  
                         inactivityTimeout="00:02:00"  
                         enabled="true" />  
                    <security mode="Transport">  
                         <transport clientCredentialType="Digest"  
                            proxyCredentialType="None"  
                            realm="someRealm" />  
                         <message clientCredentialType="Windows"  
                            negotiateServiceCredential="false"  
                            algorithmSuite="Aes128"   
                            defaultProtectionLevel="None" />  
                    </security>  
                </binding>  
           </ws2007HttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.WS2007HttpBinding>   
 <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<바인딩 >](../../../../../docs/framework/misc/binding.md)

