---
title: "BinaryMessageEncodingBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# BinaryMessageEncodingBindingElement
BinaryMessageEncodingBindingElement  
  
## 구문  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## 메서드  
 BinaryMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 BinaryMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
## MaxReadPoolSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.  
  
## MaxSessionSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 인코딩에 사용되는 버퍼의 크기\(바이트\)를 지정하는 값입니다.  
  
## MaxWritePoolSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.  
  
## ReaderQuotas  
 데이터 형식: XmlDictionaryReaderQuotas  
  
 액세스 형식: 읽기 전용  
  
 판독기의 할당량입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>