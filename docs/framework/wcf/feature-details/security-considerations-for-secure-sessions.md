---
title: 보안 세션에 대한 보안 고려 사항
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f4ee56204d6980f412b9781868714dedb3c2675c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497492"
---
# <a name="security-considerations-for-secure-sessions"></a>보안 세션에 대한 보안 고려 사항
보안 세션 구현 시 보안에 영향을 주는 다음 항목에 대해 고려해야 합니다. 보안 고려 사항에 대 한 자세한 내용은 참조 [보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) 및 [보안에 대 한 유용한](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)합니다.  
  
## <a name="secure-sessions-and-metadata"></a>보안 세션 및 메타데이터  
 보안 세션이 설정 될 때 및 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> 속성이 `false`, Windows Communication Foundation (WCF) 보냅니다는 `mssp:MustNotSendCancel` 에 대 한 설명 언어 WSDL (웹 서비스) 문서에서 메타 데이터의 일부로 어설션은 서비스 끝점입니다. 이`mssp:MustNotSendCancel` 어설션은 서비스가 보안 세션 취소 요청에 응답하지 않음을 클라이언트에게 알립니다. 때는 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> 속성이로 설정 되어 `true`, WCF를 생성 하지 않도록 한 다음는 `mssp:MustNotSendCancel` WSDL 문서에 어설션 합니다. 클라이언트에서 보안 세션이 더 이상 필요하지 않으면 취소 요청을 서비스에 보내야 합니다. 클라이언트를 사용 하 여 생성 될 때는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), 클라이언트 코드의 유무에 적절 하 게 반응 하는 `mssp:MustNotSendCancel` 어설션 합니다.  
  
## <a name="secure-conversations-and-custom-tokens"></a>보안 대화 및 사용자 지정 토큰  
 WS-SecureConversation 사양의 정의로 인해 사용자 지정 토큰과 파생 키를 함께 사용할 때 문제가 발생할 수 있습니다. 사양에 따르면 `wsse:SecurityTokenReference` 파생된 토큰을 참조 하는 선택적 요소: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` 이 선택적 요소는 보안 컨텍스트 토큰, 보안 토큰 또는 파생에 사용 되는 공유 키/암호를 지정 하는 데 사용 됩니다. 이 요소를 지정하지 않으면 받는 사람이 메시지 컨텍스트를 통해 공유 키를 확인할 수 있다고 간주됩니다. 컨텍스트를 확인할 수 없는 경우와 같은 오류가 다음 `wsc:UnknownDerivationSource` 발생 해야 합니다. "  
  
 즉, 사용자 지정 토큰이 파생되게 하려면 해당 절 형식을 `SecurityTokenReference` 요소 내에 래핑해야 합니다. 파생을 해제하는 옵션도 있지만 키를 파생시키는 것이 기본값입니다. 키를 래핑하지 못하면 파생 키 토큰을 serialize하는 작업이 성공하지만 이를 deserialize하면 예외가 throw됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [보안을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
