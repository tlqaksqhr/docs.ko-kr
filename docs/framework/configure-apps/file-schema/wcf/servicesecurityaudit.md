---
title: '&lt;serviceSecurityAudit&gt;'
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 293cd3118ace2e073933e4c124664c775902e7d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751183"
---
# <a name="ltservicesecurityauditgt"></a>&lt;serviceSecurityAudit&gt;
서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<serviceBehaviors>  
\<동작 >  
\<serviceSecurityAudit>  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessOrFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|auditLogLocation|감사 로그의 위치를 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -Default: 보안 이벤트가 기록 됩니다 응용 프로그램 로그에 Windows XP에서 및 이벤트 로그에 Windows Server 2003 및 Windows Vista에서.<br />-응용 프로그램: 감사 이벤트가 응용 프로그램 이벤트 로그에 기록 됩니다.<br />-보안: 감사 이벤트가 보안 이벤트 로그에 기록 됩니다.<br /><br /> 기본값은 Default입니다. 자세한 내용은 <xref:System.ServiceModel.AuditLogLocation>을 참조하세요.|  
|suppressAuditFailure|감사 로그에 쓰기 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.<br /><br /> 응용 프로그램은 감사 로그 쓰기 실패에 대해 알림을 받아야 합니다. 해당 응용 프로그램에 감사 실패 처리 기능이 없는 경우 감사 로그에 쓰기 실패를 표시하지 않으려면 이 특성을 사용해야 합니다.<br /><br /> 이 특성이 `true`이면 감사 이벤트 쓰기 시도로 인해 발생한 OutOfMemoryException, StackOverFlowException, ThreadAbortException 및 ArgumentException 이외의 예외는 시스템에 의해 처리되며 응용 프로그램으로 전파되지 않습니다. 이 특성이 `false`이면 감사 이벤트 쓰기 시도로 인해 발생한 모든 예외가 응용 프로그램까지 전달됩니다.<br /><br /> 기본값은 `true`입니다.|  
|serviceAuthorizationAuditLevel|감사 로그에 기록되는 인증 이벤트의 형식을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -None: 서비스 인증 이벤트의 감사 안 수행 됩니다.<br />-Success: 성공적인 서비스 권한 부여 이벤트만 감사 됩니다.<br />-오류: 실패 서비스 권한 부여 이벤트만 감사 됩니다.<br />-둘 다 SuccessOrFailure: 성공 및 실패 서비스 권한 부여 이벤트만 감사 됩니다.<br /><br /> 기본값은 None입니다. 자세한 내용은 <xref:System.ServiceModel.AuditLevel>을 참조하세요.|  
|messageAuthenticationAuditLevel|기록되는 메시지 인증 감사 이벤트 형식을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -None: 감사 이벤트가 생성 됩니다.<br />-Success: 성공적인 보안 (메시지 시그니처 유효성 검사, 암호화 및 토큰 유효성 검사를 포함 한 전체 유효성) 이벤트만 기록 됩니다.<br />-오류: 실패 한 이벤트만 기록 됩니다.<br />-둘 다 SuccessOrFailure: 성공 및 실패 이벤트가 기록 됩니다.<br /><br /> 기본값은 None입니다. 자세한 내용은 <xref:System.ServiceModel.AuditLevel>을 참조하세요.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소는 Windows Communication Foundation (WCF) 인증 이벤트 감사에 사용 됩니다. 감사 기능을 사용하도록 설정하면 성공한 인증 시도나 실패한 인증 시도 또는 둘 모두를 감사할 수 있습니다. 이벤트는 운영 체제 버전의 응용 프로그램 로그, 보안 로그 또는 기본 로그의 세 가지 이벤트 로그 중 하나에 기록됩니다. 이벤트 로그는 Windows 이벤트 뷰어를 사용하여 볼 수 있습니다.  
  
 이 구성 요소를 사용 하 여의 자세한 예제를 보려면 [서비스 감사 동작](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)합니다.  
  
 기본적으로 Windows XP에서는 응용 프로그램 로그에서 감사 이벤트를 볼 수 있지만 Windows Server 2003 및 Windows Vista에서는 보안 로그에서 감사 이벤트를 볼 수 있습니다. 감사 이벤트의 위치는 `auditLogLocation` 특성을 'Application' 또는 'Security'로 설정하여 지정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 보안 이벤트 감사](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)합니다. 이벤트가 보안 로그에 기록되면 "Success" 및 "Failure"에 대해 LocalSecurityPolicy-> Enable Object Access를 설정해야 합니다.  
  
 이벤트 로그를 확인하면 감사 이벤트의 소스는 "ServiceModel Audit 3.0.0.0"입니다. 메시지 인증 감사 레코드의 범주는 "MessageAuthentication"이지만 서비스 권한 부여 감사 레코드의 범주는 'ServiceAuthorization'입니다.  
  
 메시지 인증 감사 이벤트는 메시지가 훼손되었는지 여부, 메시지가 만료되었는지 여부 및 클라이언트가 서비스에서 인증될 수 있는지 여부를 포함합니다. 이 이벤트는 클라이언트의 ID와 함께 인증의 성공 여부, 메시지와 연결된 동작과 함께 메시지가 보내진 끝점에 대한 정보를 제공합니다.  
  
 서비스 권한 부여 감사 이벤트는 서비스 권한 부여 관리자가 내린 권한 부여 결정을 포함합니다. 권한 부여의 성공 여부에 대 한 정보를 제공 하거나 클라이언트의 id와 함께 실패, 메시지가 보내진 끝점에서 생성 된 권한 부여 컨텍스트의 식별자 메시지와 관련 된 작업에는 들어오는 메시지 및 액세스 결정을 내린 권한 부여 관리자의 형식입니다.  
  
## <a name="example"></a>예제  
  
```xml  
<system.serviceModel>  
   <serviceBehaviors>  
      <behavior name="NewBehavior">  
         <serviceSecurityAudit auditLogLocation="Application"   
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"   
             messageAuthenticationAuditLevel="Success" />  
      </behavior>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [감사](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [방법: 보안 이벤트 감사](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [서비스 감사 동작](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)
