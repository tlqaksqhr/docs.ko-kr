---
title: "보안 세션에 대한 보안 고려 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: be460249ed877b2f67f2d153c2aea4a3cc4d2b37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-considerations-for-secure-sessions"></a>보안 세션에 대한 보안 고려 사항
보안 세션 구현 시 보안에 영향을 주는 다음 항목에 대해 고려해야 합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]보안 고려 사항 참조 [보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) 및 [보안에 대 한 유용한](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)합니다.  
  
## <a name="secure-sessions-and-metadata"></a>보안 세션 및 메타데이터  
 보안 세션을 설정할 때 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> 속성을 `false`로 설정하면, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 `mssp:MustNotSendCancel` 어설션을 서비스 끝점에 대한 WSDL(웹 서비스 기술 언어) 문서의 메타데이터 일부로 보냅니다. 이`mssp:MustNotSendCancel` 어설션은 서비스가 보안 세션 취소 요청에 응답하지 않음을 클라이언트에게 알립니다. <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> 속성을 `true`로 설정하면, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `mssp:MustNotSendCancel` 어설션을 WSDL 문서로 내보내지 않습니다. 클라이언트에서 보안 세션이 더 이상 필요하지 않으면 취소 요청을 서비스에 보내야 합니다. 클라이언트를 사용 하 여 생성 될 때는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), 클라이언트 코드의 유무에 적절 하 게 반응 하는 `mssp:MustNotSendCancel` 어설션 합니다.  
  
## <a name="secure-conversations-and-custom-tokens"></a>보안 대화 및 사용자 지정 토큰  
 WS-SecureConversation 사양의 정의로 인해 사용자 지정 토큰과 파생 키를 함께 사용할 때 문제가 발생할 수 있습니다. 사양에 따르면 `wsse:SecurityTokenReference` 파생된 토큰을 참조 하는 선택적 요소: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` 이 선택적 요소는 보안 컨텍스트 토큰, 보안 토큰 또는 파생에 사용 되는 공유 키/암호를 지정 하는 데 사용 됩니다. 이 요소를 지정하지 않으면 받는 사람이 메시지 컨텍스트를 통해 공유 키를 확인할 수 있다고 간주됩니다. 컨텍스트를 확인할 수 없는 경우와 같은 오류가 다음 `wsc:UnknownDerivationSource` 발생 해야 합니다. "  
  
 즉, 사용자 지정 토큰이 파생되게 하려면 해당 절 형식을 `SecurityTokenReference` 요소 내에 래핑해야 합니다. 파생을 해제하는 옵션도 있지만 키를 파생시키는 것이 기본값입니다. 키를 래핑하지 못하면 파생 키 토큰을 serialize하는 작업이 성공하지만 이를 deserialize하면 예외가 throw됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [보안을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
