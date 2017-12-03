---
title: "WCF에서 권한 부여"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a08627e213196c2d5fb296f458a5d3a8c7bb1a0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="authentication-in-wcf"></a>WCF에서 권한 부여
다음 항목에서는 Windows 인증, X.509 인증서 및 사용자 이름과 암호와 같은 인증을 제공하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 다양한 메커니즘을 보여 줍니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: ASP.NET 멤버 자격 공급자를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 ASP.NET 기능에는 멤버 자격 및 역할 공급자, 인증에 필요한 사용자 이름/암호 쌍을 저장할 데이터베이스 및 권한 부여를 위한 사용자 역할이 포함되어 있습니다. 이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 동일한 데이터베이스를 사용하여 사용자를 인증하고 권한을 부여하는 방법에 대해 설명합니다.  
  
 [방법: 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 사용자 지정 사용자 이름/암호 유효성 검사기를 통합하는 방법에 대해 보여 줍니다.  
  
 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 에서는 추가적인 보호 수단으로 클라이언트를 인증할 수 서비스 예상 된을 지정 하 여 *identity* 서비스입니다. 예상 ID 및 서비스에서 반환한 ID가 서로 일치하지 않으면 인증되지 않습니다.  
  
 [보안 협상 및 시간 제한](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 클래스의 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> 속성을 사용하는 방법에 대해 설명합니다.  
  
 [Windows 인증 오류 디버깅](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Windows 인증을 사용할 때 일반적으로 발생하는 문제에 대해 중점적으로 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>관련 단원  
 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>참고 항목  
 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Windows Server App Fabric에 대 한 보안 모델](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
