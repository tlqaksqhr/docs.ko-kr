---
title: "영구 저장소 | Microsoft Docs"
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
  - "이진 serialization, 영구 저장소"
  - "영구 저장소"
  - "serialization, 영구 저장소"
ms.assetid: b112c0dd-93e2-4eef-908d-5963f80bab65
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 영구 저장소
개체의 필드 값을 디스크에 저장하고 나중에 이 데이터를 검색하는 것이 필요할 경우가 많습니다.serialization을 사용하지 않고 쉽게 구현할 수 있는 기능이지만 이 방식은 불편하고 오류가 발생하기 쉬우며 개체의 계층 구조를 추적해야 할 때는 점점 더 복잡해 집니다.수천 개의 개체가 있으며 각 개체마다 필드와 속성을 디스크에 저장하고 복원하는 코드를 작성해야 하는 대규모 비즈니스 응용 프로그램을 가정해 보십시오.serialization을 사용하면 이러한 목표를 편리하게 달성할 수 있습니다.  
  
 공용 언어 런타임은 개체가 메모리에 저장되는 방식을 관리하며 [reflection](../../../docs/framework/reflection-and-codedom/reflection.md)을 사용하여 자동화된 serialization 메커니즘을 제공합니다.개체가 serialize될 때 클래스의 이름, 어셈블리 및 클래스 인스턴스의 모든 데이터 멤버가 저장소에 기록됩니다.개체는 다른 인스턴스에 대한 참조를 멤버 변수에 저장할 경우가 있습니다.클래스가 serialize될 때 serialization 엔진은 이미 serialize된 참조되는 개체를 추적하여 동일한 개체가 두 번 이상 serialize되는 것을 방지합니다.[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 제공되는 serialization 아키텍처는 개체 그래프와 순환 참조를 자동으로 적절하게 처리합니다.개체 그래프에 대한 유일한 요구 사항은 serialize된 개체가 참조하는 모든 개체도 [Serializable](frlrfSystemSerializableAttributeClassTopic)로 표시되어야 한다는 점입니다. 자세한 내용은 [기본 Serialization](../../../docs/framework/serialization/basic-serialization.md)을 참조하십시오.이렇게 되지 않으면 serializer가 표시되지 않은 개체를 serialize하려고 시도할 때 예외가 throw됩니다.  
  
 serialize된 클래스가 deserialize될 때는 클래스가 다시 만들어지고 모든 데이터 멤버의 값이 자동으로 복원됩니다.  
  
## 참고 항목  
 [Serialization 개념](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)