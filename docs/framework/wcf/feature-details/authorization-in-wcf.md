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
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09bbbaad055447103a1153f1888dcae4a511cbeb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="authorization-in-wcf"></a>WCF에서 권한 부여
권한 부여는 서비스나 파일과 같은 리소스에 대한 액세스 및 권한을 제어하는 프로세스입니다. 이 단원의 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 여러 가지 방법으로 기본 작업을 수행하는 방법에 대해 설명합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [액세스 제어 메커니즘](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 권한 부여 메커니즘 및 제안된 사용에 대해 간략히 설명합니다.  
  
 [방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용하여 서비스에 대한 액세스를 제한하는 프로세스를 보여 줍니다.  
  
 [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]의 역할 공급자 기능을 사용할 수 있도록 설정하는 서비스 구성에 대해 설명합니다.  
  
 [방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]은 권한 부여 관리자를 사용하여 웹 사이트의 권한을 관리할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]도 이와 유사하게 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/권한 부여 관리자를 결합 사용하여 클라이언트 권한을 관리할 수 있습니다.  
  
 [클레임 및 권한 부여 Id 모델 관리](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 클레임 기반 권한 부여에 ID 모델 인프라를 사용하는 기본적인 사용법에 대해 설명합니다 .  
  
 [위임 및 가장](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 위임과 가장의 차이점을 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>관련 단원  
 [인증](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>참고 항목  
 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Windows Server App Fabric에 대 한 보안 모델](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
