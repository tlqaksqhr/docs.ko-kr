---
title: "방법: Windows Communication Foundation 보안 이벤트 감사 | Microsoft Docs"
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
  - "보안 [WCF], 이벤트 감사"
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# 방법: Windows Communication Foundation 보안 이벤트 감사
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 Windows 이벤트 뷰어를 사용하여 볼 수 있는 Windows 이벤트 로그에 보안 이벤트를 기록할 수 있습니다.  이 항목에서는 보안 이벤트를 기록하도록 응용 프로그램을 설정하는 방법에 대해 설명합니다.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 감사에 대한 자세한 내용은 [감사](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)를 참조하세요.  
  
### 코드에서 보안 이벤트를 감사하려면  
  
1.  감사 로그 위치를 지정합니다.  이렇게 하려면 다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> 클래스의 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> 속성을 <xref:System.ServiceModel.AuditLogLocation> 열거형 값 중 하나로 설정합니다.  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <xref:System.ServiceModel.AuditLogLocation> 열거에는 `Application`, `Security` 또는 `Default`의 세 개 값이 있습니다.  이 값은 이벤트 뷰어에서 볼 수 있는 로그\(보안 로그 또는 응용 프로그램 로그\) 중 하나를 지정합니다.  `Default` 값을 사용하는 경우 실제 로그는 응용 프로그램을 실행하는 운영 체제에 따라 달라집니다.  감사를 사용하지만 로그 위치가 지정되지 않은 경우 기본값은 보안 로그에 쓰기를 지원하는 플랫폼의 `Security` 로그입니다. 그렇지 않으면 `Application` 로그에 씁니다.  기본적으로 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 및 [!INCLUDE[wv](../../../../includes/wv-md.md)]만 보안 로그에 쓰기를 지원합니다.  
  
2.  감사할 이벤트 형식을 설정합니다.  서비스 수준 이벤트나 메시지 수준 권한 부여 이벤트를 동시에 감사할 수 있습니다.  이렇게 하려면 다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> 속성이나 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> 속성을 <xref:System.ServiceModel.AuditLevel> 열거형 값 중 하나로 설정합니다.  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3.  로그 감사 이벤트에 대해 오류를 응용 프로그램에 노출할지 또는 표시하지 않을지 지정합니다.  다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 속성을 `true` 또는 `false`로 설정합니다.  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     기본 `SuppressAuditFailure` 속성이 `true`이므로 감사하지 못해도 응용 프로그램에 영향을 주지 않습니다.  그렇지 않으면 예외가 throw됩니다.  성공한 모든 감사에 대해 자세한 추적이 기록됩니다.  감사하지 못하면 오류 수준에서 추적이 기록됩니다.  
  
4.  <xref:System.ServiceModel.ServiceHost>의 설명에 있는 동작 컬렉션에서 기존 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 삭제합니다.  동작 컬렉션은 <xref:System.ServiceModel.ServiceHostBase.Description%2A> 컬렉션에서 액세스되는 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 속성으로 액세스됩니다.  다음 코드와 같이 동일한 컬렉션에 새 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 추가합니다.  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### 구성에서 감사를 설정하려면  
  
1.  구성에서 감사를 설정하려면 web.config 파일의 [\<behaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 섹션에 [\<behavior\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소를 추가합니다.  다음 예제와 같이 [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) 요소를 추가하고 다양한 특성을 설정합니다.  
  
    ```  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"   
                serviceAuthorizationAuditLevel="None"   
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2.  다음 예제와 같이 서비스의 동작을 지정해야 합니다.  
  
    ```  
    <services>  
        <service type="WCS.Samples.Service.Echo"   
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"   
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
  
    ```  
  
## 예제  
 다음 코드에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들고 동작 컬렉션에 새 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 추가합니다.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## .NET Framework 보안  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 속성을 `true`로 설정하면 보안 감사 생성 오류가 표시되지 않습니다. `false`로 설정하면 예외가 throw됩니다.  그러나 다음 Windows **로컬 보안 설정** 속성을 사용하면 감사 이벤트를 생성하지 못할 경우 Windows가 즉시 종료됩니다.  
  
 **감사: 보안 감사를 로그할 수 없는 경우 즉시 시스템 종료**  
  
 속성을 설정하려면 **로컬 보안 설정** 대화 상자를 엽니다.  **보안 설정**에서 **로컬 정책**을 클릭합니다.  그런 다음 **보안 옵션**을 클릭합니다.  
  
 <xref:System.ServiceModel.AuditLogLocation> 속성이 <xref:System.ServiceModel.AuditLogLocation>로 설정되어 있지만 **개체 액세스 감사**가 **로컬 보안 정책**에 설정되지 않은 경우 감사 이벤트는 보안 로그에 기록되지 않습니다.  오류가 반환되지는 않지만 감사 항목이 보안 로그에 기록되지 않습니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>   
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>   
 <xref:System.ServiceModel.AuditLogLocation>   
 [감사](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)