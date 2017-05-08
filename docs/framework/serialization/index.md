---
title: "Serialization | Microsoft Docs"
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
  - "개체, serialization"
  - "serialization"
  - "개체 serialize"
  - "XML serialization, 정의"
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Serialization
serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다.serialization과 짝을 이루는 것은 스트림을 개체로 변환하는 deserialization입니다.이 두 프로세스를 통해 데이터를 쉽게 저장하고 전송할 수 있습니다.  
  
 .NET Framework에서는 다음 두 가지의 serialization 기술이 있습니다.  
  
-   이진 serialization은 형식 정확도를 유지하므로 응용 프로그램의 여러 호출 간에 개체 상태를 유지하는 데 유용합니다.예를 들어, 개체를 클립보드로 serialize하면 여러 응용 프로그램 간에 개체를 공유할 수 있습니다.개체를 스트림, 디스크, 메모리, 네트워크 등으로 serialize할 수 있습니다.Remoting에서는 serialization을 사용하여 한 컴퓨터 또는 응용 프로그램 도메인의 개체를 다른 컴퓨터 또는 응용 프로그램 도메인으로 "값으로" 전달합니다.  
  
-   XML serialization은 public 속성과 필드만 serialize하며 형식 정확도를 유지하지 않습니다.데이터를 사용하는 응용 프로그램을 제한하지 않고 데이터를 제공하거나 사용하려고 할 때 유용합니다.XML은 공개 표준이기 때문에 웹을 통해 정보를 공유할 때 적합합니다.SOAP도 마찬가지로 공개 표준이어서 적합한 선택입니다.  
  
## 단원 내용  
 [Serialization 방법 항목](../../../docs/framework/serialization/serialization-how-to-topics.md)  
 이 단원에 포함된 방법 항목에 대한 링크를 나열합니다.  
  
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)  
 공용 언어 런타임에 포함된 이진 serialization 메커니즘을 설명합니다.  
  
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 공용 언어 런타임에 포함된 XML 및 SOAP serialization 메커니즘을 설명합니다.  
  
 [Serialization 도구](../../../docs/framework/serialization/serialization-tools.md)  
 이러한 도구는 serialization 코드를 개발하는 데 도움이 됩니다.  
  
 [Serialization 샘플](../../../docs/framework/serialization/serialization-samples.md)  
 이러한 샘플에서는 serialization을 수행하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.Runtime.Serialization>  
 개체를 serialize하거나 deserialize하는 데 사용할 수 있는 클래스를 포함합니다.  
  
 <xref:System.Xml.Serialization>  
 개체를 XML 형식 문서 또는 스트림으로 serialize하는 데 사용할 수 있는 클래스를 포함합니다.  
  
## 관련 단원  
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)  
 .NET Framework에서 원격 통신에 사용할 수 있는 다양한 통신 방법에 대해 설명합니다.  
  
 [Advanced Development Technologies](http://msdn.microsoft.com/ko-kr/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 .NET Framework의 복잡한 개발 작업 및 기술에 대한 자세한 내용을 볼 수 있는 링크를 제공합니다.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/ko-kr/1e64af78-d705-4384-b08d-591a45f4379c)  
 ASP.NET을 사용하여 만든 XML Web services를 프로그래밍하는 방법을 설명하는 항목을 제공합니다.