---
title: ".NET microservices 및 웹 응용 프로그램에서 권한 부여에 대 한"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | .NET microservices 및 웹 응용 프로그램에서 권한 부여에 대 한"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 51adda4f5bdb28154f17b9a988ee2d887bf1d461
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="f6503-104">.NET microservices 및 웹 응용 프로그램에서 권한 부여에 대 한</span><span class="sxs-lookup"><span data-stu-id="f6503-104">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="f6503-105">인증을 받은 후 ASP.NET Core 웹 Api 액세스 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-105">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="f6503-106">이 프로세스에 모두 그렇지는 않지만 일부 인증 된 사용자에 게 사용할 수 있는 서비스 Api를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-106">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="f6503-107">[권한 부여](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) 클레임 또는 다른 추론을 검사 합니다. 이때 사용자 지정 정책에 따라 또는 사용자의 역할에 따라 수행 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-107">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="f6503-108">ASP.NET Core MVC 경로에 대 한 액세스를 제한 하는 동작 메서드에 (또는 모든 컨트롤러 작업 권한을 부여 받아야 하는 경우 컨트롤러의 클래스에)에 표시 된 다음 예제와 같이 권한 부여 특성을 적용 하는 것 만큼 쉽게:</span><span class="sxs-lookup"><span data-stu-id="f6503-108">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

<span data-ttu-id="f6503-109">기본적으로 매개 변수 없이 권한 부여 특성을 추가 하면 해당 컨트롤러 또는 동작에 대 한 인증 된 사용자에 대 한 액세스를 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-109">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="f6503-110">특정 사용자만 사용할 수 있는 API를 더욱 제한 하려면 필요한 역할 또는 사용자가 충족 해야 하는 정책을 지정 하는 특성을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-110">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="f6503-111">역할 기반 권한 부여를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-111">Implementing role-based authorization</span></span>

<span data-ttu-id="f6503-112">ASP.NET Core Id는 역할의 기본 개념을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-112">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="f6503-113">사용자 외에도 ASP.NET Core Id 응용 프로그램에서 사용 되는 다른 역할에 대 한 정보를 저장 하 고 있는 역할에 할당 되는 사용자의 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-113">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="f6503-114">RoleManager 종류 (입니다. 지속형된 저장소에는 역할 업데이트 포함)와 (있음 할당 하거나 할당 하 고 역할에서 사용자가 해제할 수) UserManager 형식이 이러한 할당을 프로그래밍 방식으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-114">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="f6503-115">JWT 전달자 토큰을 인증 하는 경우 ASP.NET Core JWT 전달자 인증 미들웨어는 토큰에 있는 역할 클레임에 따라 사용자의 역할을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-115">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="f6503-116">MVC 작업 또는 특정 역할의 사용자로 컨트롤러에 대 한 액세스를 제한 하려면 다음 예에서 같이 권한 부여 헤더에으로 역할 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-116">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

<span data-ttu-id="f6503-117">이 예에서 관리자 또는 PowerUser 역할의 사용자만 Api (예: SetTime 작업 실행 중) 제어판 컨트롤러에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-117">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="f6503-118">종료 API는 더 관리자 역할에 사용자 에게만 액세스를 허용 하도록 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-118">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="f6503-119">사용자는 여러 역할의 구성원을 요구 하려면 다음 예제와 같이 여러 권한 부여 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-119">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="f6503-120">이 예제에서는 API1를 호출 하는 사용자 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-120">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="f6503-121">관리자에 *또는* PowerUser 역할 *및*</span><span class="sxs-lookup"><span data-stu-id="f6503-121">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="f6503-122">RemoteEmployee 역할에 *및*</span><span class="sxs-lookup"><span data-stu-id="f6503-122">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="f6503-123">CustomPolicy 권한 부여에 대 한 사용자 지정 처리기를 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-123">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="f6503-124">정책 기반 권한 부여를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-124">Implementing policy-based authorization</span></span>

<span data-ttu-id="f6503-125">사용 하 여 사용자 지정 권한 부여 규칙을 작성할 수 또한 [권한 부여 정책](https://docs.asp.net/en/latest/security/authorization/policies.html)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-125">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="f6503-126">이 섹션의 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-126">In this section we provide an overview.</span></span> <span data-ttu-id="f6503-127">자세한 세부 정보는 온라인에서 사용할 수 있는 [ASP.NET 권한 부여 Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-127">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="f6503-128">사용자 지정 권한 부여 정책에서 서비스를 사용 하 여 Startup.ConfigureServices 메서드에 등록 됩니다. AddAuthorization 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-128">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="f6503-129">이 메서드는 AuthorizationOptions 인수를 구성 하는 대리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-129">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));
    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));
    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

