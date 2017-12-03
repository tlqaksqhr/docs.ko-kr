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
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="6c322-102">방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="6c322-102">How to: Create a Custom Authorization Manager for a Service</span></span>
<span data-ttu-id="6c322-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 ID 모델 인프라에서는 확장 가능한 클레임 기반의 권한 부여 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="6c322-104">클레임은 토큰에서 추출되어 사용자 지정 권한 부여 정책에 의해 선택적으로 처리된 다음,<xref:System.IdentityModel.Policy.AuthorizationContext>에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="6c322-105">권한 부여 관리자는 <xref:System.IdentityModel.Policy.AuthorizationContext>에서 클레임을 검사하여 권한 부여 결정을 내립니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>  
  
 <span data-ttu-id="6c322-106">기본적으로 권한 부여는 <xref:System.ServiceModel.ServiceAuthorizationManager> 클래스에서 결정되지만, 사용자 지정 권한 부여 관리자를 만들어 이러한 결정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="6c322-107">사용자 지정 권한 부여 관리자를 만들려면 <xref:System.ServiceModel.ServiceAuthorizationManager>에서 파생되는 클래스를 만든 다음 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="6c322-108">권한 부여는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드에서 결정되며, 액세스가 허용되면 `true`를 반환하고 액세스가 거부되면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>  
  
 <span data-ttu-id="6c322-109">권한 부여 결정이 메시지 본문 내용에 따라 달라지는 경우 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>  
  
 <span data-ttu-id="6c322-110">성능 문제 때문에 가능하다면 권한 부여 결정 시 메시지 본문에 액세스하지 않아도 되도록 응용 프로그램을 다시 디자인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>  
  
 <span data-ttu-id="6c322-111">서비스에 대한 사용자 지정 권한 부여 관리자는 코드 또는 구성을 통해 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>  
  
### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="6c322-112">사용자 지정 권한 부여 관리자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6c322-112">To create a custom authorization manager</span></span>  
  
1.  <span data-ttu-id="6c322-113"><xref:System.ServiceModel.ServiceAuthorizationManager> 클래스에서 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  <span data-ttu-id="6c322-114"><xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>  
  
     <span data-ttu-id="6c322-115"><xref:System.ServiceModel.OperationContext> 메서드에 전달되는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>를 사용하여 권한 부여 결정을 내립니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>  
  
     <span data-ttu-id="6c322-116">다음 코드 예제에서는 권한 부여 결정을 내리기 위해 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> 메서드를 사용하여 사용자 지정 클레임 `http://www.contoso.com/claims/allowedoperation`을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="6c322-117">코드를 사용하여 사용자 지정 권한 부여 관리자를 등록하려면</span><span class="sxs-lookup"><span data-stu-id="6c322-117">To register a custom authorization manager using code</span></span>  
  
1.  <span data-ttu-id="6c322-118">사용자 지정 권한 부여 관리자의 인스턴스를 만들어 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>  
  
     <span data-ttu-id="6c322-119"><xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 속성을 사용하여 <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>  
  
     <span data-ttu-id="6c322-120">다음 코드 예제에서는 `MyServiceAuthorizationManager` 사용자 지정 권한 부여 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="6c322-121">구성을 사용하여 사용자 지정 권한 부여 관리자를 등록하려면</span><span class="sxs-lookup"><span data-stu-id="6c322-121">To register a custom authorization manager using configuration</span></span>  
  
1.  <span data-ttu-id="6c322-122">서비스에 대한 구성 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-122">Open the configuration file for the service.</span></span>  
  
2.  <span data-ttu-id="6c322-123">추가 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 에 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span>  
  
     <span data-ttu-id="6c322-124">에 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), 추가 `serviceAuthorizationManagerType` 특성 및 사용자 지정 권한 부여 관리자를 나타내는 형식에 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-124">To the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>  
  
3.  <span data-ttu-id="6c322-125">클라이언트와 서비스 간의 통신을 보안하는 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-125">Add a binding that secures the communication between the client and service.</span></span>  
  
     <span data-ttu-id="6c322-126">이 통신에 대해 선택된 바인딩에 따라 <xref:System.IdentityModel.Policy.AuthorizationContext>에 추가되는 클레임이 결정되고, 사용자 지정 권한 부여 관리자는 이 클레임을 사용하여 권한 부여 결정을 내립니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="6c322-127">시스템 제공 바인딩에 대 한 자세한 내용은 참조 하십시오. [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-127">For more details about the system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
4.  <span data-ttu-id="6c322-128">추가 하 여 서비스 끝점에 동작을 연결할는 [ \<서비스 >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) 요소 값을 설정 하 고는 `behaviorConfiguration` 특성에 대 한 이름 특성의 값으로는 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
     <span data-ttu-id="6c322-129">서비스 끝점을 구성 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 구성에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
     <span data-ttu-id="6c322-130">다음 코드 예제에서는 `Samples.MyServiceAuthorizationManager` 사용자 지정 권한 부여 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>  
  
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
    >  <span data-ttu-id="6c322-131">serviceAuthorizationManagerType을 지정할 경우 문자열에 정규화된 형식 이름이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="6c322-132">콤마 및 형식이 정의된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="6c322-133">어셈블리 이름을 지정하지 않을 경우 WCF는 System.ServiceModel.dll에서 형식 로드를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c322-134">예제</span><span class="sxs-lookup"><span data-stu-id="6c322-134">Example</span></span>  
 <span data-ttu-id="6c322-135">다음 코드 예제에서는 <xref:System.ServiceModel.ServiceAuthorizationManager> 메서드 재정의를 포함하는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 클래스의 기본 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="6c322-136">예제 코드에서는 <xref:System.IdentityModel.Policy.AuthorizationContext>에서 사용자 지정 클레임을 검사하고 해당 사용자 지정 클레임의 리소스가 `true`의 동작 값과 일치하면 <xref:System.ServiceModel.OperationContext>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="6c322-137">구현은 보다 완전 한 <xref:System.ServiceModel.ServiceAuthorizationManager> 클래스를 참조 하십시오 [권한 부여 정책](../../../../docs/framework/wcf/samples/authorization-policy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c322-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6c322-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c322-138">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="6c322-139">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="6c322-139">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [<span data-ttu-id="6c322-140">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="6c322-140">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
