---
title: "보안 개요 2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33e09965-61d5-48cc-9e8c-3b047cc4f194
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c952a79b70314ff9de195da322efd78d54176201
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="security-overview"></a><span data-ttu-id="6f29d-102">보안 개요</span><span class="sxs-lookup"><span data-stu-id="6f29d-102">Security Overview</span></span>
<span data-ttu-id="6f29d-103">응용 프로그램 보안은 지속적인 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-103">Securing an application is an ongoing process.</span></span> <span data-ttu-id="6f29d-104">새로운 기술로 인해 앞으로 어떠한 공격이 가해질지 예측할 수 없기 때문에 개발자가 응용 프로그램이 모든 공격으로부터 안전하다고 장담하는 것은 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-104">There will never be a point where a developer can guarantee that an application is safe from all attacks, because it is impossible to predict what kinds of future attacks new technologies will bring about.</span></span> <span data-ttu-id="6f29d-105">반대로, 아직까지 아무도 시스템의 보안 허점을 발견(또는 발표)하지 않았더라도 허점이 없다고 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-105">Conversely, just because nobody has yet discovered (or published) security flaws in a system does not mean that none exist or could exist.</span></span> <span data-ttu-id="6f29d-106">보안 계획은 프로젝트 디자인 단계에서 수립해야 하며 아울러 응용 프로그램의 수명이 다할 때까지 이러한 보안을 어떻게 유지할지도 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-106">You need to plan for security during the design phase of the project, as well as plan how security will be maintained over the lifetime of the application.</span></span>  
  
## <a name="design-for-security"></a><span data-ttu-id="6f29d-107">보안을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="6f29d-107">Design for Security</span></span>  
 <span data-ttu-id="6f29d-108">안전한 응용 프로그램을 개발하는 데 있어서 가장 큰 문제 중 하나는 보안이 프로젝트의 코드가 완성된 후에야 구현되는 사후 대책이라는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-108">One of the biggest problems in developing secure applications is that security is often an afterthought, something to implement after a project is code-complete.</span></span> <span data-ttu-id="6f29d-109">개발 초기부터 응용 프로그램에 보안 기능을 포함해야지 그렇지 않으면 보안에 대해 제대로 고려하지 않게 되므로 결국 안전하지 않은 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-109">Not building security into an application at the outset leads to insecure applications because little thought has been given to what makes an application secure.</span></span>  
  
 <span data-ttu-id="6f29d-110">보안을 마지막 단계에 구현하면 소프트웨어가 새로운 제한에 부딪혀 제 기능을 못하거나 예기치 않은 기능을 수용하기 위해 다시 작성되어야 하므로 버그가 많아집니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-110">Last minute security implementation leads to more bugs, as software breaks under the new restrictions or has to be rewritten to accommodate unanticipated functionality.</span></span> <span data-ttu-id="6f29d-111">코드 한 줄을 수정할 때마다 새로운 버그가 발생할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-111">Every line of revised code contains the possibility of introducing a new bug.</span></span> <span data-ttu-id="6f29d-112">따라서 개발 프로세스 초기에 보안을 고려하여 새로운 기능 개발과 함께 진행할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-112">For this reason, you should consider security early in the development process so that it can proceed in tandem with the development of new features.</span></span>  
  
