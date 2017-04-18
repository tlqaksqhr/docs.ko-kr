---
title: "&lt;wsDualHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "wsDualHttpBinding 요소"
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# &lt;wsDualHttpBinding&gt;
이중 서비스 계약 또는 SOAP 중간 매개자를 통한 통신에 사용할 수 있도록 보안이 유지되고 신뢰할 수 있으며 상호 운용할 수 있는 바인딩을 정의합니다.  
  
## 구문  
  
```  
  
<wsDualHttpBinding>  
        <binding name="string"  
        closeTimeout="TimeSpan"  
        openTimeout="TimeSpan"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        bypassProxyOnLocal="Boolean"  
        clientBaseAddress="URI"  
        transactionFlow="Boolean"   
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
        proxyAddress="URI"  
  
textEncoding="Unicode/BigEndianUnicode/UTF8"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
            inactivityTimeout="TimeSpan" />  
        <security mode="None/Message">  
           <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
                negotiateServiceCredential="Boolean"  
                    algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />  
                </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</wsDualHttpBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|bypassProxyOnLocal|로컬 주소에 대해 프록시 서버를 사용하지 않을 것인지 여부를 나타내는 부울 값입니다.  기본값은 `false`입니다.|  
|clientBaseAddress|클라이언트가 서비스로부터의 응답 메시지를 수신할 기본 주소를 설정하는 URI입니다.  이 특성을 지정하면 수신에 이 주소와 채널별 GUID가 사용됩니다.  값을 지정하지 않으면 전송별로 클라이언트 기본 주소가 생성됩니다.  기본값은 `null`입니다.|  
|closeTimeout|닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|hostnameComparisonMode|URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.  이 특성은 <xref:System.ServiceModel.HostnameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.  기본값은 <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.|  
|maxBufferPoolSize|이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.  기본값은 524,288바이트\(512 \* 1024\)입니다.  WCF\(Windows Communication Foundation\)의 많은 부분에서 버퍼를 사용합니다.  버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.  버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.  따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.|  
|maxReceivedMessageSize|헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기\(바이트\)를 지정하는 양의 정수입니다.  이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.  수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.  기본값은 65536입니다.|  
|messageEncoding|메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   Text: 텍스트 메시지 인코더를 사용합니다.<br />-   Mtom: MTOM\(Message Transmission Organization Mechanism\) 1.0 인코더를 사용합니다.<br />-   기본값은 Text입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.|  
|name|바인딩의 구성 이름을 포함하는 문자열입니다.  이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.  [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.  기본 구성 및 이름 없는 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하세요.|  
|openTimeout|열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|proxyAddress|HTTP 프록시의 주소를 지정하는 URI입니다.  `useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.  기본값은 `null`입니다.|  
|receiveTimeout|받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|sendTimeout|보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|textEncoding|바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   BigEndianUnicode: 유니코드 BigEndian 인코딩<br />-   Unicode: 16비트 인코딩<br />-   UTF8: 8비트 인코딩<br /><br /> 기본값은 UTF8입니다.  이 특성은 <xref:System.Text.Encoding> 형식입니다.|  
|transactionFlow|바인딩에서 WS\-Transactions 이동을 지원할지 여부를 지정하는 부울 값입니다.  기본값은 `false`입니다.|  
|useDefaultWebProxy|시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 부울 값입니다.  이 특성이 `true`이면 프록시 주소는 `null`이어야 합니다\(설정되지 않음\).  기본값은 `true`입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsdualhttpbinding.md)|바인딩에 대한 보안 설정을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement> 형식입니다.|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.|  
|[reliableSession](http://msdn.microsoft.com/ko-kr/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|채널 끝점 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<bindings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.|  
  
## 설명  
 `WSDualHttpBinding`은 `WSHttpBinding`과 동일하게 웹 서비스 프로토콜을 지원하지만 이중 계약에만 사용할 수 있습니다.  `WSDualHttpBinding`은 SOAP 보안만 지원하며 신뢰할 수 있는 메시징이 필요합니다.  이 바인딩에서는 서비스의 콜백 끝점을 제공하는 공용 URI가 클라이언트에 있어야 합니다.  이 공용 URI는 `clientBaseAddress` 특성에서 제공됩니다.  이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.  클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.  
  
 이 바인딩을 사용하여 하나 이상의 SOAP 중간 매개자를 통해 안정적으로 통신할 수 있습니다.  
  
 이 바인딩은 기본적으로 안정성을 위한 WS\-ReliableMessaging, 메시지 보안 및 인증을 위한 WS\-Security, 메시지 배달을 위한 HTTP 및 텍스트\/XML 메시지 인코딩을 지원하는 런타임 스택을 생성합니다.  
  
## 예제  
  
```  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsDualHttpBinding>  
    <binding   
        closeTimeout="00:00:10"  
        openTimeout="00:00:20"   
        receiveTimeout="00:00:30"  
        sendTimeout="00:00:40"  
        bypassProxyOnLocal="false"   
        clientBaseAddress="http://localhost:8001/client/"  
        transactionFlow="true"   
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="utf-16"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" />  
        <security mode="None">  
            <message clientCredentialType="None"  
                negotiateServiceCredential="false"  
                algorithmSuite="Aes128" />  
        </security>  
    </binding>  
</wsDualHttpBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.WSDualHttpBinding>   
 <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)