---
title: '방법: 서비스에서 ASP.NET 역할 공급자 사용'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9180ebe687d61315a66160a6fc95569a0e6b8e72
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>방법: 서비스에서 ASP.NET 역할 공급자 사용
[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자와 함께 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 개발자가 웹 사이트를 만들 수 있는 기능입니다. 이 웹 사이트에서 사용자는 사이트에 계정을 만들고 인증을 위해 역할을 할당받을 수 있습니다. 이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다. 반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다. 대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.  
  
 샘플 응용 프로그램에 대 한 참조 [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)합니다. 에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자 기능 참조 [하는 방법: ASP.NET 멤버 자격 공급자를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)합니다.  
  
 역할 공급자 기능은 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장합니다. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 통합된 경우 사용자는 사용자 이름/암호 조합을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램에 제공해야 합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 데이터베이스를 사용하려면 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 클래스의 인스턴스를 만들고 해당 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> 속성을 <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>로 설정한 다음 서비스를 호스팅하는 <xref:System.ServiceModel.ServiceHost>에 대한 동작 컬렉션에 해당 인스턴스를 추가해야 합니다.  
  
### <a name="to-configure-the-role-provider"></a>역할 공급자를 구성하려면  
  
1.  Web.config 파일에 아래에서 <`system.web`> 요소를 추가 <`roleManager`> 요소 해당 `enabled` 특성을 `true`합니다.  
  
2.  `defaultProvider` 특성을 `SqlRoleProvider`으로 설정합니다.  
  
3.  하위 항목으로 <`roleManager`> 요소를 추가 된 <`providers`> 요소입니다.  
  
4.  하위 항목으로 <`providers`> 요소를 추가 <`add`> 요소는 다음 특성으로 적절 한 값으로 설정: `name`, `type`, `connectionStringName`, 및 `applicationName`다음 예제에 나온 것 처럼 합니다.  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a>역할 공급자를 사용하도록 서비스를 구성하려면  
  
1.  Web.config 파일에서 추가 된 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소입니다.  
  
2.  추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소는 <`system.ServiceModel`> 요소입니다.  
  
3.  추가 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 <`behaviors`> 요소입니다.  
  
4.  추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소는 `name` 특성을 적절 한 값입니다.  
  
5.  추가 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 에 <`behavior`> 요소입니다.  
  
6.  `principalPermissionMode` 특성을 `UseAspNetRoles`으로 설정합니다.  
  
7.  `roleProviderName` 특성을 `SqlRoleProvider`으로 설정합니다. 다음 예제에서는 구성의 단편을 보여 줍니다.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [방법: ASP.NET 멤버 자격 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
