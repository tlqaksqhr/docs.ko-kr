---
title: '&lt;mtomMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc7db79f25e2ab202f79f7f4ab5cc2a0e5eb0242
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltmtommessageencodinggt"></a>&lt;mtomMessageEncoding&gt;
SOAP MTOM(Message Transmission Optimization Mechanism) 기반 메시지에 사용되는 인코딩 및 메시지 버전 관리를 지정합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<customBinding >  
\<바인딩 >  
\<mtomMessageEncoding >  
  
## <a name="syntax"></a>구문  
  
```xml  
<mtomMessageEncoding   
   maxBufferSize="Integer"  
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing1/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|maxBufferSize|사용할 수 있는 버퍼의 최대 크기를 지정하는 정수입니다.|  
|maxReadPoolSize|새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다. 풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다. 기본값은 64입니다.|  
|maxWritePoolSize|새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다. 풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다. 기본값은 16입니다.|  
|messageVersion|바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -Soap11Addressing1<br />-Soap12Addressing10<br /><br /> 기본값은 Soap12Addressing10입니다. 이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.|  
|writeEncoding|바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -UnicodeFffeTextEncoding: 유니코드 BigEndian 인코딩<br />-Utf16TextEncoding: 유니코드 인코딩<br />-Utf8TextEncoding: 8 비트 인코딩<br /><br /> 기본값은 Utf8TextEncoding입니다. 이 특성은 <xref:System.Text.Encoding> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<바인딩 >](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>설명  
 인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다. 디코딩은 역프로세스입니다. WCF(Windows Communication Foundation)에서는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM(Message Transmission Optimization Mechanism)이라는 세 가지 형식의 인코딩을 제공합니다.  
  
 `MtomMessageEncoding` 요소는 MTOM(Message Transmission Optimization Mechanism) 인코딩을 사용하는 메시지에 사용되는 문자 인코딩, 메시지 버전 관리 및 기타 설정을 지정합니다. MTOM은 WCF 메시지의 이진 데이터를 전송하기 위한 효율적인 기술입니다. MTOM 인코더는 효율성과 상호 운용성 간의 균형을 유지하려고 합니다. MTOM 인코딩은 대부분의 XML을 텍스트 형식으로 전송하지만, 대량의 이진 데이터 블록의 경우는 base64 인코딩 형식으로 변환하지 않고 있는 그대로 전송하여 최적화합니다.  
  
## <a name="example"></a>예  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap11Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
 [메시지 인코딩](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [메시지 인코더 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
