---
title: "동작 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# 동작 보안
이 단원에는 서비스 동작에 대한 보안을 구성하는 방법을 보여 주는 샘플이 포함되어 있습니다.  
  
## 단원 내용  
 [Service Auditing Behavior](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 이 샘플에서는 서비스 작업 중에 서비스 이벤트 감사를 활성화하기 위해 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 사용하는 방법을 보여 줍니다.  
  
 [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 이 샘플에서는 서비스에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 및 역할 공급자를 사용하여 클라이언트를 인증하고 권한을 부여하는 방법을 보여 줍니다.  
  
 [Authorizing Access to Service Operations](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 이 샘플에서는 [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)를 사용하여 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 통해 서비스 작업에 대한 액세스 권한을 부여하는 방법을 보여 줍니다.  
  
 [Impersonating the Client](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 이 샘플에서는 서비스가 호출자를 대신하여 시스템 리소스에 액세스할 수 있도록 서비스에서 호출자 응용 프로그램을 가장하는 방법을 보여 줍니다.