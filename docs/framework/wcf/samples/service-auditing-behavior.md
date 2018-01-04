---
title: Service Auditing Behavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 140793e41be012a777dbfa4bf66528612ab33da7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="service-auditing-behavior"></a><span data-ttu-id="8dc20-102">Service Auditing Behavior</span><span class="sxs-lookup"><span data-stu-id="8dc20-102">Service Auditing Behavior</span></span>
<span data-ttu-id="8dc20-103">이 샘플에서는 서비스 작업 중에 서비스 이벤트 감사를 활성화하기 위해 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-103">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span> <span data-ttu-id="8dc20-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="8dc20-105">서비스와 클라이언트를 사용 하 여 구성 된는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-105">The service and client have been configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="8dc20-106">`mode` 특성에는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 가로 설정 된 `Message` 및 `clientCredentialType` 가로 설정 된 `Windows`합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="8dc20-107">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8dc20-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8dc20-109">서비스 구성 파일은 `serviceSecurityAudit` 요소를 사용하여 감사를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-109">The service configuration file uses the `serviceSecurityAudit` element to configure auditing.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="8dc20-110">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-110">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8dc20-111">클라이언트를 종료하려면 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-111">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="8dc20-112">결과 감사 로그는 이벤트 뷰어를 실행하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-112">The resulting audit logs can be seen by running the Event Viewer.</span></span> <span data-ttu-id="8dc20-113">기본적으로 Windows XP에서는 응용 프로그램 로그에서 감사 이벤트를 볼 수 있지만 Windows Server 2003 및 Windows Vista에서는 보안 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-113">By default, on Windows XP the audit events can be seen in the Application Log while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="8dc20-114">Windows Server 2008 및 Windows 7에서는 응용 프로그램 및 서비스 로그에서 감사 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-114">On Windows Server 2008 and Windows 7, the audit events can be seen in the Applications and Services logs.</span></span> <span data-ttu-id="8dc20-115">감사 이벤트의 위치를 설정 하 여 지정할 수는 `auditLogLocation` 특성을 "Application" 또는 "보안"입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-115">The location of audit events can be specified by setting the `auditLogLocation` attribute to "Application" or "Security".</span></span> <span data-ttu-id="8dc20-116">자세한 내용은 참조 [하는 방법: 보안 이벤트 감사](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-116">For more information, see [How to: Audit Security Events](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="8dc20-117">이벤트가 보안 로그에 기록되면 "Success" 및 "Failure"에 대해 LocalSecurityPolicy-> Enable Object Access를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-117">If the events are written in the Security Log the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="8dc20-118">이벤트 로그를 확인하면 감사 이벤트의 소스는 "ServiceModel Audit 3.0.0.0"입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-118">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="8dc20-119">메시지 인증 감사 레코드는 "MessageAuthentication" 범주의 있고 서비스 권한 부여 감사 레코드는 "ServiceAuthorization"의 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-119">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of "ServiceAuthorization".</span></span>  
  
 <span data-ttu-id="8dc20-120">메시지 인증 감사 이벤트는 메시지가 훼손되었는지 여부, 메시지가 만료되었는지 여부 및 클라이언트가 서비스에서 인증될 수 있는지 여부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-120">Message authentication audit events cover whether the message was tampered with, whether the message has expired, and whether the client can authenticate to the service.</span></span> <span data-ttu-id="8dc20-121">이 이벤트는 클라이언트의 ID와 함께 인증의 성공 여부, 메시지와 연결된 동작과 함께 메시지가 보내진 끝점에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-121">They provide information about whether the authentication succeeded or failed along with the identity of the client, and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="8dc20-122">서비스 권한 부여 감사 이벤트는 서비스 권한 부여 관리자가 내린 권한 부여 결정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-122">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="8dc20-123">이 이벤트는 클라이언트 ID와 함께 권한 부여의 성공 여부, 메시지가 보내진 끝점, 메시지와 연결된 동작, 들어오는 메시지에서 생성된 권한 부여 컨텍스트의 식별자 및 액세스 결정을 내린 권한 부여 관리자의 형식에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-123">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message, and the type of the authorization manager that made the access decision.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8dc20-124">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8dc20-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8dc20-125">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8dc20-126">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8dc20-127">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc20-127">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc20-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dc20-128">See Also</span></span>  
 [<span data-ttu-id="8dc20-129">감사</span><span class="sxs-lookup"><span data-stu-id="8dc20-129">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [<span data-ttu-id="8dc20-130">방법: 보안 이벤트 감사</span><span class="sxs-lookup"><span data-stu-id="8dc20-130">How to: Audit Security Events</span></span>](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