### <a name="threat-modeling"></a><span data-ttu-id="6f29d-113">위협 모델링</span><span class="sxs-lookup"><span data-stu-id="6f29d-113">Threat Modeling</span></span>  
 <span data-ttu-id="6f29d-114">노출되어 있는 모든 잠재적인 공격을 이해하지 못하면 시스템을 공격으로부터 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-114">You cannot protect a system against attack unless you understand all the potential attacks that it is exposed to.</span></span> <span data-ttu-id="6f29d-115">보안 위협 평가 프로세스가 호출 *위협 모델링*, 가능성 및 ADO.NET 응용 프로그램의 보안 위험 그 결과 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-115">The process of evaluating security threats, called *threat modeling*, is necessary to determine the likelihood and ramifications of security breaches in your ADO.NET application.</span></span>  
  
 <span data-ttu-id="6f29d-116">위협 모델링은 크게 공격자의 의도 파악, 시스템 보안 특성 결정, 위협 요소 확인이라는 세 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-116">Threat modeling is composed of three high-level steps: understanding the adversary’s view, characterizing the security of the system, and determining threats.</span></span>  
  
 <span data-ttu-id="6f29d-117">위협 모델링은 응용 프로그램의 취약성을 평가하여 가장 위험한 영역, 즉 가장 중요한 데이터가 노출되는 영역을 찾아내기 위한 반복되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-117">Threat modeling is an iterative approach to assessing vulnerabilities in your application to find those that are the most dangerous because they expose the most sensitive data.</span></span> <span data-ttu-id="6f29d-118">취약한 영역을 식별한 후에는 심각도 순으로 영역에 등급을 매기고, 위협에 대한 대응책을 마련한 다음 여기에도 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-118">Once you identify the vulnerabilities, you rank them in order of severity and create a prioritized set of countermeasures to counter the threats.</span></span>  
  
 <span data-ttu-id="6f29d-119">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f29d-119">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="6f29d-120">리소스</span><span class="sxs-lookup"><span data-stu-id="6f29d-120">Resource</span></span>|<span data-ttu-id="6f29d-121">설명</span><span class="sxs-lookup"><span data-stu-id="6f29d-121">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6f29d-122">[위협 모델링](http://go.microsoft.com/fwlink/?LinkId=98353) MSDN Security Developer Center에서 사이트</span><span class="sxs-lookup"><span data-stu-id="6f29d-122">The [Threat Modeling](http://go.microsoft.com/fwlink/?LinkId=98353) site on the MSDN Security Developer Center</span></span>|<span data-ttu-id="6f29d-123">이 페이지의 리소스는 위협 모델링 프로세스를 이해하고 응용 프로그램을 안전하게 보호하는 데 사용할 수 있는 위협 모델을 만드는 데 유용한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-123">The resources on this page will help you understand the threat modeling process and build threat models that you can use to secure your own applications</span></span>|  
  
## <a name="the-principle-of-least-privilege"></a><span data-ttu-id="6f29d-124">최소 권한의 원칙</span><span class="sxs-lookup"><span data-stu-id="6f29d-124">The Principle of Least Privilege</span></span>  
 <span data-ttu-id="6f29d-125">응용 프로그램을 디자인하고 빌드하고 배포할 때는 응용 프로그램이 언제든지 공격을 받을 수 있다는 가능성을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-125">When you design, build, and deploy your application, you must assume that your application will be attacked.</span></span> <span data-ttu-id="6f29d-126">대개 이러한 공격은 코드를 실행하는 사용자의 권한으로 실행되는 악의적인 코드에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-126">Often these attacks come from malicious code that executes with the permissions of the user running the code.</span></span> <span data-ttu-id="6f29d-127">또한 악의적이지 않은 코드를 공격자가 악용하여 공격이 시작되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-127">Others can originate with well-intentioned code that has been exploited by an attacker.</span></span> <span data-ttu-id="6f29d-128">보안 계획을 수립할 때는 항상 발생 가능한 최악의 상황을 가정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-128">When planning security, always assume the worst-case scenario will occur.</span></span>  
  
 <span data-ttu-id="6f29d-129">최소 권한으로 코드를 실행함으로써 코드 주변에 가능한 한 많은 방어벽을 치는 것도 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-129">One counter-measure you can employ is to try to erect as many walls around your code as possible by running with least privilege.</span></span> <span data-ttu-id="6f29d-130">최소 권한의 원칙이란 특정 작업을 수행하는 데 필요한 최소한의 시간 동안 필요한 최소한의 코드에 대해서만 권한을 부여하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-130">The principle of least privilege says that any given privilege should be granted to the least amount of code necessary for the shortest duration of time that is required to get the job done.</span></span>  
  
 <span data-ttu-id="6f29d-131">안전한 응용 프로그램을 만드는 가장 좋은 방법은 아무런 권한 없이 시작한 다음 수행하는 특정 작업에 필요한 최소한의 권한만 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-131">The best practice for creating secure applications is to start with no permissions at all and then add the narrowest permissions for the particular task being performed.</span></span> <span data-ttu-id="6f29d-132">반대로, 모든 권한으로 시작한 다음 필요하지 않은 개별 권한을 거부하면 무심결에 부여한 필요 이상의 권한으로 인해 보안 허점이 생길 수 있으므로 결국에는 테스트 및 유지 관리가 어려운 안전하지 않은 응용 프로그램이 만들어지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-132">By contrast, starting with all permissions and then denying individual ones leads to insecure applications that are difficult to test and maintain because security holes may exist from unintentionally granting more permissions than required.</span></span>  
  
 <span data-ttu-id="6f29d-133">응용 프로그램 보안에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f29d-133">For more information on securing your applications, see the following resources.</span></span>  
  
|<span data-ttu-id="6f29d-134">리소스</span><span class="sxs-lookup"><span data-stu-id="6f29d-134">Resource</span></span>|<span data-ttu-id="6f29d-135">설명</span><span class="sxs-lookup"><span data-stu-id="6f29d-135">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="6f29d-136">응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-136">Securing Applications</span></span>](/visualstudio/ide/securing-applications)|<span data-ttu-id="6f29d-137">일반 보안 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-137">Contains links to general security topics.</span></span> <span data-ttu-id="6f29d-138">분산 응용 프로그램, 웹 응용 프로그램, 모바일 응용 프로그램 및 데스크톱 응용 프로그램을 보호하는 방법에 대해 설명하는 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-138">Also contains links to topics for securing distributed applications, Web applications, mobile applications, and desktop applications.</span></span>|  
  
## <a name="code-access-security-cas"></a><span data-ttu-id="6f29d-139">CAS(코드 액세스 보안)</span><span class="sxs-lookup"><span data-stu-id="6f29d-139">Code Access Security (CAS)</span></span>  
 <span data-ttu-id="6f29d-140">CAS(코드 액세스 보안)는 보호된 리소스 및 작업에 대한 코드의 액세스를 제한하는 데 도움이 되는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-140">Code access security (CAS) is a mechanism that helps limit the access that code has to protected resources and operations.</span></span> <span data-ttu-id="6f29d-141">.NET Framework에서 CAS는 다음 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-141">In the .NET Framework, CAS performs the following functions:</span></span>  
  
-   <span data-ttu-id="6f29d-142">다양한 시스템 리소스에 액세스하는 데 필요한 권한을 나타내는 권한 및 권한 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-142">Defines permissions and permission sets that represent the right to access various system resources.</span></span>  
  
-   <span data-ttu-id="6f29d-143">권한 집합을 코드 그룹과 연결하여 관리자가 보안 정책을 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-143">Enables administrators to configure security policy by associating sets of permissions with groups of code (code groups).</span></span>  
  
-   <span data-ttu-id="6f29d-144">코드가 유용한 권한 및 실행되는 데 필요한 권한을 요청할 수 있도록 하며, 코드가 가질 수 없는 권한을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-144">Enables code to request the permissions it requires in order to run, as well as the permissions that would be useful to have, and specifies which permissions the code must never have.</span></span>  
  
-   <span data-ttu-id="6f29d-145">코드에서 요청한 권한과 보안 정책에서 허용한 작업에 따라 로드된 각 어셈블리에 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-145">Grants permissions to each assembly that is loaded, based on the permissions requested by the code and on the operations permitted by security policy.</span></span>  
  
-   <span data-ttu-id="6f29d-146">코드에서 해당 코드의 호출자가 특정 권한을 갖도록 요구할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-146">Enables code to demand that its callers have specific permissions.</span></span>  
  
-   <span data-ttu-id="6f29d-147">코드의 호출자가 디지털 서명을 갖도록 해당 코드가 요구하여 특정 조직이나 사이트의 호출자만이 보호된 코드를 호출할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-147">Enables code to demand that its callers possess a digital signature, thus allowing only callers from a particular organization or site to call the protected code.</span></span>  
  
-   <span data-ttu-id="6f29d-148">호출 스택에 있는 모든 호출자에게 부여된 권한과 해당 호출자가 가져야 하는 권한을 비교하여 런타임에 코드를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-148">Enforces restrictions on code at run time by comparing the granted permissions of every caller on the call stack to the permissions that callers must have.</span></span>  
  
 <span data-ttu-id="6f29d-149">공격이 감행될 경우 발생할 수 있는 피해를 최소화하려면 코드 실행에 꼭 필요한 리소스에 대한 액세스 권한만 부여하는 코드 보안 컨텍스트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-149">To minimize the amount of damage that can occur if an attack succeeds, choose a security context for your code that grants access only to the resources it needs to get its work done and no more.</span></span>  
  
 <span data-ttu-id="6f29d-150">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f29d-150">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="6f29d-151">리소스</span><span class="sxs-lookup"><span data-stu-id="6f29d-151">Resource</span></span>|<span data-ttu-id="6f29d-152">설명</span><span class="sxs-lookup"><span data-stu-id="6f29d-152">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="6f29d-153">코드 액세스 보안 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f29d-153">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)|<span data-ttu-id="6f29d-154">코드 액세스 보안, 역할 기반 보안, 부분적으로 신뢰할 수 있는 환경 간의 상호 작용을 ADO.NET 응용 프로그램의 측면에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-154">Describes the interactions between code access security, role-based security, and partially trusted environments from the perspective of an ADO.NET application.</span></span>|  
