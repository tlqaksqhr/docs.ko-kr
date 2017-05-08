---
title: "방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# 방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에는 클라이언트와 서버가 서로를 인증하는 데 사용되는 모드가 몇 가지 있습니다.<xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스에 static 메서드를 사용하거나 다음 예제처럼 구성을 통해 이러한 인증 모드의 보안 바인딩 요소를 만들 수 있습니다.  
  
 18가지 인증 모드[!INCLUDE[crabout](../../../../includes/crabout-md.md)][SecurityBindingElement 인증 모드](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)를 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 다양한 인증 모드의 바인딩을 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.ServiceModel.Channels.SecurityBindingElement> 개체의 인스턴스를 만들면 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> 및 <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A> 등의 여러 속성을 변경할 수 없게 됩니다.이러한 속성에서 `set`을 호출해도 해당 속성은 변경되지 않습니다.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## 참고 항목  
 [SecurityBindingElement 인증 모드](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)   
 [방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)