---
title: '&lt;serviceSecurityAudit&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f0c708c19761f6086e1b5c2fdd15904c76fe3de9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicesecurityauditgt"></a><span data-ttu-id="3b352-102">&lt;serviceSecurityAudit&gt;</span><span class="sxs-lookup"><span data-stu-id="3b352-102">&lt;serviceSecurityAudit&gt;</span></span>
<span data-ttu-id="3b352-103">서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-103">Specifies settings that enable auditing of security events during service operations.</span></span>  
  
 <span data-ttu-id="3b352-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3b352-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3b352-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3b352-105">\<behaviors></span></span>  
<span data-ttu-id="3b352-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3b352-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3b352-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3b352-107">\<behavior></span></span>  
<span data-ttu-id="3b352-108">\<serviceSecurityAudit ></span><span class="sxs-lookup"><span data-stu-id="3b352-108">\<serviceSecurityAudit></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b352-109">구문</span><span class="sxs-lookup"><span data-stu-id="3b352-109">Syntax</span></span>  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessAndFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessAndFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b352-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3b352-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3b352-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b352-112">특성</span><span class="sxs-lookup"><span data-stu-id="3b352-112">Attributes</span></span>  
  
|<span data-ttu-id="3b352-113">특성</span><span class="sxs-lookup"><span data-stu-id="3b352-113">Attribute</span></span>|<span data-ttu-id="3b352-114">설명</span><span class="sxs-lookup"><span data-stu-id="3b352-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b352-115">auditLogLocation</span><span class="sxs-lookup"><span data-stu-id="3b352-115">auditLogLocation</span></span>|<span data-ttu-id="3b352-116">감사 로그의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-116">Specifies the location of the audit log.</span></span> <span data-ttu-id="3b352-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3b352-118">-Default: 보안 이벤트가 기록 됩니다 응용 프로그램 로그에 Windows XP에서 및 이벤트 로그에 Windows Server 2003 및 Windows Vista에서.</span><span class="sxs-lookup"><span data-stu-id="3b352-118">-   Default: Security events are written to the application log on Windows XP, and to the Event Log on Windows Server 2003 and Windows Vista.</span></span><br /><span data-ttu-id="3b352-119">-응용 프로그램: 감사 이벤트가 응용 프로그램 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-119">-   Application: Audit events are written to the Application Event Log.</span></span><br /><span data-ttu-id="3b352-120">-보안: 감사 이벤트가 보안 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-120">-   Security: Audit events are written to the Security Event Log.</span></span><br /><br /> <span data-ttu-id="3b352-121">기본값은 Default입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-121">The default value is Default.</span></span> <span data-ttu-id="3b352-122">자세한 내용은 <xref:System.ServiceModel.AuditLogLocation>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b352-122">For more information, see <xref:System.ServiceModel.AuditLogLocation>.</span></span>|  
|<span data-ttu-id="3b352-123">suppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="3b352-123">suppressAuditFailure</span></span>|<span data-ttu-id="3b352-124">감사 로그에 쓰기 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-124">A Boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span><br /><br /> <span data-ttu-id="3b352-125">응용 프로그램은 감사 로그 쓰기 실패에 대해 알림을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-125">Applications should be notified for failures of writing to the audit log.</span></span> <span data-ttu-id="3b352-126">해당 응용 프로그램에 감사 실패 처리 기능이 없는 경우 감사 로그에 쓰기 실패를 표시하지 않으려면 이 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-126">If your application is not designed to handle audit failures, you should use this attribute to suppress failures in writing to the audit log.</span></span><br /><br /> <span data-ttu-id="3b352-127">이 특성이 `true`이면 감사 이벤트 쓰기 시도로 인해 발생한 OutOfMemoryException, StackOverFlowException, ThreadAbortException 및 ArgumentException 이외의 예외는 시스템에 의해 처리되며 응용 프로그램으로 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-127">If this attribute is `true`, exceptions other than OutOfMemoryException, StackOverFlowException, ThreadAbortException, and ArgumentException that result from attempts to write audit events are handled by the system, and are not propagated to the application.</span></span> <span data-ttu-id="3b352-128">이 특성이 `false`이면 감사 이벤트 쓰기 시도로 인해 발생한 모든 예외가 응용 프로그램까지 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-128">If this attribute is `false`, all exceptions that result from attempts to write audit events are passed up to the application.</span></span><br /><br /> <span data-ttu-id="3b352-129">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-129">The default is `true`.</span></span>|  
|<span data-ttu-id="3b352-130">serviceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="3b352-130">serviceAuthorizationAuditLevel</span></span>|<span data-ttu-id="3b352-131">감사 로그에 기록되는 인증 이벤트의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-131">Specifies the types of authorization events that are recorded in the audit log.</span></span> <span data-ttu-id="3b352-132">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3b352-133">-None: 서비스 인증 이벤트의 감사 안 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-133">-   None: No auditing of service authorization events is performed.</span></span><br /><span data-ttu-id="3b352-134">-Success: 성공적인 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-134">-   Success: Only successful service authorization events are audited.</span></span><br /><span data-ttu-id="3b352-135">-오류: 실패 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-135">-   Failure: Only failure service authorization events are audited.</span></span><br /><span data-ttu-id="3b352-136">-둘 다 SuccessAndFailure: 성공 및 실패 서비스 권한 부여 이벤트만 감사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-136">-   SuccessAndFailure: Both success and failure service authorization events are audited.</span></span><br /><br /> <span data-ttu-id="3b352-137">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-137">The default value is None.</span></span> <span data-ttu-id="3b352-138">자세한 내용은 <xref:System.ServiceModel.AuditLevel>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b352-138">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
|<span data-ttu-id="3b352-139">messageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="3b352-139">messageAuthenticationAuditLevel</span></span>|<span data-ttu-id="3b352-140">기록되는 메시지 인증 감사 이벤트 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-140">Specifies the type of message authentication audit events logged.</span></span> <span data-ttu-id="3b352-141">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3b352-142">-None: 감사 이벤트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-142">-   None: No audit events are generated.</span></span><br /><span data-ttu-id="3b352-143">-Success: 성공적인 보안 (메시지 시그니처 유효성 검사, 암호화 및 토큰 유효성 검사를 포함 한 전체 유효성) 이벤트만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-143">-   Success: Only successful security (full validation including message signature validation, cipher, and token validation) events are logged.</span></span><br /><span data-ttu-id="3b352-144">-오류: 실패 한 이벤트만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-144">-   Failure: Only failure events are logged.</span></span><br /><span data-ttu-id="3b352-145">-둘 다 SuccessAndFailure: 성공 및 실패 이벤트가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-145">-   SuccessAndFailure: Both success and failure events are logged.</span></span><br /><br /> <span data-ttu-id="3b352-146">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-146">The default value is None.</span></span> <span data-ttu-id="3b352-147">자세한 내용은 <xref:System.ServiceModel.AuditLevel>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b352-147">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b352-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3b352-148">Child Elements</span></span>  
 <span data-ttu-id="3b352-149">없음</span><span class="sxs-lookup"><span data-stu-id="3b352-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b352-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3b352-150">Parent Elements</span></span>  
  
