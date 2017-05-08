---
title: "선택적 Serialization | Microsoft Docs"
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
  - "이진 serialization, 선택적 serialization"
  - "serialization, 선택적 serialization"
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 선택적 Serialization
클래스에는 흔히 serialize하지 않아야 하는 필드가 있습니다.예를 들어 클래스가 멤버 변수에 스레드 ID를 저장하는 경우입니다.클래스가 deserialize되면 클래스가 serialize된 시점에 대한 ID가 저장된 스레드가 더 이상 실행 중이지 않을 수 있으므로 이 값을 serialize하는 것은 의미가 없습니다.다음과 같이 멤버 변수를 [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic) 특성으로 표시하여 해당 변수가 serialize되는 것을 방지할 수 있습니다.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```  
  
 가능한 경우 보안에 민감한 데이터가 포함될 수 있는 개체는 serialize할 수 없게 만드십시오.개체를 serialize할 수 있어야 하는 경우에는 중요한 데이터가 저장되는 특정 필드에 **NonSerialized** 특성을 적용하십시오.이러한 필드를 serialization에서 제외하지 않는 경우에는 저장되는 데이터가 serialize 권한이 있는 모든 코드에 노출됩니다.보안 serialization 코드 작성에 대한 자세한 내용은 [보안 및 Serialization](../../../docs/framework/misc/security-and-serialization.md)를 참조하십시오.  
  
## 참고 항목  
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [보안 및 Serialization](../../../docs/framework/misc/security-and-serialization.md)