---
title: "Serialization 개념 | Microsoft Docs"
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
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Serialization 개념
serialization을 사용하는 이유는 무엇입니까?가장 중요한 두 가지 이유는 이후 단계에서 정확한 복사본을 다시 만들 수 있도록 저장 매체에 개체의 상태를 유지하는 것과 개체를 한 응용 프로그램 도메인에서 다른 응용 프로그램 도메인으로 값으로 전송하는 것입니다.예를 들어 serialization을 사용하여 세션 상태를 ASP.NET에 저장하고 개체를 Windows Forms의 클립보드로 복사할 수 있습니다.또한 Remoting에서 이를 사용하여 개체를 한 응용 프로그램 도메인에서 다른 응용 프로그램 도메인으로 값으로 전달할 수도 있습니다.  
  
## 단원 내용  
 [영구 저장소](../../../docs/framework/serialization/persistent-storage.md)  
 개체 serialize의 필요성을 설명합니다.  
  
 [값에 의한 마샬링](../../../docs/framework/serialization/marshal-by-value.md)  
 값에 의한 마샬링 프로세스에 대해 설명합니다.  
  
## 관련 단원  
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)  
 공용 언어 런타임에 포함된 이진 serialization 메커니즘을 설명합니다.  
  
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)  
 .NET Framework에서 원격 통신에 사용할 수 있는 다양한 통신 방법에 대해 설명합니다.  
  
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 공용 언어 런타임에 포함된 XML 및 SOAP serialization 메커니즘을 설명합니다.