|<span data-ttu-id="3b352-151">요소</span><span class="sxs-lookup"><span data-stu-id="3b352-151">Element</span></span>|<span data-ttu-id="3b352-152">설명</span><span class="sxs-lookup"><span data-stu-id="3b352-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b352-153">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3b352-153">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3b352-154">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-154">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b352-155">설명</span><span class="sxs-lookup"><span data-stu-id="3b352-155">Remarks</span></span>  
 <span data-ttu-id="3b352-156">이 구성 요소는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 인증 이벤트를 감사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-156">This configuraton element is used to audit [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] authentication events.</span></span> <span data-ttu-id="3b352-157">감사 기능을 사용하도록 설정하면 성공한 인증 시도나 실패한 인증 시도 또는 둘 모두를 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-157">When auditing is enabled, either successful or failed authentication attempts (or both) can be audited.</span></span> <span data-ttu-id="3b352-158">이벤트는 운영 체제 버전의 응용 프로그램 로그, 보안 로그 또는 기본 로그의 세 가지 이벤트 로그 중 하나에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-158">The events are written to one of three event logs: application, security, or the default log for the operating system version.</span></span> <span data-ttu-id="3b352-159">이벤트 로그는 Windows 이벤트 뷰어를 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-159">The event logs can all be viewed using the Windows Event viewer.</span></span>  
  
 <span data-ttu-id="3b352-160">이 구성 요소를 사용 하 여의 자세한 예제를 보려면 [서비스 감사 동작](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-160">For a detailed example of using this configuration element, see [Service Auditing Behavior](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).</span></span>  
  
 <span data-ttu-id="3b352-161">기본적으로 Windows XP에서는 응용 프로그램 로그에서 감사 이벤트를 볼 수 있지만 Windows Server 2003 및 Windows Vista에서는 보안 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-161">By default, on Windows XP the audit events can be seen in the Application Log; while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="3b352-162">감사 이벤트의 위치는 `auditLogLocation` 특성을 'Application' 또는 'Security'로 설정하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-162">The location of audit events can be specified by setting the `auditLogLocation` attribute to 'Application' or 'Security'.</span></span> <span data-ttu-id="3b352-163">자세한 내용은 참조 [하는 방법: 보안 이벤트 감사](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-163">For more information, see [How to: Audit Security Events](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="3b352-164">이벤트가 보안 로그에 기록되면 "Success" 및 "Failure"에 대해 LocalSecurityPolicy-> Enable Object Access를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-164">If the events are written in the Security Log, the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="3b352-165">이벤트 로그를 확인하면 감사 이벤트의 소스는 "ServiceModel Audit 3.0.0.0"입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-165">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="3b352-166">메시지 인증 감사 레코드의 범주는 "MessageAuthentication"이지만 서비스 권한 부여 감사 레코드의 범주는 'ServiceAuthorization'입니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-166">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of 'ServiceAuthorization'.</span></span>  
  
 <span data-ttu-id="3b352-167">메시지 인증 감사 이벤트는 메시지가 훼손되었는지 여부, 메시지가 만료되었는지 여부 및 클라이언트가 서비스에서 인증될 수 있는지 여부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-167">Message authentication audit events cover whether the message was tampered with, whether the message has expired and whether the client can authenticate to the service.</span></span> <span data-ttu-id="3b352-168">이 이벤트는 클라이언트의 ID와 함께 인증의 성공 여부, 메시지와 연결된 동작과 함께 메시지가 보내진 끝점에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-168">They provide information about whether the authentication succeeded or failed along with the identity of the client and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="3b352-169">서비스 권한 부여 감사 이벤트는 서비스 권한 부여 관리자가 내린 권한 부여 결정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-169">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="3b352-170">이 이벤트는 클라이언트 ID와 함께 권한 부여의 성공 여부, 메시지가 보내진 끝점, 메시지와 연결된 동작, 들어오는 메시지에서 생성된 권한 부여 컨텍스트의 식별자 및 액세스 결정을 내린 권한 부여 관리자의 형식에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3b352-170">They provide information about whether authorization succeeded of failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message and the type of the authorization manager that made the access decision.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b352-171">예제</span><span class="sxs-lookup"><span data-stu-id="3b352-171">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b352-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b352-172">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [<span data-ttu-id="3b352-173">보안 동작</span><span class="sxs-lookup"><span data-stu-id="3b352-173">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="3b352-174">감사</span><span class="sxs-lookup"><span data-stu-id="3b352-174">Auditing</span></span>](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [<span data-ttu-id="3b352-175">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="3b352-175">How to: Audit Security Events</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [<span data-ttu-id="3b352-176">서비스 감사 동작</span><span class="sxs-lookup"><span data-stu-id="3b352-176">Service Auditing Behavior</span></span>](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)
