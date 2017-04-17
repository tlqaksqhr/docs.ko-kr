---
title: "방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기 | Microsoft Docs"
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
  - "WCF, 인증(authentication)"
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기
이 항목에서는 사용자 지정 인증서 유효성 검사기를 구현하는 방법과 클라이언트 또는 서비스 자격 증명을 구성하여 기본 인증서 유효성 검사 논리를 사용자 지정 인증서 유효성 검사기로 바꾸는 방법을 보여 줍니다.  
  
 X.509 인증서를 사용하여 클라이언트 또는 서비스를 인증하는 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 기본적으로 Windows 인증서 저장소와 Crypto API를 사용하여 인증서의 유효성을 검사하고 신뢰할 수 있는지 확인합니다.  기본 제공 인증서 유효성 검사 기능으로 충분하지 않은 경우에는 변경해야 합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 사용자가 사용자 지정 인증서 유효성 검사기를 추가할 수 있도록 하여 쉽게 유효성 검사 논리를 변경하는 방법을 제공합니다.  사용자 지정 인증서 유효성 검사기를 지정하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 기본 제공 인증서 유효성 검사 논리를 사용하지 않고 대신 사용자 지정 유효성 검사기를 사용합니다.  
  
## 절차  
  
#### 사용자 지정 인증서 유효성 검사기를 만들려면  
  
1.  <xref:System.IdentityModel.Selectors.X509CertificateValidator>에서 파생된 새 클래스를 정의합니다.  
  
2.  추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> 메서드를 구현합니다.  유효성을 검사해야 하는 인증서는 인수로 메서드에 전달됩니다.  전달된 인증서가 유효성 검사 논리에 따라 유효하지 않은 경우 이 메서드는 <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>을 throw합니다.  인증서가 유효하면 메서드가 호출자에게 반환됩니다.  
  
    > [!NOTE]
    >  인증 오류를 다시 클라이언트에 반환하려면 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드에서 <xref:System.ServiceModel.FaultException>을 throw합니다.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### 서비스 구성에 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1.  [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소 및 [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)을 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소에 추가합니다.  
  
2.  [\<behavior\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)를 추가하고 `name` 특성을 적절한 값으로 설정합니다.  
  
3.  [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)를 `<behavior>` 요소에 추가합니다.  
  
4.  `<clientCertificate>` 요소를 `<serviceCredentials>` 요소에 추가합니다.  
  
5.  [\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)를 `<clientCertificate>` 요소에 추가합니다.  
  
6.  `customCertificateValidatorType` 특성을 유효성 검사기 형식으로 설정합니다.  다음 예제에서는 특성을 형식의 네임스페이스 및 이름으로 설정합니다.  
  
7.  `certificateValidationMode` 특성을 `Custom`으로 설정합니다.  
  
    ```  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### 클라이언트에 구성을 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1.  [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소 및 [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)을 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소에 추가합니다.  
  
2.  [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) 요소를 추가합니다.  
  
3.  `<behavior>` 요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다.  
  
4.  [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소를 추가합니다.  
  
5.  [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)를 추가합니다.  
  
6.  다음 예제와 같이 [\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)를 추가합니다.  
  
7.  `customCertificateValidatorType` 특성을 유효성 검사기 형식으로 설정합니다.  
  
8.  `certificateValidationMode` 특성을 `Custom`으로 설정합니다.  다음 예제에서는 특성을 형식의 네임스페이스 및 이름으로 설정합니다.  
  
    ```  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### 서비스에 코드를 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1.  <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> 속성에 사용자 지정 인증서 유효성 검사기를 지정합니다.  <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성을 사용하여 서비스 자격 증명에 액세스할 수 있습니다.  
  
2.  <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> 속성을 <xref:System.ServiceModel.Security.X509CertificateValidationMode>으로 설정합니다.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### 클라이언트에 코드를 사용하여 사용자 지정 인증서 유효성 검사기를 지정하려면  
  
1.  <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> 속성을 사용하여 사용자 지정 인증서 유효성 검사기를 지정합니다.  <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성을 사용하여 클라이언트 자격 증명에 액세스할 수 있습니다.  [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)에 의해 생성된 클라이언트 클래스는 항상 <xref:System.ServiceModel.ClientBase%601> 클래스에서 파생됩니다.  
  
2.  <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> 속성을 <xref:System.ServiceModel.Security.X509CertificateValidationMode>으로 설정합니다.  
  
## 예제  
  
### 설명  
 다음 샘플에서는 서비스에 사용자 지정 인증서 유효성 검사기를 구현하고 사용하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>