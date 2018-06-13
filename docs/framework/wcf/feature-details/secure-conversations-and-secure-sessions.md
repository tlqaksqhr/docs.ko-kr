---
title: 보안 대화 및 보안 세션
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c87f53bcaa167dd7b3b039c70129efca43742c1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497609"
---
# <a name="secure-conversations-and-secure-sessions"></a>보안 대화 및 보안 세션
Windows Communication Foundation (WCF)의 기능은 서로 인증 하 고 암호화 및 디지털 서명 프로세스에 동의 하는 두 개의 끝점 사이 보안 세션을 설정 하는 기능. 예를 들어, 서비스 끝점은 인증을 위해 X.509 인증서에 기반한 보안 토큰을 보낼 클라이언트 끝점이 필요할 수 있습니다. 클라이언트가 인증되면 서비스 끝점은 세션 내의 모든 후속 메시지 보안을 설정하는 데 사용되는 클라이언트에게 SCT(보안 컨텍스트 토큰)를 다시 반환합니다. 이 보안 세션을 설정하면 SCT에 대칭 키가 포함되기 때문에 두 개의 끝점 간에 교환되는 메시지 집합이 훨씬 효율적일 수 있습니다. X.509 인증서가 기준으로 하는 비대칭 키는 디지털 서명을 생성하거나 데이터 집합을 암호화할 때 대칭 키보다 훨씬 더 많은 계산 능력이 필요합니다.  
  
 부트스트랩 정책 (의 6.2.7 섹션에 정의 된 [Ws-securitypolicy](http://go.microsoft.com/fwlink/?LinkId=99817) 표준) 채널을 보호 하 고 RST/SCT 및 RSTR/SCT 교환 하기 전에 클라이언트를 인증 하는 데 사용 하는 메시지 보안 어설션을 포함 합니다. 특정 WCF 표준 바인딩에 `Security.Message.EstablishSecurityContext` 여부 보안 대화를 제어 하는 속성을 사용 합니다. 부트스트랩을 통해 중첩 보안 바인딩 요소를 가리키는 사용자 지정 바인딩을 사용 하는 경우 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 구성 파일 또는 호출 하 여 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> 코드에서입니다.  
  
 세션에 대 한 자세한 내용은 참조 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [세션, 인스턴스 및 동시성](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [방법: 세션이 필요한 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
