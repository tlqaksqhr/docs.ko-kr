---
title: "방법: 서비스 인스턴스 만들기 제어 | Microsoft Docs"
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
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# 방법: 서비스 인스턴스 만들기 제어
서비스의 인스턴스 모드를 설정하면 <xref:System.ServiceModel.InstanceContext?displayProperty=fullName>\(및 연결된 사용자 정의 서비스 개체\)가 만들어지는 시기를 지정할 수 있습니다.  가능한 모드에 대해서는 <xref:System.ServiceModel.InstanceContextMode> 열거형을 참조하세요.  동작에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [동작을 사용하여 런타임 구성 및 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)을 참조하세요.  작업 예제는 [동작](../../../../docs/framework/wcf/samples/behaviors.md)을 참조하세요.  
  
### 코드를 사용하여 서비스 인스턴스 수명을 제어하려면  
  
1.  서비스 클래스에 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 적용합니다.  
  
2.  <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성을 <xref:System.ServiceModel.InstanceContextMode>, <xref:System.ServiceModel.InstanceContextMode> 또는 <xref:System.ServiceModel.InstanceContextMode> 값 중 하나로 설정합니다.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## 예제  
 다음 코드 예제에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성의 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성을 <xref:System.ServiceModel.InstanceContextMode>로 설정합니다.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## 참고 항목  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>   
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>   
 <xref:System.ServiceModel.InstanceContextMode>   
 [Service: Behaviors Samples](http://msdn.microsoft.com/ko-kr/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)