---
title: "보안 대화 및 보안 세션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# 보안 대화 및 보안 세션
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 특징은 서로를 인증하고 암호화 및 디지털 서명 프로세스에 동의하는 두 개의 끝점 사이에 보안 세션을 설정하는 기능입니다.예를 들어, 서비스 끝점은 인증을 위해 X.509 인증서에 기반한 보안 토큰을 보낼 클라이언트 끝점이 필요할 수 있습니다.클라이언트가 인증되면 서비스 끝점은 세션 내의 모든 후속 메시지 보안을 설정하는 데 사용되는 클라이언트에게 SCT\(보안 컨텍스트 토큰\)를 다시 반환합니다.이 보안 세션을 설정하면 SCT에 대칭 키가 포함되기 때문에 두 개의 끝점 간에 교환되는 메시지 집합이 훨씬 효율적일 수 있습니다.X.509 인증서가 기준으로 하는 비대칭 키는 디지털 서명을 생성하거나 데이터 집합을 암호화할 때 대칭 키보다 훨씬 더 많은 계산 능력이 필요합니다.  
  
 부트스트랩 정책\([WS\-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) 표준의 섹션 6.2.7에 정의됨\)에는 RST\/SCT 및 RSTR\/SCT 교환 이전에 채널을 보안하고 클라이언트를 인증하는 데 사용되는 메시지 보안 어설션이 포함되어 있습니다.특정 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 표준 바인딩에는 보안 대화를 사용할지 여부를 제어하는 `Security.Message.EstablishSecurityContext` 속성이 있습니다.사용자 지정 바인딩을 사용하는 경우 구성 파일의 [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> 을 통해 또는 호출을 통해 보안 바인딩 요소를 중첩하여 부트스트랩을 나타냅니다.  
  
 세션[!INCLUDE[crabout](../../../../includes/crabout-md.md)][세션 사용](../../../../docs/framework/wcf/using-sessions.md)을 참조하십시오.  
  
## 참고 항목  
 [세션, 인스턴스 및 동시성](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [방법: 세션이 필요한 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)