---
title: "이진 Serialization | Microsoft Docs"
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
  - "이진 serialization"
  - "이진 serialization, serialization 정보"
  - "deserialization"
  - "serialization, serialization 정보"
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 이진 Serialization
serialization은 개체의 상태를 저장 매체에 저장하는 프로세스로 정의됩니다.이 프로세스 도중 클래스가 포함된 어셈블리를 포함하여 개체의 public 및 private 필드와 클래스의 이름을 바이트의 스트림으로 변환한 다음 데이터 스트림에 씁니다.그런 다음 개체가 deserialize되면 원본 개체의 정확한 복제본이 만들어집니다.  
  
 개체 지향적 환경에서 serialization 메커니즘을 구현할 때는 사용 편의성과 유연성 사이에서 균형을 조정해야 합니다.프로세스를 충분히 제어할 수 있으면 프로세스의 많은 부분을 자동화할 수 있습니다.예를 들어 단순한 이진 serialization로 충분하지 않거나 클래스의 필드를 serialize해야 하는 것으로 결정할 특별한 이유가 있는 상황이 발생할 수 있습니다.다음 단원에서는 .NET Framework에서 제공하는 강력한 serialization 메커니즘을 살펴보고 프로세스를 필요에 따라 사용자 지정할 수 있는 몇 가지 중요한 기능을 강조합니다.  
  
> [!NOTE]
>  UTF\-8 또는 UTF\-7로 인코딩된 개체가 서로 다른 .NET Framework 버전을 사용하여 serialize되고 deserialize될 경우 해당 개체의 상태는 유지되지 않습니다.  
  
## 단원 내용  
 [Serialization 개념](../../../docs/framework/serialization/serialization-concepts.md)  
 serialization이 유용하게 사용되는 두 가지 경우, 즉 저장소에 데이터를 유지할 경우와 응용 프로그램 도메인에 개체를 전달할 경우에 대해 설명합니다.  
  
 [기본 Serialization](../../../docs/framework/serialization/basic-serialization.md)  
 이진 및 SOAP 포맷터를 사용하여 개체를 serialize하는 방법을 설명합니다.  
  
 [선택적 Serialization](../../../docs/framework/serialization/selective-serialization.md)  
 클래스의 일부 멤버가 serialize되는 것을 방지하는 방법을 설명합니다.  
  
 [사용자 지정 Serialization](../../../docs/framework/serialization/custom-serialization.md)  
 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 사용하여 클래스에 대한 serialization을 사용자 지정하는 방법을 설명합니다.  
  
 [Serialization 과정의 단계](../../../docs/framework/serialization/steps-in-the-serialization-process.md)  
 포맷터에서 <xref:System.Runtime.Serialization.Formatter.Serialize%2A> 메서드가 호출될 때 serialization이 수행하는 작업을 설명합니다.  
  
 [버전 독립적 Serialization](../../../docs/framework/serialization/version-tolerant-serialization.md)  
 응용 프로그램에서 예외가 throw되는 것을 방지하면서 시간 경과에 따라 수정할 수 있는 serialize 가능 형식을 만드는 방법을 설명합니다.  
  
 [Serialization 지침](../../../docs/framework/serialization/serialization-guidelines.md)  
 개체를 serialize하는 시점을 결정하기 위한 일반 지침을 제공합니다.  
  
## 참조  
 <xref:System.Runtime.Serialization>  
 개체를 serialize하거나 deserialize하는 데 사용할 수 있는 클래스를 포함합니다.  
  
## 관련 단원  
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 공용 언어 런타임에 포함된 XML serialization 메커니즘을 설명합니다.  
  
 [보안 및 Serialization](../../../docs/framework/misc/security-and-serialization.md)  
 serialization을 수행하는 코드를 쓸 때 따를 보안 코딩 지침을 설명합니다.  
  
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)  
 .NET Framework에서 원격 통신에 사용할 수 있는 다양한 통신 방법에 대해 설명합니다.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/ko-kr/1e64af78-d705-4384-b08d-591a45f4379c)  
 ASP.NET을 사용하여 만든 XML Web services를 프로그래밍하는 방법을 설명하는 항목을 제공합니다.