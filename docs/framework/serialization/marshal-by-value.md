---
title: "값에 의한 마샬링 | Microsoft Docs"
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
  - "이진 serialization, 값에 의한 마샬링"
  - "값에 의한 마샬링 개체"
  - "serialization, 값에 의한 마샬링"
ms.assetid: ee91e8f0-92e0-4732-8015-d17dee154be1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 값에 의한 마샬링
개체는 해당 개체가 만들어진 응용 프로그램 도메인에서만 유효합니다.개체를 매개 변수로 전달하거나 결과로 반환하려고 하는 시도는 개체가 [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic)에서 파생되거나 [Serializable](frlrfSystemSerializableAttributeClassTopic)로 표시된 경우 이외에는 실패합니다.개체가 **Serializable**로 표시된 경우 개체는 자동으로 serialize되고, 하나의 응용 프로그램 도메인에서 다른 응용 프로그램 도메인으로 전송된 다음, deserialize되어 두 번째 응용 프로그램 도메인에서 개체의 정확한 복사본을 생성합니다.이 프로세스를 일반적으로 값에 의한 마샬링이라고 합니다.  
  
 개체가 **MarshalByRefObject**에서 파생되는 경우 개체 자체가 아니라 개체 참조가 한 응용 프로그램 도메인에서 다른 응용 프로그램 도메인으로 전달됩니다.**MarshalByRefObject**에서 파생되는 개체를 **Serializable**로 표시할 수도 있습니다.이 개체를 Remoting에 사용하면 서로게이트 선택기\([SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)\)로 미리 구성된 serialization 담당 포맷터가 serialization 프로세스를 제어하고, [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic)에서 파생된 모든 개체를 프록시로 바꿉니다.[SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)가 없으면 serialization 아키텍처는 [Serialization 과정의 단계](../../../docs/framework/serialization/steps-in-the-serialization-process.md)에서 설명하는 표준 serialization 규칙을 따릅니다.  
  
## 참고 항목  
 [Serialization 개념](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)