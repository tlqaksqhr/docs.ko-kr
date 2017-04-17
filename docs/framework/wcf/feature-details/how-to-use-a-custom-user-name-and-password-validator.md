---
title: "방법: 사용자 지정 사용자 이름 및 암호 유효성 검사기 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, 사용자 이름 및 암호"
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 방법: 사용자 지정 사용자 이름 및 암호 유효성 검사기 사용
기본적으로 사용자 이름과 암호가 인증에 사용될 때, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 Windows를 사용하여 사용자 이름과 암호의 유효성을 검사합니다.그러나 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 *유효성 검사기*라고도 하는 사용자 지정 사용자 이름 및 암호 인증 스키마를 허용합니다.사용자 지정 사용자 이름 및 암호 유효성 검사기를 통합하려면 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만들어 구성합니다.  
  
 샘플 응용 프로그램을 보려면 [사용자 이름 암호 유효성 검사기](../../../../docs/framework/wcf/samples/user-name-password-validator.md)를 참조하십시오.  
  
### 사용자 지정 사용자 이름 및 암호 유효성 검사기를 만들려면  
  
1.  <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에서 파생되는 클래스를 만듭니다.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하여 사용자 지정 인증 스키마를 구현합니다.  
  
     다음 예제에서는 프로덕션 환경에서 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다.코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.  
  
     인증 오류를 다시 클라이언트에 반환하려면 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드에서 <xref:System.ServiceModel.FaultException>을 throw합니다.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하도록 서비스를 구성하려면  
  
1.  HTTP\(S\)를 통해 전송 또는 전송 수준 보안에서 메시지 보안을 사용하는 바인딩을 구성합니다.  
  
     메시지 보안을 사용하는 경우 메시지 보안 및 `UserName` 자격 증명 형식을 지원하는 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 또는 [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)처럼 시스템 제공 바인딩 중 하나를 추가합니다.  
  
     HTTP\(S\)를 통해 전송 수준 보안을 사용하는 경우 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)나 [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 또는 HTTP\(S\) 및 `Basic` 인증 체계를 사용하는 [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) 또는 [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)를 추가합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 이상을 사용하는 경우 메시지 및 전송 보안과 함께 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용할 수 있습니다.[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]를 사용하는 경우에는 메시지 보안에서만 사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용할 수 있습니다.  
  
    > [!TIP]
    >  이 컨텍스트에서 \<netTcpBinding\>을 사용하는 방법은 [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)를 참조하십시오.  
  
    1.  구성 파일에서 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소 아래에 [\<bindings\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소를 추가합니다.  
  
    2.  bindings 섹션에 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 또는 [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소를 추가합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩 요소 만들기[!INCLUDE[crabout](../../../../includes/crabout-md.md)][방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)을 참조하십시오.  
  
    3.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 또는 [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)의 `mode` 특성을 `Message`, `Transport`, `또는``TransportWithMessageCredential`로 설정합니다.  
  
    4.  [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) 또는 [\<transport\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)의 `clientCredentialType` 특성을 설정합니다.  
  
         메시지 보안을 사용하는 경우 [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)의 `clientCredentialType` 특성을 `UserName`으로 설정합니다.  
  
         HTTP\(S\)를 통해 전송 수준 보안을 사용하는 경우 [\<transport\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) 또는 [\<transport\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)의 `clientCredentialType` 특성을 `Basic`으로 설정합니다.  
  
        > [!NOTE]
        >  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 전송 수준 보안을 사용하여 IIS\(인터넷 정보 서비스\)에서 호스팅되고 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> 속성이 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>으로 설정되는 경우 사용자 지정 인증 스키마에서는 Windows 인증의 하위 집합을 사용합니다.이 시나리오의 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 사용자 지정 인증자를 호출하기 전에 IIS에서 Windows 인증을 수행하기 때문입니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩 요소 만들기[!INCLUDE[crabout](../../../../includes/crabout-md.md)][방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)을 참조하십시오.  
  
     다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.  
  
    ```  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2.  사용자 지정 사용자 이름 및 암호 유효성 검사기를 사용하여 들어오는 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> 보안 토큰에 대한 사용자 이름과 암호 쌍의 유효성을 검사하도록 지정하는 동작을 구성합니다.  
  
    1.  [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소에 대한 자식으로 추가합니다.  
  
    2.  [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)를 [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소에 추가합니다.  
  
    3.  [\<behavior\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다.  
  
    4.  [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)를 [\<behavior\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소에 추가합니다.  
  
    5.  [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)를 [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)에 추가합니다.  
  
    6.  `userNamePasswordValidationMode`를 `Custom`으로 설정합니다.  
  
        > [!IMPORTANT]
        >  `userNamePasswordValidationMode` 값이 설정되어 있지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 사용자 지정 사용자 이름 및 암호 유효성 검사기 대신 Windows 인증을 사용합니다.  
  
    7.  `customUserNamePasswordValidatorType`을 사용자 지정 사용자 이름 및 암호 유효성 검사기를 나타내는 형식으로 설정합니다.  
  
     다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.  
  
    ```  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## 예제  
 다음 코드 예제에서는 사용자 지정 사용자 이름 및 암호 유효성 검사기를 만드는 방법을 보여 줍니다.프로덕션 환경에서는 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 재정의하는 코드를 사용하지 않습니다.코드를 사용자 지정 사용자 이름 및 암호 유효성 검사 스키마로 바꿉니다. 이 스키마는 데이터베이스에서 사용자 이름과 암호 쌍을 검색합니다.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>   
 [방법: ASP.NET 멤버 자격 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)   
 [인증](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)