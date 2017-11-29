---
title: "방법: 엔터프라이즈에서 끝점 잠그기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ada33c6b6ea0995d0390040710ed1b2457b9e4af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a><span data-ttu-id="7e75a-102">방법: 엔터프라이즈에서 끝점 잠그기</span><span class="sxs-lookup"><span data-stu-id="7e75a-102">How to: Lock Down Endpoints in the Enterprise</span></span>
<span data-ttu-id="7e75a-103">대형 엔터프라이즈에서는 응용 프로그램을 엔터프라이즈 보안 정책에 따라 개발해야 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-103">Large enterprises often require that applications are developed in compliance with enterprise security policies.</span></span> <span data-ttu-id="7e75a-104">다음 항목에서는 컴퓨터에 설치된 모든 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 응용 프로그램의 유효성을 확인할 수 있는 클라이언트 끝점 유효성 검사기를 개발하고 설치하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-104">The following topic discusses how to develop and install a client endpoint validator that can be used to validate all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client applications installed on computers.</span></span>  
  
 <span data-ttu-id="7e75a-105">이 끝점 동작은 클라이언트에 추가 되기 때문에 유효성 검사기는 클라이언트 유효성 검사기가이 경우 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) machine.config 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-105">In this case, the validator is a client validator because this endpoint behavior is added to the client [\<commonBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) section in the machine.config file.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7e75a-106">는 클라이언트 응용 프로그램 전용의 공통 끝점 동작을 로드하고 서비스 응용 프로그램 전용의 공통 서비스 동작을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-106"> loads common endpoint behaviors only for client applications and loads common service behaviors only for service applications.</span></span> <span data-ttu-id="7e75a-107">서비스 응용 프로그램에 동일한 유효성 검사기를 설치하려면 유효성 검사기가 서비스 동작이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-107">To install this same validator for service applications, the validator must be a service behavior.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7e75a-108">[ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) 섹션.</span><span class="sxs-lookup"><span data-stu-id="7e75a-108"> the [\<commonBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) section.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7e75a-109">서비스 또는 끝점 동작으로 표시 되어 있지는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA)에 추가 되는 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) 구성 파일의 섹션에는 응용 프로그램이 부분 신뢰에서 실행 될 때 실행 되지 않습니다 이 경우 환경과 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-109">Service or endpoint behaviors not marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute (APTCA) that are added to the [\<commonBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) section of a configuration file are not run when the application runs in a partial trust environment, and no exception is thrown when this occurs.</span></span> <span data-ttu-id="7e75a-110">유효성 검사기와 같은 일반 동작을 실행하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-110">To enforce the running of common behaviors such as validators, you must either:</span></span>  
