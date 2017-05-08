---
title: "MtomMessageEncodingBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## 구문  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## 메서드  
 MtomMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 MtomMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### Encoding  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩에서 메시지를 내보낼 때 사용되는 문자 집합 인코딩입니다.  
  
### MaxReadPoolSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.  
  
### MaxWritePoolSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.  
  
### ReaderQuotas  
 데이터 형식: XmlDictionaryReaderQuotas  
  
 액세스 형식: 읽기 전용  
  
 판독기의 할당량입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>