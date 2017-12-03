---
title: "방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cba64767aaac4092f3c6103f7417a9d707b9a380
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a>방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 ID 모델 인프라에서는 확장 가능한 클레임 기반의 권한 부여 모델을 지원합니다. 클레임은 토큰에서 추출되어 사용자 지정 권한 부여 정책에 의해 선택적으로 처리된 다음,<xref:System.IdentityModel.Policy.AuthorizationContext>에 배치됩니다. 권한 부여 관리자는 <xref:System.IdentityModel.Policy.AuthorizationContext>에서 클레임을 검사하여 권한 부여 결정을 내립니다.  
  
 기본적으로 권한 부여는 <xref:System.ServiceModel.ServiceAuthorizationManager> 클래스에서 결정되지만, 사용자 지정 권한 부여 관리자를 만들어 이러한 결정을 재정의할 수 있습니다. 사용자 지정 권한 부여 관리자를 만들려면 <xref:System.ServiceModel.ServiceAuthorizationManager>에서 파생되는 클래스를 만든 다음 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드를 구현합니다. 권한 부여는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드에서 결정되며, 액세스가 허용되면 `true`를 반환하고 액세스가 거부되면 `false`를 반환합니다.  
  
 권한 부여 결정이 메시지 본문 내용에 따라 달라지는 경우 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드를 사용합니다.  
  
 성능 문제 때문에 가능하다면 권한 부여 결정 시 메시지 본문에 액세스하지 않아도 되도록 응용 프로그램을 다시 디자인해야 합니다.  
  
 서비스에 대한 사용자 지정 권한 부여 관리자는 코드 또는 구성을 통해 등록할 수 있습니다.  
  
### <a name="to-create-a-custom-authorization-manager"></a>사용자 지정 권한 부여 관리자를 만들려면  
  
1.  <xref:System.ServiceModel.ServiceAuthorizationManager> 클래스에서 클래스를 파생시킵니다.  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> 메서드를 재정의합니다.  
  
     <xref:System.ServiceModel.OperationContext> 메서드에 전달되는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>를 사용하여 권한 부여 결정을 내립니다.  
  
     다음 코드 예제에서는 권한 부여 결정을 내리기 위해 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> 메서드를 사용하여 사용자 지정 클레임 `http://www.contoso.com/claims/allowedoperation`을 찾습니다.  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a>코드를 사용하여 사용자 지정 권한 부여 관리자를 등록하려면  
  
1.  사용자 지정 권한 부여 관리자의 인스턴스를 만들어 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> 속성에 할당합니다.  
  
     <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 속성을 사용하여 <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>에 액세스할 수 있습니다.  
  
     다음 코드 예제에서는 `MyServiceAuthorizationManager` 사용자 지정 권한 부여 관리자를 등록합니다.  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a>구성을 사용하여 사용자 지정 권한 부여 관리자를 등록하려면  
  
1.  서비스에 대한 구성 파일을 엽니다.  
  
2.  추가 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 에 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)합니다.  
  
     에 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), 추가 `serviceAuthorizationManagerType` 특성 및 사용자 지정 권한 부여 관리자를 나타내는 형식에 값을 설정 합니다.  
  
3.  클라이언트와 서비스 간의 통신을 보안하는 바인딩을 추가합니다.  
  
     이 통신에 대해 선택된 바인딩에 따라 <xref:System.IdentityModel.Policy.AuthorizationContext>에 추가되는 클레임이 결정되고, 사용자 지정 권한 부여 관리자는 이 클레임을 사용하여 권한 부여 결정을 내립니다. 시스템 제공 바인딩에 대 한 자세한 내용은 참조 하십시오. [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)합니다.  
  
4.  추가 하 여 서비스 끝점에 동작을 연결할는 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) 요소 값을 설정 하 고는 `behaviorConfiguration` 특성에 대 한 이름 특성의 값으로는 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소입니다.  
  
     서비스 끝점을 구성 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 구성에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)합니다.  
  
     다음 코드 예제에서는 `Samples.MyServiceAuthorizationManager` 사용자 지정 권한 부여 관리자를 등록합니다.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.CalculatorService"  
              behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <endpoint address=""  
                      binding="wsHttpBinding_Calculator"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <WSHttpBinding>  
           <binding name = "wsHttpBinding_Calculator">  
             <security mode="Message">  
               <message clientCredentialType="Windows"/>  
             </security>  
            </binding>  
          </WSHttpBinding>  
    </bindings>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />  
             </behavior>  
         </serviceBehaviors>  
       </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
    > [!WARNING]
    >  serviceAuthorizationManagerType을 지정할 경우 문자열에 정규화된 형식 이름이 포함되어야 합니다. 콤마 및 형식이 정의된 어셈블리의 이름입니다. 어셈블리 이름을 지정하지 않을 경우 WCF는 System.ServiceModel.dll에서 형식 로드를 시도합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.ServiceModel.ServiceAuthorizationManager> 메서드 재정의를 포함하는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 클래스의 기본 구현을 보여 줍니다. 예제 코드에서는 <xref:System.IdentityModel.Policy.AuthorizationContext>에서 사용자 지정 클레임을 검사하고 해당 사용자 지정 클레임의 리소스가 `true`의 동작 값과 일치하면 <xref:System.ServiceModel.OperationContext>를 반환합니다. 구현은 보다 완전 한 <xref:System.ServiceModel.ServiceAuthorizationManager> 클래스를 참조 하십시오 [권한 부여 정책](../../../../docs/framework/wcf/samples/authorization-policy.md)합니다.  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [권한 부여 정책](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [권한 부여 정책](../../../../docs/framework/wcf/samples/authorization-policy.md)