|[<span data-ttu-id="6f29d-155">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-155">Code Access Security</span></span>](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="6f29d-156">.NET Framework의 CAS에 대해 설명하는 추가 항목 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-156">Contains links to additional topics describing CAS in the .NET Framework.</span></span>|  
  
## <a name="database-security"></a><span data-ttu-id="6f29d-157">데이터베이스 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-157">Database Security</span></span>  
 <span data-ttu-id="6f29d-158">데이터 소스에도 최소 권한의 원칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-158">The principle of least privilege also applies to your data source.</span></span> <span data-ttu-id="6f29d-159">데이터베이스 보안을 위한 일반적인 지침 중 일부가 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-159">Some general guidelines for database security include:</span></span>  
  
-   <span data-ttu-id="6f29d-160">최소 권한을 사용하여 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-160">Create accounts with the lowest possible privileges.</span></span>  
  
-   <span data-ttu-id="6f29d-161">코드 실행 목적만을 위해서는 사용자에게 관리자 계정에 대한 액세스를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-161">Do not allow users access to administrative accounts just to get code working.</span></span>  
  
-   <span data-ttu-id="6f29d-162">서버측 오류 메시지를 클라이언트 응용 프로그램에 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-162">Do not return server-side error messages to client applications.</span></span>  
  
-   <span data-ttu-id="6f29d-163">클라이언트와 서버 모두에서 모든 입력의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-163">Validate all input at both the client and the server.</span></span>  
  
-   <span data-ttu-id="6f29d-164">매개 변수화된 명령을 사용하고 동적 SQL 문은 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-164">Use parameterized commands and avoid dynamic SQL statements.</span></span>  
  
-   <span data-ttu-id="6f29d-165">보안 위험에 대한 알림을 받을 수 있도록 사용 중인 데이터베이스에 대해 보안 감사 및 로깅 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-165">Enable security auditing and logging for the database you are using so that you are alerted to any security breaches.</span></span>  
  
 <span data-ttu-id="6f29d-166">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f29d-166">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="6f29d-167">리소스</span><span class="sxs-lookup"><span data-stu-id="6f29d-167">Resource</span></span>|<span data-ttu-id="6f29d-168">설명</span><span class="sxs-lookup"><span data-stu-id="6f29d-168">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="6f29d-169">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-169">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)|<span data-ttu-id="6f29d-170">SQL Server를 대상으로 하는 안전한 ADO.NET 응용 프로그램을 만드는 지침을 제공하는 응용 프로그램 시나리오와 함께 SQL Server 보안에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-170">Provides an overview of SQL Server security with application scenarios that provide guidance for creating secure ADO.NET applications that target SQL Server.</span></span>|  
