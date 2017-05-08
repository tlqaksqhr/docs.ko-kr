---
title: "&lt;binaryMessageEncoding&gt; | Microsoft Docs"
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
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;binaryMessageEncoding&gt;
통신 중에 WCF\(Windows Communication Foundation\) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.  
  
## 구문  
  
```  
  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10” />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|maxReadPoolSize|새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.  풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.  기본값은 64입니다.|  
|maxSessionSize|인코딩에 사용되는 버퍼의 크기\(바이트\)를 설정하는 양의 정수입니다.  버퍼가 크면 작업 집합의 크기 문제가 생기지만 인코딩 속도가 빨라집니다.  기본값은 2048입니다.|  
|maxWritePoolSize|새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.  풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.  기본값은 16입니다.|  
|messageVersion|사용되거나 필요한 SOAP 메시지 및 WS\-Addressing 버전을 지정합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 인코딩은 메시지를 바이트 시퀀스로 변환하는 프로세스이고,  디코딩은 역프로세스입니다.  WCF\(Windows Communication Foundation\)에서는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM\(Message Transmission Optimization Mechanism\)이라는 세 가지 형식의 인코딩을 제공합니다.  
  
 `binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS\-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다.  이진 메시지 인코더는 통신 중에 WCF\(Windows Communication Foundation\) 메시지를 이진 형식으로 인코딩합니다.  이 인코딩은 전송 속도가 매우 빠르지만 WS\-\* 표준과 호환되지 않습니다.  
  
## 예제  
  
```  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>   
 [메시지 인코딩](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [메시지 인코더 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)