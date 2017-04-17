---
title: "&lt;ws2007FederationHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;ws2007FederationHttpBinding&gt;
[\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)에서 파생되며 페더레이션 보안을 지원하는 안전하고 상호 운용 가능한 바인딩입니다.  
  
## 구문  
  
```  
  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                issuedTokenType="string"  
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</ws2007FederationHttpBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`bypassProxyOnLocal`|로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다.  기본값은 `false`입니다.|  
|`closeTimeout`|닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|`hostnameComparisonMode`|URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.  이 특성은 <xref:System.ServiceModel.HostnameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.  기본값은 <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.|  
|`maxBufferPoolSize`|이 바인딩에 대한 최대 버퍼 풀 크기입니다.  기본값은 524,288바이트\(512 \* 1024\)입니다.  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 많은 부분에서 버퍼를 사용합니다.  버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.  버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.  따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.|  
|`maxReceivedMessageSize`|이 바인딩으로 구성된 채널에서 받을 수 있는 헤더를 비롯한 최대 메시지 크기\(바이트\)입니다.  이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.  수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.  기본값은 65536입니다.|  
|`messageEncoding`|메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   Text: 텍스트 메시지 인코더를 사용합니다.<br />-   Mtom: MTOM\(Message Transmission Organization Mechanism\) 1.0 인코더를 사용합니다.<br /><br /> 기본값은 Text입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.|  
|`name`|바인딩의 구성 이름입니다.  이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.  [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.  기본 구성 및 이름 없는 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하세요.|  
|`openTimeout`|열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|`privactyNoticeAt`|개인 정보 알림이 있는 URI입니다.|  
|`privactyNoticeVersion`|현재 개인 정보 알림의 버전입니다.|  
|`proxyAddress`|HTTP 프록시의 주소를 지정하는 URI입니다.  `useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.  기본값은 `null`입니다.|  
|`receiveTimeout`|받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:10:00입니다.|  
|`sendTimeout`|보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|`textEncoding`|바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   BigEndianUnicode: 유니코드 Big Endian 인코딩<br />-   Unicode: 16비트 인코딩<br />-   UTF8: 8비트 인코딩<br /><br /> 기본값은 UTF8입니다.  이 특성은 <xref:System.Text.Encoding> 형식입니다.|  
|`transactionFlow`|바인딩에서 WS\-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다.  기본값은 `false`입니다.|  
|`useDefaultWebProxy`|시스템의 자동 구성된 HTTP 프록시 사용 여부를 나타내는 값입니다.  이 특성이 `true`이면 프록시 주소는 `null`이어야 합니다\(설정되지 않음\).  기본값은 `true`입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|메시지에 대한 보안 설정을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 형식입니다.|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.|  
|[reliableSession](http://msdn.microsoft.com/ko-kr/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|채널 끝점 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<bindings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.|  
  
## 설명  
 페더레이션은 인증 및 권한 부여를 위해 여러 회사나 트러스트 도메인 간에 ID를 공유하는 기능입니다.  WS\-Trust 프로토콜을 사용하여 ID 표현을 트러스트 도메인 간에 매핑합니다.  페더레이션 HTTP 바인딩은 SOAP 보안과 혼합 모드 보안을 지원하지만 전송 보안을 지원하지는 않습니다.  이 바인딩으로 구성된 서비스는 HTTP 전송을 사용해야 합니다.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
## 예제  
  
```  
<configuration>  
<system.ServiceModel>  
<bindings>  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://www.contoso.com"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.WS2007FederationHttpBinding>   
 <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>   
 [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)