>   
>  <span data-ttu-id="7e75a-111">-- 부분 신뢰 응용 프로그램으로 배포될 때 실행될 수 있도록 일반 동작을 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-111">-- Mark your common behavior with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute so that it can run when deployed as a Partial Trust application.</span></span> <span data-ttu-id="7e75a-112">APTCA로 표시된 어셈블리가 실행되지 않도록 컴퓨터에 레지스트리 항목을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-112">Note that a registry entry can be set on the computer to prevent APTCA-marked assemblies from running..</span></span>  
>   
>  <span data-ttu-id="7e75a-113">-- 부분 신뢰 환경에서 응용 프로그램을 실행하기 위해 사용자가 코드 액세스 보안 설정을 수정할 수 없는 완전 신뢰 응용 프로그램으로서 응용 프로그램이 배포되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-113">-- Ensure that if the application is deployed as a fully-trusted application that users cannot modify the code-access security settings to run the application in a Partial Trust environment.</span></span> <span data-ttu-id="7e75a-114">사용자가 보안 설정을 수정할 수 있는 경우 사용자 지정 유효성 검사기가 실행되지 않고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-114">If they can do so, the custom validator does not run and no exception is thrown.</span></span> <span data-ttu-id="7e75a-115">이 보장 하 한 가지 방법은 참조는 `levelfinal` 옵션을 사용 하 여 [코드 액세스 보안 정책 도구 (Caspol.exe)](http://go.microsoft.com/fwlink/?LinkId=248222)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-115">For one way to ensure this, see the `levelfinal` option using [Code Access Security Policy Tool (Caspol.exe)](http://go.microsoft.com/fwlink/?LinkId=248222).</span></span>  
>   
>  <span data-ttu-id="7e75a-116">자세한 내용은 참조 [부분 신뢰 모범 사례](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) 및 [배포 시나리오 지원](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-116">For more information, see [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) and [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).</span></span>  
  
### <a name="to-create-the-endpoint-validator"></a><span data-ttu-id="7e75a-117">끝점 유효성 검사기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7e75a-117">To create the endpoint validator</span></span>  
  
1.  <span data-ttu-id="7e75a-118"><xref:System.ServiceModel.Description.IEndpointBehavior> 메서드의 원하는 유효성 검사 단계를 사용하여 <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-118">Create an <xref:System.ServiceModel.Description.IEndpointBehavior> with the desired validation steps in the <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A> method.</span></span> <span data-ttu-id="7e75a-119">코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-119">The following code provides an example.</span></span> <span data-ttu-id="7e75a-120">(의 `InternetClientValidatorBehavior` 에서 가져온 것은 [보안 유효성 검사](../../../../docs/framework/wcf/samples/security-validation.md) 샘플.)</span><span class="sxs-lookup"><span data-stu-id="7e75a-120">(The `InternetClientValidatorBehavior` is taken from the [Security Validation](../../../../docs/framework/wcf/samples/security-validation.md) sample.)</span></span>  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  <span data-ttu-id="7e75a-121">1단계에서 만든 끝점 유효성 검사기를 등록할 새 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-121">Create new <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> that registers the endpoint validator created in step 1.</span></span> <span data-ttu-id="7e75a-122">다음 코드 예제에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-122">The following code example shows this.</span></span> <span data-ttu-id="7e75a-123">(이 예제에 대 한 원본 코드는 [보안 유효성 검사](../../../../docs/framework/wcf/samples/security-validation.md) 샘플.)</span><span class="sxs-lookup"><span data-stu-id="7e75a-123">(The original code for this example is in the [Security Validation](../../../../docs/framework/wcf/samples/security-validation.md) sample.)</span></span>  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  <span data-ttu-id="7e75a-124">컴파일된 어셈블리가 강력한 이름으로 서명되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-124">Make sure the compiled assembly is signed with a strong name.</span></span> <span data-ttu-id="7e75a-125">자세한 내용은 참조는 [강력한 이름 도구 (SN입니다. EXE)](http://go.microsoft.com/fwlink/?LinkId=248217) 및 해당 하는 언어에 대 한 컴파일러 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-125">For details, see the [Strong Name Tool (SN.EXE)](http://go.microsoft.com/fwlink/?LinkId=248217) and the compiler commands for your language.</span></span>  
  
### <a name="to-install-the-validator-into-the-target-computer"></a><span data-ttu-id="7e75a-126">대상 컴퓨터에 유효성 검사기를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="7e75a-126">To install the validator into the target computer</span></span>  
  
1.  <span data-ttu-id="7e75a-127">적절한 메커니즘을 사용하여 끝점 유효성 검사기를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-127">Install the endpoint validator using the appropriate mechanism.</span></span> <span data-ttu-id="7e75a-128">엔터프라이즈에서는 그룹 정책 및 SMS(Systems Management Server)를 사용해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-128">In an enterprise, this can be using Group Policy and Systems Management Server (SMS).</span></span>  
  
2.  <span data-ttu-id="7e75a-129">강력한 이름의 어셈블리를 사용 하 여 전역 어셈블리 캐시에 설치 된 [Gacutil.exe (전역 어셈블리 캐시 도구)](http://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-129">Install the strongly-named assembly into the global assembly cache using the [Gacutil.exe (Global Assembly Cache Tool)](http://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx).</span></span>  
  
3.  <span data-ttu-id="7e75a-130">다음 작업에 <xref:System.Configuration?displayProperty=nameWithType> 네임스페이스 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-130">Use the <xref:System.Configuration?displayProperty=nameWithType> namespace types to:</span></span>  
  
    1.  <span data-ttu-id="7e75a-131">확장을 추가 [ \<behaviorExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) 완전히 정규화 된 유형 이름을 사용 하 여 섹션 및 고 요소를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-131">Add the extension to the [\<behaviorExtensions>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) section using a fully-qualified type name and lock the element.</span></span>  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  <span data-ttu-id="7e75a-132">동작 요소를 추가 `EndpointBehaviors` 의 속성은 [ \<c o m m >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) 섹션 및 고 요소를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-132">Add the behavior element to the `EndpointBehaviors` property of the [\<commonBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) section and lock the element.</span></span> <span data-ttu-id="7e75a-133">서비스에 유효성 검사기를 설치하려면 유효성 검사기가 <xref:System.ServiceModel.Description.IServiceBehavior>이어야 하며 `ServiceBehaviors` 속성에 추가되어야 합니다. 다음 코드 예제에서는 a 및 b 단계 후 올바른 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-133">(To install the validator on the service, the validator must be an <xref:System.ServiceModel.Description.IServiceBehavior> and added to the `ServiceBehaviors` property.) The following code example shows the proper configuration after steps a.</span></span> <span data-ttu-id="7e75a-134">단, 강력한 이름이 없다는 한 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-134">and b., with the sole exception that there is no strong name.</span></span>  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  <span data-ttu-id="7e75a-135">machine.config 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-135">Save the machine.config file.</span></span> <span data-ttu-id="7e75a-136">다음 코드 예제에서는 3단계의 모든 작업을 수행하며 수정된 machine.config 파일의 복사본을 로컬에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-136">The following code example performs all the tasks in step 3 but saves a copy of the modified machine.config file locally.</span></span>  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="7e75a-137">예제</span><span class="sxs-lookup"><span data-stu-id="7e75a-137">Example</span></span>  
 <span data-ttu-id="7e75a-138">다음 코드 예제에서는 일반 동작을 machine.config 파일에 추가하고 복사본을 디스크에 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-138">The following code example shows how to add a common behavior to the machine.config file and save a copy to the disk.</span></span> <span data-ttu-id="7e75a-139">`InternetClientValidatorBehavior` 에서 가져온 것은 [보안 유효성 검사](../../../../docs/framework/wcf/samples/security-validation.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="7e75a-139">The `InternetClientValidatorBehavior` is taken from the [Security Validation](../../../../docs/framework/wcf/samples/security-validation.md) sample.</span></span>  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="7e75a-140">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="7e75a-140">.NET Framework Security</span></span>  
 <span data-ttu-id="7e75a-141">구성 파일 요소를 암호화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e75a-141">You may also want to encrypt the configuration file elements.</span></span> <span data-ttu-id="7e75a-142">자세한 내용은 참고 항목 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e75a-142">For more information, see the See Also section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e75a-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e75a-143">See Also</span></span>  
 [<span data-ttu-id="7e75a-144">DPAPI를 사용 하 여 구성 파일 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="7e75a-144">Encrypting configuration file elements using DPAPI</span></span>](http://go.microsoft.com/fwlink/?LinkId=94954)  
 [<span data-ttu-id="7e75a-145">RSA를 사용 하 여 구성 파일 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="7e75a-145">Encrypting configuration file elements using RSA</span></span>](http://go.microsoft.com/fwlink/?LinkId=94955)
