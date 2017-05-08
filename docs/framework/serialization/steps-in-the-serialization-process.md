---
title: "Serialization 과정의 단계 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "이진 serialization, 단계"
  - "serialization, 단계"
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Serialization 과정의 단계
[Serialize](frlrfSystemRuntimeSerializationFormatterClassSerializeTopic) 메서드가 [포맷터](frlrfSystemRuntimeSerializationFormatterClassTopic)에서 호출되면 개체 serialization이 다음 규칙 시퀀스에 따라 진행됩니다.  
  
-   포맷터에 서로게이트 선택기가 있는지 여부를 검사합니다.포맷터에 서로게이트 선택기가 있는 경우에는 서로게이트 선택기가 지정된 형식의 개체를 처리하는지 검사합니다.선택기가 개체 형식을 처리하는 경우에는 서로게이트 선택기에 대해 **ISerializable.GetObjectData**가 호출됩니다.  
  
-   서로게이트 선택기가 없거나 개체 형식을 처리하지 않는 경우에는 개체가 [Serializable](frlrfSystemSerializableAttributeClassTopic) 특성으로 표시되었는지 여부를 확인하는 검사가 수행됩니다.개체가 표시되지 않은 경우에는 [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic)이 throw됩니다.  
  
-   개체가 적절하게 표시된 경우에는 개체가 [ISerializable](frlrfSystemRuntimeSerializationISerializableClassTopic) 인터페이스를 구현하는지 여부를 검사합니다.이 인터페이스를 구현하는 경우에는 개체에 대해 [GetObjectData](frlrfSystemRuntimeSerializationISerializableClassGetObjectDataTopic)가 호출됩니다.  
  
-   개체가 **ISerializable**을 구현하지 않는 경우에는 기본 serialization 정책이 사용되어 [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic)로 표시되지 않은 모든 필드를 serialize합니다.  
  
## 참고 항목  
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)