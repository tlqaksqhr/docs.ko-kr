---
title: "보안 이벤트 감사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- auditing security events [WCF]
ms.assetid: 5633f61c-a3c9-40dd-8070-1c373b66a716
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: cb8f112c71c743fd6650baf04b8db55ceaeef4ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="auditing-security-events"></a><span data-ttu-id="17f65-102">보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="17f65-102">Auditing Security Events</span></span>
<span data-ttu-id="17f65-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 만든 응용 프로그램은 감사 기능을 사용하여 보안 이벤트(성공, 실패 또는 둘 다)를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-103">Applications created with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] can log security events (either success, failure, or both) with the auditing feature.</span></span> <span data-ttu-id="17f65-104">이벤트는 Windows의 시스템 이벤트 로그에 기록되며 이벤트 뷰어를 사용하여 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-104">The events are written to the Windows system event log and can be examined using the Event Viewer.</span></span>  
  
 <span data-ttu-id="17f65-105">관리자는 감사를 사용하여 이미 발생했거나 진행 중인 공격을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-105">Auditing provides a way for an administrator to detect an attack that has already occurred or is in progress.</span></span> <span data-ttu-id="17f65-106">또한 감사는 개발자가 보안 관련 문제를 디버깅하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-106">In addition, auditing can help a developer to debug security-related problems.</span></span> <span data-ttu-id="17f65-107">예를 들어, 정책 검사 또는 권한 부여 구성 오류로 인해 실수로 권한 있는 사용자의 액세스가 거부될 경우 개발자는 이벤트 로그를 검사하여 오류의 원인을 신속하게 찾아서 격리시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-107">For example, if an error in the configuration of the authorization or checking policy accidentally denies access to an authorized user, a developer can quickly discover and isolate the cause of this error by examining the event log.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="17f65-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 참조 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-108"> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security, see [Security Overview](../../../../docs/framework/wcf/feature-details/security-overview.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="17f65-109">프로그래밍 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], 참조 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-109"> programming [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="audit-level-and-behavior"></a><span data-ttu-id="17f65-110">감사 수준 및 동작</span><span class="sxs-lookup"><span data-stu-id="17f65-110">Audit Level and Behavior</span></span>  
 <span data-ttu-id="17f65-111">보안 감사에는 다음과 같은 두 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-111">Two levels of security audits exist:</span></span>  
  
-   <span data-ttu-id="17f65-112">서비스 인증 수준 - 호출자에게 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-112">Service authorization level, in which a caller is authorized.</span></span>  
  
-   <span data-ttu-id="17f65-113">메시지 수준 - [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 메시지의 유효성을 검사하고 호출자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-113">Message level, in which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] checks for message validity and authenticates the caller.</span></span>  
  
 <span data-ttu-id="17f65-114">감사 성공 또는 실패 라고 하는 수준 모두를 확인할 수 있습니다는 *감사 동작*합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-114">You can check both audit levels for success or failure, which is known as the *audit behavior*.</span></span>  
  
## <a name="audit-log-location"></a><span data-ttu-id="17f65-115">감사 로그 위치</span><span class="sxs-lookup"><span data-stu-id="17f65-115">Audit Log Location</span></span>  
 <span data-ttu-id="17f65-116">감사 수준과 동작을 결정한 후 사용자 또는 관리자가 감사 로그의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-116">Once you determine an audit level and behavior, you (or an administrator) can specify a location for the audit log.</span></span> <span data-ttu-id="17f65-117">기본값, 응용 프로그램, 보안의 세 가지 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-117">The three choices include: Default, Application, and Security.</span></span> <span data-ttu-id="17f65-118">기본값을 지정한 경우 실제 로그는 사용 중인 시스템과 시스템에서 보안 로그 기록을 지원하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-118">When you specify Default, the actual log depends on which system you are using and whether the system supports writing to the security log.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="17f65-119"> 이 항목의 뒷부분에 나오는 "운영 체제".</span><span class="sxs-lookup"><span data-stu-id="17f65-119"> the "Operating System" section later in this topic.</span></span>  
  
 <span data-ttu-id="17f65-120">보안 로그에 기록하려면 `SeAuditPrivilege`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-120">To write to the Security log requires the `SeAuditPrivilege`.</span></span> <span data-ttu-id="17f65-121">기본적으로 로컬 시스템 및 네트워크 서비스 계정에만 이 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-121">By default, only Local System and Network Service accounts have this privilege.</span></span> <span data-ttu-id="17f65-122">보안 로그 기능 `read` 및 `delete`를 관리하려면 `SeSecurityPrivilege`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-122">To manage the Security log functions `read` and `delete` requires the `SeSecurityPrivilege`.</span></span> <span data-ttu-id="17f65-123">기본적으로 관리자만 이 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-123">By default, only administrators have this privilege.</span></span>  
  
 <span data-ttu-id="17f65-124">반대로, 인증된 사용자는 응용 프로그램 로그를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-124">In contrast, authenticated users can read and write to the Application log.</span></span> [!INCLUDE[wxp](../../../../includes/wxp-md.md)]<span data-ttu-id="17f65-125">는 기본적으로 감사 이벤트를 응용 프로그램 로그에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-125"> writes audit events to the Application log by default.</span></span> <span data-ttu-id="17f65-126">이 로그는 모든 인증된 사용자에게 표시되는 개인 정보를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-126">The log can also contain personal information that is visible to all authenticated users.</span></span>  
  
## <a name="suppressing-audit-failures"></a><span data-ttu-id="17f65-127">감사 실패 억제</span><span class="sxs-lookup"><span data-stu-id="17f65-127">Suppressing Audit Failures</span></span>  
 <span data-ttu-id="17f65-128">또한 감사 중에 감사 실패를 억제할지 여부를 지정하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-128">Another option during auditing is whether to suppress any audit failure.</span></span> <span data-ttu-id="17f65-129">기본적으로 감사 실패는 응용 프로그램에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-129">By default, an audit failure does not affect an application.</span></span> <span data-ttu-id="17f65-130">그러나 필요한 경우 이 옵션을 `false`로 설정할 수 있습니다. 그러면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-130">If required, however, you can set the option to `false`, which causes an exception to be thrown.</span></span>  
  
## <a name="programming-auditing"></a><span data-ttu-id="17f65-131">감사 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="17f65-131">Programming Auditing</span></span>  
 <span data-ttu-id="17f65-132">프로그래밍 방식이나 구성을 통해 감사 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-132">You can specify auditing behavior either programmatically or through configuration.</span></span>  
  
### <a name="auditing-classes"></a><span data-ttu-id="17f65-133">감사 클래스</span><span class="sxs-lookup"><span data-stu-id="17f65-133">Auditing Classes</span></span>  
 <span data-ttu-id="17f65-134">다음 표에서는 감사 동작을 프로그래밍하는 데 사용되는 클래스와 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-134">The following table describes the classes and properties used to program auditing behavior.</span></span>  
  
|<span data-ttu-id="17f65-135">클래스</span><span class="sxs-lookup"><span data-stu-id="17f65-135">Class</span></span>|<span data-ttu-id="17f65-136">설명</span><span class="sxs-lookup"><span data-stu-id="17f65-136">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>|<span data-ttu-id="17f65-137">감사 옵션을 서비스 동작으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-137">Enables setting options for auditing as a service behavior.</span></span>|  
|<xref:System.ServiceModel.AuditLogLocation>|<span data-ttu-id="17f65-138">기록할 로그를 지정하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-138">Enumeration to specify which log to write to.</span></span> <span data-ttu-id="17f65-139">가능한 값은 기본값, 응용 프로그램 및 보안입니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-139">The possible values are Default, Application, and Security.</span></span> <span data-ttu-id="17f65-140">기본값을 선택하면 운영 체제에서 실제 로그 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-140">When you select Default, the operating system determines the actual log location.</span></span> <span data-ttu-id="17f65-141">이 항목의 뒷부분에 나오는 "응용 프로그램 또는 보안 이벤트 로그 선택" 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="17f65-141">See the "Application or Security Event Log Choice" section later in this topic.</span></span>|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>|<span data-ttu-id="17f65-142">메시지 수준에서 감사할 메시지 인증 이벤트의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-142">Specifies which types of message authentication events are audited at the message level.</span></span> <span data-ttu-id="17f65-143">`None`, `Failure`, `Success` 및 `SuccessOrFailure` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-143">The choices are `None`, `Failure`, `Success`, and `SuccessOrFailure`.</span></span>|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>|<span data-ttu-id="17f65-144">서비스 수준에서 감사할 서비스 인증 이벤트의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-144">Specifies which types of service authorization events are audited at the service level.</span></span> <span data-ttu-id="17f65-145">`None`, `Failure`, `Success` 및 `SuccessOrFailure` 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-145">The choices are `None`, `Failure`, `Success`, and `SuccessOrFailure`.</span></span>|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>|<span data-ttu-id="17f65-146">감사가 실패할 경우 클라이언트 요청 처리 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-146">Specifies what happens to the client request when auditing fails.</span></span> <span data-ttu-id="17f65-147">예를 들어, 서비스에서 보안 로그에 기록하려고 시도하지만 `SeAuditPrivilege`가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="17f65-147">For example, when the service attempts to write to the security log, but does not have `SeAuditPrivilege`.</span></span> <span data-ttu-id="17f65-148">기본값 `true`를 지정했다면 실패가 무시되고 클라이언트 요청이 정상적으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-148">The default value of `true` indicates that failures are ignored, and the client request is processed normally.</span></span>|  
  
 <span data-ttu-id="17f65-149">감사 이벤트를 기록 하도록 응용 프로그램을 설정 하는 예제를 보려면 [하는 방법: 보안 이벤트 감사](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-149">For an example of setting up an application to log audit events, see [How to: Audit Security Events](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span>  
  
### <a name="configuration"></a><span data-ttu-id="17f65-150">구성</span><span class="sxs-lookup"><span data-stu-id="17f65-150">Configuration</span></span>  
 <span data-ttu-id="17f65-151">구성 추가 하 여 감사 동작을 지정 하려면 사용할 수도 있습니다는 [ \<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) 아래는 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-151">You can also use configuration to specify auditing behavior by adding a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) under the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span> <span data-ttu-id="17f65-152">요소를 추가 해야는 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-152">You must add the element under a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) as shown in the following code.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <behavior>  
        <!— auditLogLocation="Application" or "Security" -—>  
        <serviceSecurityAudit  
                  auditLogLocation="Application"  
                  suppressAuditFailure="true"  
                  serviceAuthorizationAuditLevel="Failure"  
                  messageAuthenticationAuditLevel="SuccessOrFailure" />   
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="17f65-153">감사가 설정되어 있지만 `auditLogLocation`이 지정되어 있지 않으면 보안 로그 기록을 지원하는 플랫폼의 기본 로그 이름은 "Security" 로그이고, 그렇지 않으면 "Application" 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-153">If auditing is enabled and an `auditLogLocation` is not specified, the default log name is "Security" log for the platform supporting writing to the Security log; otherwise, it is "Application" log.</span></span> <span data-ttu-id="17f65-154">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 및 [!INCLUDE[wv](../../../../includes/wv-md.md)] 운영 체제만 보안 로그에 쓰기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-154">Only the [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wv](../../../../includes/wv-md.md)] operating systems support writing to the Security log.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="17f65-155"> 이 항목의 뒷부분에 나오는 "운영 체제".</span><span class="sxs-lookup"><span data-stu-id="17f65-155"> the "Operating System" section later in this topic.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="17f65-156">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="17f65-156">Security Considerations</span></span>  
 <span data-ttu-id="17f65-157">악의적인 사용자가 감사가 설정된 사실을 알고 있다면 잘못된 메시지를 보내 감사 항목을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-157">If a malicious user knows that auditing is enabled, that attacker can send invalid messages that cause audit entries to be written.</span></span> <span data-ttu-id="17f65-158">이런 식으로 감사 로그가 채워지면 감사 시스템이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-158">If the audit log is filled in this manner, the auditing system fails.</span></span> <span data-ttu-id="17f65-159">이 문제를 완화하려면 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 속성을 `true`로 설정하고 이벤트 뷰어의 속성을 사용하여 감사 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-159">To mitigate this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true` and use the properties of the Event Viewer to control the auditing behavior.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="17f65-160">Microsoft 지원 문서 보기 및에서 사용할 수 있는 Windows XP에서 이벤트 뷰어를 사용 하 여 이벤트 로그 관리에 [보고 Windows XP에서 이벤트 뷰어에서 이벤트 로그를 관리 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=89150)합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-160"> the Microsoft Support article on viewing and managing event logs by using the Event Viewer in Windows XP available at [How to view and manage event logs in Event Viewer in Windows XP](http://go.microsoft.com/fwlink/?LinkId=89150).</span></span>  
  
 <span data-ttu-id="17f65-161">[!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 응용 프로그램 로그에 기록되는 감사 이벤트는 모든 인증된 사용자가 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-161">Audit events that are written to the Application Log on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] are visible to any authenticated user.</span></span>  
  
## <a name="choosing-between-application-and-security-event-logs"></a><span data-ttu-id="17f65-162">응용 프로그램 및 보안 이벤트 로그 선택</span><span class="sxs-lookup"><span data-stu-id="17f65-162">Choosing Between Application and Security Event Logs</span></span>  
 <span data-ttu-id="17f65-163">다음 표에서는 응용 프로그램 이벤트 로그에 기록할지 보안 이벤트 로그에 기록할지 여부를 선택하는 데 도움이 되는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-163">The following tables provide information to help you choose whether to log into the Application or the Security event log.</span></span>  
  
#### <a name="operating-system"></a><span data-ttu-id="17f65-164">운영 체제</span><span class="sxs-lookup"><span data-stu-id="17f65-164">Operating System</span></span>  
  
|<span data-ttu-id="17f65-165">시스템</span><span class="sxs-lookup"><span data-stu-id="17f65-165">System</span></span>|<span data-ttu-id="17f65-166">응용 프로그램 로그</span><span class="sxs-lookup"><span data-stu-id="17f65-166">Application log</span></span>|<span data-ttu-id="17f65-167">보안 로그</span><span class="sxs-lookup"><span data-stu-id="17f65-167">Security log</span></span>|  
|------------|---------------------|------------------|  
|[!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]<span data-ttu-id="17f65-168"> 이상</span><span class="sxs-lookup"><span data-stu-id="17f65-168"> or later</span></span>|<span data-ttu-id="17f65-169">지원함</span><span class="sxs-lookup"><span data-stu-id="17f65-169">Supported</span></span>|<span data-ttu-id="17f65-170">지원 안 함</span><span class="sxs-lookup"><span data-stu-id="17f65-170">Not supported</span></span>|  
|[!INCLUDE[ws2003sp1](../../../../includes/ws2003sp1-md.md)]<span data-ttu-id="17f65-171"> 및 [!INCLUDE[wv](../../../../includes/wv-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17f65-171"> and [!INCLUDE[wv](../../../../includes/wv-md.md)]</span></span>|<span data-ttu-id="17f65-172">지원함</span><span class="sxs-lookup"><span data-stu-id="17f65-172">Supported</span></span>|<span data-ttu-id="17f65-173">스레드 컨텍스트에 `SeAuditPrivilege`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-173">Thread context must possess `SeAuditPrivilege`</span></span>|  
  
#### <a name="other-factors"></a><span data-ttu-id="17f65-174">기타 요소</span><span class="sxs-lookup"><span data-stu-id="17f65-174">Other Factors</span></span>  
 <span data-ttu-id="17f65-175">다음 표에서는 운영 체제 이외에 로깅 사용을 제어하는 기타 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-175">In addition to the operating system, the following table describes other settings that control the enablement of logging.</span></span>  
  
|<span data-ttu-id="17f65-176">요소</span><span class="sxs-lookup"><span data-stu-id="17f65-176">Factor</span></span>|<span data-ttu-id="17f65-177">응용 프로그램 로그</span><span class="sxs-lookup"><span data-stu-id="17f65-177">Application log</span></span>|<span data-ttu-id="17f65-178">보안 로그</span><span class="sxs-lookup"><span data-stu-id="17f65-178">Security log</span></span>|  
|------------|---------------------|------------------|  
|<span data-ttu-id="17f65-179">정책 관리 감사</span><span class="sxs-lookup"><span data-stu-id="17f65-179">Audit policy management</span></span>|<span data-ttu-id="17f65-180">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="17f65-180">Not applicable.</span></span>|<span data-ttu-id="17f65-181">구성과 함께 보안 로그는 LSA(로컬 보안 기관) 정책에 의해서도 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-181">Along with configuration, the Security log is also controlled by the local security authority (LSA) policy.</span></span> <span data-ttu-id="17f65-182">"개체 액세스 감사" 범주 또한 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-182">The "Audit object access" category must also be enabled.</span></span>|  
|<span data-ttu-id="17f65-183">기본 사용자 경험</span><span class="sxs-lookup"><span data-stu-id="17f65-183">Default user experience</span></span>|<span data-ttu-id="17f65-184">모든 인증된 사용자는 응용 프로그램 로그에 기록할 수 있으므로 응용 프로그램 프로세스를 위한 추가 권한 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-184">All authenticated users can write to the Application log, so no additional permission step is needed for application processes.</span></span>|<span data-ttu-id="17f65-185">응용 프로그램 프로세스(컨텍스트)에 `SeAuditPrivilege`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17f65-185">The application process (context) must have `SeAuditPrivilege`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17f65-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17f65-186">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 <xref:System.ServiceModel.AuditLogLocation>  
 [<span data-ttu-id="17f65-187">보안 개요</span><span class="sxs-lookup"><span data-stu-id="17f65-187">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="17f65-188">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="17f65-188">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="17f65-189">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="17f65-189">How to: Audit Security Events</span></span>](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [<span data-ttu-id="17f65-190">\<serviceSecurityAudit ></span><span class="sxs-lookup"><span data-stu-id="17f65-190">\<serviceSecurityAudit></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)  
 [<span data-ttu-id="17f65-191">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="17f65-191">\<behaviors></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [<span data-ttu-id="17f65-192">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="17f65-192">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
