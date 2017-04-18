---
title: "서비스 및 클라이언트에 보안 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "메시지 보안 [WCF]"
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# 서비스 및 클라이언트에 보안 설정
이 단원의 정보는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 보안 프로그래밍에 중점을 둡니다.  일반적으로 여기에는 적절한 시스템 제공 바인딩 선택, 보안 요소의 속성 설정 및 서비스나 클라이언트에서 사용할 자격 증명을 검색하는 방법을 제어하는 서비스 동작의 속성 설정이 포함됩니다.  이러한 기술은 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)에 표시된 대부분의 시나리오에서 사용자의 보안 요구 사항을 대부분 처리합니다.  시나리오에 추가 기능이 필요한 경우 먼저 [사용자 지정 바인딩을 사용하는 보안 기능](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)을 참조하세요. 솔루션이 확실하지 않으면 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)을 참조하세요.  다양한 클레임을 사용하는 시스템을 만들거나 상호 운용하는 경우 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)의 항목을 참조하세요.  
  
## 단원 내용  
 [WCF 보안 프로그래밍](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 메시지 보안을 설정하는 데 사용되는 프로그래밍 모델의 개요입니다.  
  
 [전송 보안 개요](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 전송 계층에서 메시지 보안을 설정하는 방법의 개요입니다.  
  
 [메시지 보안](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 메시지 수준 보안을 사용하는 이유를 요약합니다.  
  
 [보안 세션](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 세션의 보안을 설정할 때 고려할 사항에 대해 설명합니다.  
  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 X.509 인증서를 사용할 때 필요한 일반 작업 중 일부에 대해 설명합니다.  
  
## 참조  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## 관련 단원  
 [보안 개념](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [바인딩 및 보안](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [사용자 지정 바인딩을 사용하는 보안 기능](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## 참고 항목  
 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)   
 [Windows Server AppFabric에 대한 보안 모델](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)