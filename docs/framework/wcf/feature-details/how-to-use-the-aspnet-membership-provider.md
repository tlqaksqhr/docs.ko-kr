---
title: "방법: ASP.NET 멤버 자격 공급자 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c5042e73945c54da2b1ee71fc5ea61727dc73c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>방법: ASP.NET 멤버 자격 공급자 사용
[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 개발자가 웹 사이트를 만들어 사용자에게 고유 사용자 이름 및 암호 조합을 만들 수 있도록 해주는 기능입니다. 이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다. 반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다. 대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.  
  
 샘플 응용 프로그램에 대 한 참조 [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)합니다. 사용 하는 방법에 대 한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자 기능 참조 [하는 방법: ASP.NET 역할 공급자를 사용 하 여 서비스와](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)합니다.  
  
 멤버 자격 기능을 사용하려면 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장해야 합니다. 해당 기능에는 암호를 잊은 사용자에게 질문을 표시하기 위한 메서드도 포함됩니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 통합된 경우 사용자는 사용자 이름/암호 조합을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램에 제공해야 합니다. 데이터를 전송 하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 같은 사용자 이름/암호 자격 증명을 지 원하는 바인딩을 사용는 <xref:System.ServiceModel.WSHttpBinding> (구성에서는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) 하 고 클라이언트 자격 증명 설정 입력 `UserName`합니다. 서비스에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안이 사용자 이름 및 암호를 기반으로 사용자를 인증하고, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할에서 지정한 역할도 할당합니다.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 사용자 이름/암호 조합 또는 기타 사용자 정보로 데이터베이스를 입력할 수 있는 메서드를 제공하지 않습니다.  
  
### <a name="to-configure-the-membership-provider"></a>멤버 자격 공급자를 구성하려면  
  
1.  Web.config 파일에 아래에서 <`system.web`> 요소를 만들는 <`membership`> 요소.  
  
2.  `<membership>` 요소 아래에 `<providers>` 요소를 만듭니다.  
  
3.  하위 항목으로 <`providers`> 요소를 추가 `<clear />` 요소 플러시 공급자의 컬렉션입니다.  
  
4.  아래는 `<clear />` 요소를 만들기는 <`add`> 요소는 다음 특성으로 적절 한 값으로 설정: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` `requiresUniqueEmail`, 및 `passwordFormat`합니다. `name` 특성은 나중에 구성 파일의 값으로 사용됩니다. 다음 예제에서는 이 특성을 `SqlMembershipProvider`으로 설정합니다.  
  
     다음 예제에서는 구성 섹션을 보여 줍니다.  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>사용자 이름/암호 조합을 허용하도록 서비스 보안을 구성하려면  
  
1.  구성 파일에 아래에서 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소입니다.  
  
2.  추가 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 바인딩 섹션에 있습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]만들기는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 참조 바인딩 요소 [하는 방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.  
  
3.  `mode` 요소의 `<security>` 특성을 `Message`로 설정합니다.  
  
4.  설정의 `clientCredentialType` 특성에는 <`message`> 요소를 `UserName`합니다. 이를 통해 사용자 이름/암호 쌍을 클라이언트의 자격 증명으로 사용하도록 지정됩니다.  
  
     다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a>멤버 자격 공급자를 사용하여 서비스를 구성하려면  
  
1.  하위 항목으로 `<system.serviceModel>` 요소를 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소  
  
2.  추가 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 <`behaviors`> 요소입니다.  
  
3.  추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 설정 하 고는 `name` 특성을 적절 한 값입니다.  
  
4.  추가 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 에 <`behavior`> 요소입니다.  
  
5.  추가 [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) 에 `<serviceCredentials>` 요소입니다.  
  
6.  `userNamePasswordValidationMode` 특성을 `MembershipProvider`으로 설정합니다.  
  
    > [!IMPORTANT]
    >  `userNamePasswordValidationMode` 값이 설정되어 있지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자 대신 Windows 인증을 사용합니다.  
  
7.  `membershipProviderName` 특성을 공급자의 이름으로 설정합니다(이 항목의 첫 번째 절차에서 공급자를 추가할 때 지정됨). 다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>예  
 다음 코드에서는 ASP 멤버 자격 기능을 사용하는 서비스의 구성을 보여 줍니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