|[<span data-ttu-id="6f29d-171">데이터 액세스 전략에 대 한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="6f29d-171">Recommendations for Data Access Strategies</span></span>](http://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)|<span data-ttu-id="6f29d-172">데이터 액세스 및 데이터베이스 작업 수행에 대한 권장 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-172">Provides recommendations for accessing data and performing database operations.</span></span>|  
  
## <a name="security-policy-and-administration"></a><span data-ttu-id="6f29d-173">보안 정책 및 관리</span><span class="sxs-lookup"><span data-stu-id="6f29d-173">Security Policy and Administration</span></span>  
 <span data-ttu-id="6f29d-174">CAS(코드 액세스 보안) 정책을 잘못 관리하면 보안 허점이 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-174">Improperly administering code access security (CAS) policy can potentially create security weaknesses.</span></span> <span data-ttu-id="6f29d-175">응용 프로그램을 배포한 후에는 새로운 위협이 출현할 때마다 보안 모니터링 기술을 사용하고 위험을 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-175">Once an application is deployed, techniques for monitoring security should be used and risks evaluated as new threats emerge.</span></span>  
  
 <span data-ttu-id="6f29d-176">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f29d-176">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="6f29d-177">리소스</span><span class="sxs-lookup"><span data-stu-id="6f29d-177">Resource</span></span>|<span data-ttu-id="6f29d-178">설명</span><span class="sxs-lookup"><span data-stu-id="6f29d-178">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="6f29d-179">NIB: 보안 정책 관리</span><span class="sxs-lookup"><span data-stu-id="6f29d-179">NIB: Security Policy Management</span></span>](http://msdn.microsoft.com/library/d754e05d-29dc-4d3a-a2c2-95eaaf1b82b9)|<span data-ttu-id="6f29d-180">보안 정책을 만들고 관리하는 작업에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-180">Provides information on creating and administering security policy.</span></span>|  
|[<span data-ttu-id="6f29d-181">NIB: 보안 정책에 대 한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="6f29d-181">NIB: Security Policy Best Practices</span></span>](http://msdn.microsoft.com/library/d49bc4d5-efb7-4caa-a2fe-e4d3cec63c05)|<span data-ttu-id="6f29d-182">보안 정책을 관리하는 방법에 대해 설명하는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f29d-182">Provides links describing how to administer security policy.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f29d-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f29d-183">See Also</span></span>  
 [<span data-ttu-id="6f29d-184">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-184">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="6f29d-185">네이티브 및 .NET Framework 코드의 PAVE 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-185">PAVE Security in Native and .NET Framework Code</span></span>](http://msdn.microsoft.com/library/bd61be84-c143-409a-a75a-44253724f784)  
 [<span data-ttu-id="6f29d-186">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="6f29d-186">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [<span data-ttu-id="6f29d-187">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="6f29d-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
