---
title: "WCF 서비스가 웹 팜에서 호스팅될 경우 재생 공격 방지 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF 서비스가 웹 팜에서 호스팅될 경우 재생 공격 방지
메시지 보안 WCF를 사용할 경우 WCF는 들어오는 메시지에서 NONCE를 만들고 내부 `InMemoryNonceCache`에 생성된 NONCE가 있는지를 확인하여 반복 공격을 방지합니다.그럴 경우 메시지를 반복으로 삭제합니다.WCF 서비스가 웹 팜에 호스팅된 경우 `InMemoryNonceCache`가 웹 팜의 노드에서 공유되지 않으므로 서비스가 반복 공격에 취약합니다.이 시나리오를 완화하기 위해 WCF 4.5는 추상 클래스 <xref:System.ServiceModel.Security.NoneCache>에서 클래스를 파생하여 자체 공유 NONCE 캐시를 구현할 수 있도록 하는 확장성 지점을 제공합니다.  
  
## NoneCache 구현  
 자체 공유 NONCE 캐시를 구현하려면 <xref:System.ServiceModel.Security.NoneCache>에서 클래스를 파생하고 [M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> 및 [M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A> 메서드를 재정의합니다.[M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A>는 캐시에 지정된 NONCE가 있는지 여부를 확인합니다.[M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A>는 NONCE를 캐시에 추가하려고 합니다.클래스가 구현되면 인스턴스를 인스턴스화한 다음 클라이언트 측 재생 검색을 위해 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSecuritySettings.NonceCache%2A>에 할당하고 서버 측 재생 검색을 위해 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSecuritySettings.NonceCache%2A>에 할당하여 연결합니다.이 기능에 대해서는 즉시 구성이 지원되지 않습니다.  
  
## 참고 항목  
 [메시지 보안](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)