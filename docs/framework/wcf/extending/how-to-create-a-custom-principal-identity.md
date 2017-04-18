---
title: "방법: 사용자 지정 보안 주체 ID 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IAuthorizationPolicy"
  - "IPrincipal"
  - "PrincipalPermissionAttribute"
  - "PrincipalPermissionMode"
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: 사용자 지정 보안 주체 ID 만들기
<xref:System.Security.Permissions.PrincipalPermissionAttribute>는 서비스 메서드에 대한 액세스를 제어하는 선언적 수단입니다.  이 특성을 사용하는 경우 <xref:System.ServiceModel.Description.PrincipalPermissionMode> 열거는 권한 부여를 검사하기 위한 모드를 지정합니다.  이 모드를 <xref:System.ServiceModel.Description.PrincipalPermissionMode>으로 설정하면 사용자가 <xref:System.Threading.Thread.CurrentPrincipal%2A> 속성에 의해 반환된 사용자 지정 <xref:System.Security.Principal.IPrincipal> 클래스를 지정할 수 있습니다.  이 항목에서는 <xref:System.ServiceModel.Description.PrincipalPermissionMode>이 사용자 지정 권한 부여 정책 및 사용자 지정 보안 주체와 함께 사용되는 시나리오를 보여 줍니다.  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 사용에 대한 자세한 내용은 [방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)을 참조하세요.  
  
## 예제  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## 코드 컴파일  
 코드를 컴파일하려면 다음 네임스페이스에 대한 참조가 필요합니다.  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>   
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)   
 [방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)