<span data-ttu-id="f6503-130">예제에서와 같이 정책을 다양 한 유형의 요구 사항에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-130">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="f6503-131">정책을 등록 된 후은 적용할 수는 작업이 나 컨트롤러에 정책의 이름을 권한 부여 속성의 정책 인수로 전달 하 여 (예를 들어 \[Authorize(Policy="EmployeesOnly")\]) 정책이 있을 수 있습니다 뿐만 아니라 하나 이상의 (이러한 예와 같이) 여러 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-131">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="f6503-132">앞의 예에서 첫 번째 AddPolicy 호출은 역할에서 권한을 부여한는 대체 방법이입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-132">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="f6503-133">경우 \[Authorize(Policy="AdministratorsOnly")\] 만 관리자 역할의 사용자가 액세스할 수 있습니다는 API에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-133">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="f6503-134">두 번째 AddPolicy 호출 쉽게 특정 클레임 사용자를 위한 록 요구할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-134">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="f6503-135">RequireClaim 메서드는 또한 필요에 따라은 클레임에 대 한 예상 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-135">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="f6503-136">값이 지정 된 경우 사용자는 올바른 형식의 클레임와 모두 지정된 된 값 중 하나에 있는 경우에 요구 사항이 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-136">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="f6503-137">JWT 전달자 인증 미들웨어를 사용 하는 경우 모든 JWT 속성 사용자 클레임으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-137">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="f6503-138">여기에 표시 된 가장 흥미로운 정책이 사용자 지정 권한 부여 요구 사항을 사용 하기 때문에 세 번째 AddPolicy 메서드 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-138">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="f6503-139">사용자 지정 권한 부여 요구를 사용 하 여 다양 한 권한 부여를 수행 하는 방법을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-139">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="f6503-140">이렇게 하려면 이러한 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-140">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="f6503-141">IAuthorizationRequirement에서 파생 되 고 요구 사항 정보를 지정 하는 필드를 포함 하는 요구 사항 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-141">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="f6503-142">예제에서는 샘플 MinimumAgeRequirement 형식에 대 한 나이 필드는 이것이입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-142">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="f6503-143">AuthorizationHandler를 구현 하는 처리기&lt;T&gt;, 여기서 T는 IAuthorizationRequirement 처리기 충족 시킬 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-143">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="f6503-144">처리기는 지정 된 컨텍스트는 사용자에 대 한 정보를 포함 하는 요구 사항을 충족 하는지 확인 하는 HandleRequirementAsync 메서드를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-144">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="f6503-145">사용자 컨텍스트 호출 요구 사항을 충족 하는 경우 합니다. 성공 하는 사용자는 권한이 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-145">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="f6503-146">여러 가지 방법으로 사용자가 권한 부여 요구를 충족 않을 수 있습니다, 경우에 여러 처리기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-146">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="f6503-147">사용자 지정 정책 요구 사항을 AddPolicy 호출을 등록 하는 것 외에도 또한 해야 (서비스 종속성 주입을 통해 사용자 지정 요구 사항 처리기를 등록 하려면입니다. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span><span class="sxs-lookup"><span data-stu-id="f6503-147">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="f6503-148">사용자 지정 권한 부여 요구 사항 및 검사 (DateOfBirth 클레임에 기반)는 사용자의 나이 대 한 이벤트 처리기의 예로 ASP.NET Core에서 사용할 수 있는 [권한 부여 설명서](https://docs.asp.net/en/latest/security/authorization/policies.html)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6503-148">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f6503-149">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="f6503-149">Additional resources</span></span>

-   <span data-ttu-id="f6503-150">**ASP.NET Core 인증**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="f6503-150">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="f6503-151">**ASP.NET Core 권한 부여**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="f6503-151">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="f6503-152">**역할 기반 권한 부여**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="f6503-152">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="f6503-153">**사용자 지정 정책 기반 권한 부여**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="f6503-153">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="f6503-154">[이전] [다음] (개발자-응용 프로그램-암호-storage.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="f6503-154">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
