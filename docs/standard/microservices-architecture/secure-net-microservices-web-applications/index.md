---
title: .NET 마이크로 서비스 및 웹 응용 프로그램 보안
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | .NET 마이크로 서비스 및 웹 응용 프로그램 보안
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: c2c7d692517c6a46225542936e05656db915bf0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="securing-net-microservices-and-web-applications"></a><span data-ttu-id="e9298-103">.NET 마이크로 서비스 및 웹 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="e9298-103">Securing .NET Microservices and Web Applications</span></span>

<span data-ttu-id="e9298-104">서비스에 의해 노출된 리소스 및 API는 종종 특정 신뢰할 수 있는 사용자 또는 클라이언트로 제한되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-104">It is often necessary for resources and APIs exposed by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="e9298-105">이러한 API 수준 신뢰 결정을 만드는 첫 번째 단계는 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-105">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="e9298-106">인증은 사용자의 ID를 안정적으로 확인하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-106">Authentication is the process of reliably ascertaining a user’s identity.</span></span>

<span data-ttu-id="e9298-107">마이크로 서비스 시나리오에서 일반적으로 인증은 중앙에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-107">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="e9298-108">API 게이트웨이를 사용하는 경우 그림 11-1에 표시된 것처럼 게이트웨이는 인증에 적합한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-108">If you are using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 11-1.</span></span> <span data-ttu-id="e9298-109">이 방법을 사용하는 경우 메시지를 인증하는 데 추가 보안을 사용하지 않는 한 (API 게이트웨이 없이) 개별 마이크로 서비스에 직접 연결할 수 없습니다. 인증하는 메시지의 출처는 반드시 게이트웨이가 아니어도 무방합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-109">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![](./media/image1.png)

<span data-ttu-id="e9298-110">**그림 11-1**.</span><span class="sxs-lookup"><span data-stu-id="e9298-110">**Figure 11-1**.</span></span> <span data-ttu-id="e9298-111">API 게이트웨이를 통한 중앙 집중식 인증</span><span class="sxs-lookup"><span data-stu-id="e9298-111">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="e9298-112">서비스에 직접 액세스할 수 있는 경우 Azure Active Directory 또는 STS(보안 토큰 서비스)로 작동하는 전용 인증 마이크로 서비스와 같은 인증 서비스를 사용하여 사용자를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-112">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="e9298-113">신뢰 결정은 보안 토큰 또는 쿠키를 통해 서비스 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-113">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="e9298-114">(필요한 경우 [데이터 보호 서비스](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)를 통해 ASP.NET에서 응용 프로그램 간에 공유할 수 있습니다.) 그림 11-2에서는 이 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-114">(These can be shared between applications, if needed, in ASP.NET Core with [data protection services](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 11-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="e9298-115">**그림 11-2**.</span><span class="sxs-lookup"><span data-stu-id="e9298-115">**Figure 11-2**.</span></span> <span data-ttu-id="e9298-116">ID 마이크로 서비스에 의한 인증. 인증 토큰을 사용하여 신뢰가 공유됨</span><span class="sxs-lookup"><span data-stu-id="e9298-116">Authentication by identity microservice; trust is shared using an authorization token</span></span>

## <a name="authenticating-using-aspnet-core-identity"></a><span data-ttu-id="e9298-117">ASP.NET Core ID를 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="e9298-117">Authenticating using ASP.NET Core Identity</span></span>

<span data-ttu-id="e9298-118">응용 프로그램의 사용자를 식별하기 위한 ASP.NET Core의 기본 메커니즘은 [ASP.NET Core ID](https://docs.microsoft.com/aspnet/core/security/authentication/identity) 멤버 자격 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-118">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="e9298-119">ASP.NET ID는 사용자 정보(로그인 정보, 역할 및 클레임 포함)를 개발자가 구성한 데이터 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-119">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="e9298-120">일반적으로 ASP.NET Core ID 데이터 저장소는 Microsoft.AspNetCore.Identity.EntityFrameworkCore 패키지에서 제공된 Entity Framework 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-120">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the Microsoft.AspNetCore.Identity.EntityFrameworkCore package.</span></span> <span data-ttu-id="e9298-121">그러나 사용자 지정 저장소 또는 타사 패키지를 사용하여 Azure Table Storage, DocumentDB 또는 다른 위치에 ID 정보를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-121">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, DocumentDB, or other locations.</span></span>

<span data-ttu-id="e9298-122">다음은 선택된 개별 사용자 계정 인증을 사용하여 ASP.NET Core 웹 응용 프로그램 프로젝트 템플릿에서 가져온 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-122">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="e9298-123">Startup.ConfigureServices 메서드에서 EntityFramework.Core를 사용하여 ASP.NET Core ID를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-123">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="e9298-124">ASP.NET Core ID가 구성되면 서비스의 Startup.Configure 메서드에서 app.UseIdentity를 호출하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-124">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s Startup.Configure method.</span></span>

<span data-ttu-id="e9298-125">ASP.NET 코드 ID를 통해 다음과 같은 몇 가지 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-125">Using ASP.NET Code Identity enables several scenarios:</span></span>

-   <span data-ttu-id="e9298-126">UserManager 형식(userManager.CreateAsync)을 사용하여 새 사용자 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-126">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

-   <span data-ttu-id="e9298-127">SignInManager 형식을 사용하여 사용자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-127">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="e9298-128">signInManager.SignInAsync를 사용하여 직접 로그인하거나 signInManager.PasswordSignInAsync를 사용하여 사용자 암호가 올바른지 확인한 다음 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-128">You can use signInManager.SignInAsync to sign in directly, or signInManager.PasswordSignInAsync to confirm the user’s password is correct and then sign them in.</span></span>

-   <span data-ttu-id="e9298-129">브라우저의 후속 요청에 로그인한 사용자의 ID와 클레임이 포함되도록 (ASP.NET Core ID 미들웨어에서 읽는) 쿠키에 저장된 정보를 기반으로 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-129">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="e9298-130">ASP.NET Core ID도 [2단계 인증](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-130">ASP.NET Core Identity also supports [two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="e9298-131">ASP.NET Core ID는 로컬 사용자 데이터 저장소를 사용하며 (MVC 웹 응용 프로그램에서는 전형적인 방식인) 쿠키를 사용하여 요청 사이의 ID를 유지하는 인증 시나리오를 위해 권장되는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-131">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

## <a name="authenticating-using-external-providers"></a><span data-ttu-id="e9298-132">외부 공급자를 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="e9298-132">Authenticating using external providers</span></span>

<span data-ttu-id="e9298-133">ASP.NET Core는 [외부 인증 공급자](https://docs.microsoft.com/aspnet/core/security/authentication/social/)를 사용하여 사용자가 [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) 흐름을 통해 로그인할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-133">ASP.NET Core also supports using [external authentication providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) to let users log in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="e9298-134">즉, 사용자가 Microsoft, Google, Facebook 또는 Twitter와 같은 공급자의 기존 인증 프로세스를 사용하여 로그인하고 응용 프로그램에서 ASP.NET Core ID와 공급자 ID를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-134">This means that users can log in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="e9298-135">외부 인증을 사용하려면 응용 프로그램의 HTTP 요청 처리 파이프라인에서 적절한 인증 미들웨어를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-135">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="e9298-136">이 미들웨어는 인증 공급자의 URI 경로 반환 요청 처리, ID 정보 캡처, SignInManager.GetExternalLoginInfo 메서드를 통해 사용 가능하도록 설정하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-136">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="e9298-137">인기 있는 외부 인증 공급자 및 해당 공급자와 연결된 NuGet 패키지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-137">Popular external authentication providers and their associated NuGet packages are shown below.</span></span>

<span data-ttu-id="e9298-138">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span><span class="sxs-lookup"><span data-stu-id="e9298-138">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span></span>

<span data-ttu-id="e9298-139">**Google:** Microsoft.AspNetCore.Authentication.Google</span><span class="sxs-lookup"><span data-stu-id="e9298-139">**Google:** Microsoft.AspNetCore.Authentication.Google</span></span>

<span data-ttu-id="e9298-140">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span><span class="sxs-lookup"><span data-stu-id="e9298-140">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span></span>

<span data-ttu-id="e9298-141">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span><span class="sxs-lookup"><span data-stu-id="e9298-141">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span></span>

<span data-ttu-id="e9298-142">모든 경우에 미들웨어는 호출을 통해 Startup.Configure의 app.Use{ExternalProvider}Authentication과 유사한 등록 메서드에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-142">In all cases, the middleware is registered with a call to a registration method similar to app.Use{ExternalProvider}Authentication in Startup.Configure.</span></span> <span data-ttu-id="e9298-143">이러한 등록 메서드에서는 공급자의 필요에 따라 응용 프로그램 ID 및 비밀 정보(예: 암호)가 포함된 옵션 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-143">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="e9298-144">외부 인증 공급자는 사용자 ID에 액세스하는 데 필요한 응용 프로그램을 사용자에게 안내하기 위해 ([ASP.NET Core 설명서](https://docs.microsoft.com/aspnet/core/security/authentication/social/)에서 설명한 것처럼) 등록할 응용 프로그램을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-144">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="e9298-145">미들웨어가 Startup.Configure에 등록되면 모든 컨트롤러 작업에서 사용자에게 로그인을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-145">Once the middleware is registered in Startup.Configure, you can prompt users to log in from any controller action.</span></span> <span data-ttu-id="e9298-146">이 작업을 수행하려면 인증 공급자의 이름 및 리디렉션 URL을 포함하는 AuthenticationProperties 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-146">To do this, you create an AuthenticationProperties object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="e9298-147">그런 다음 AuthenticationProperties 개체를 전달하는 챌린지 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-147">You then return a Challenge response that passes the AuthenticationProperties object.</span></span> <span data-ttu-id="e9298-148">다음 코드에서는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-148">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="e9298-149">redirectUrl 매개 변수는 사용자가 인증되면 외부 공급자가 리디렉션해야 하는 URL을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-149">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="e9298-150">URL은 다음 단순화된 예제와 같이 외부 ID 정보를 기반으로 사용자가 로그인하는 작업을 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-150">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="e9298-151">Visual Studio에서 ASP.NET Core 웹 응용 프로그램 프로젝트를 만들 때 **개별 사용자 계정** 인증 옵션을 선택한 경우 그림 11-3에 표시된 것처럼 외부 공급자를 통해 로그인하는 데 필요한 모든 코드는 이미 프로젝트에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-151">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 11-3.</span></span>

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

<span data-ttu-id="e9298-152">**그림 11-3**.</span><span class="sxs-lookup"><span data-stu-id="e9298-152">**Figure 11-3**.</span></span> <span data-ttu-id="e9298-153">웹 응용 프로그램 프로젝트를 만들 경우 외부 인증 사용 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="e9298-153">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="e9298-154">이전에 나열된 외부 인증 공급자뿐만 아니라 더욱 많은 외부 인증 공급자 사용에 대한 미들웨어를 제공하는 타사 패키지도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-154">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="e9298-155">자세한 목록은 GitHub에서 [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) 리포지토리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e9298-155">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="e9298-156">물론 고유한 외부 인증 미들웨어를 만드는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-156">It is also possible, of course, to create your own external authentication middleware.</span></span>

## <a name="authenticating-with-bearer-tokens"></a><span data-ttu-id="e9298-157">전달자 토큰을 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="e9298-157">Authenticating with bearer tokens</span></span>

<span data-ttu-id="e9298-158">ASP.NET Core ID(또는 ID 및 외부 인증 공급자)를 사용한 인증은 사용자 정보를 쿠키에 저장하는 것이 적합한 다수의 웹 응용 프로그램 시나리오에 대해 효과적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-158">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="e9298-159">그러나 다른 시나리오의 경우 쿠키는 데이터를 유지하고 전송하는 자연스러운 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-159">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="e9298-160">예를 들어 SPA(단일 페이지 응용 프로그램), 네이티브 클라이언트 또는 다른 웹 API에서 액세스할 수 있는 RESTful 끝점을 노출하는 ASP.NET Core 웹 API에서는 쿠키 대신 일반적으로 전달자 토큰 인증을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-160">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="e9298-161">이러한 유형의 응용 프로그램은 쿠키와는 작동하지 않지만 간편하게 전달자 토큰을 검색하여 후속 요청의 인증 헤더에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-161">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="e9298-162">토큰 인증을 사용하기 위해 ASP.NET Core는 [OAuth 2.0](https://oauth.net/2/) 및 [OpenID Connect](https://openid.net/connect/) 사용에 대한 몇 가지 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-162">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="e9298-163">OpenID Connect 또는 OAuth 2.0 ID 공급자를 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="e9298-163">Authenticating with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="e9298-164">사용자 정보가 Azure Active Directory 또는 OpenID Connect 또는 OAuth 2.0을 지원하는 다른 ID 솔루션에 저장되는 경우 Microsoft.AspNetCore.Authentication.OpenIdConnect 패키지를 사용하여 OpenID Connect 워크플로를 통해 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-164">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the Microsoft.AspNetCore.Authentication.OpenIdConnect package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="e9298-165">예를 들어 [Azure Active Directory에 대해 인증](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)하기 위해 ASP.NET Core 웹 응용 프로그램에서는 다음 예제에 표시된 것처럼 해당 패키지의 미들웨어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-165">For example, to [authenticate against Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), an ASP.NET Core web application can use middleware from that package as shown in the following example:</span></span>

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

<span data-ttu-id="e9298-166">구성 값은 응용 프로그램이 [Azure AD 클라이언트로 등록](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad)될 때 생성되는 Azure Active Directory 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-166">The configuration values are Azure Active Directory values that are created when your application is [registered as an Azure AD client](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span></span> <span data-ttu-id="e9298-167">Azure Active Directory를 통해 인증된 사용자를 모두 인증해야 하는 경우 응용 프로그램에서 여러 마이크로 서비스 간에 단일 클라이언트 ID를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-167">A single client ID can be shared among multiple microservices in an application if they all need to authenticate users authenticated via Azure Active Directory.</span></span>

<span data-ttu-id="e9298-168">이 워크플로를 사용하면 모든 사용자 정보 저장소 및 인증이 Azure Active Directory에서 처리되므로 ASP.NET Core ID 미들웨어가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-168">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by Azure Active Directory.</span></span>

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="e9298-169">ASP.NET Core 서비스에서 보안 토큰 발급</span><span class="sxs-lookup"><span data-stu-id="e9298-169">Issuing security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="e9298-170">로컬 ASP.NET Core ID 사용자를 위해 외부 ID 공급자를 사용하는 대신 보안 토큰 발급을 선호하는 경우 일부 훌륭한 타사 라이브러리를 적절하게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-170">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="e9298-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) 및 [OpenIddict](https://github.com/openiddict/openiddict-core)는 ASP.NET Core ID와 쉽게 통합하여 ASP.NET Core 서비스에서 보안 토큰을 발급할 수 있도록 허용하는 OpenID Connect 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="e9298-172">[IdentityServer4 설명서](https://identityserver4.readthedocs.io/en/release/)에는 라이브러리 사용에 대한 자세한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-172">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/release/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="e9298-173">그러나 IdentityServer4를 사용하여 토큰을 발급하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-173">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1.  <span data-ttu-id="e9298-174">Startup.Configure 메서드에서 app.UseIdentityServer를 호출하여 IdentityServer4를 응용 프로그램의 HTTP 요청 처리 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-174">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="e9298-175">이렇게 하면 라이브러리 서버에서 /connect/token과 같은 OpenID Connect 및 OAuth2 끝점에 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-175">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2.  <span data-ttu-id="e9298-176">services.AddIdentityServer를 호출하여 Startup.ConfigureServices에서 IdentityServer4를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-176">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3.  <span data-ttu-id="e9298-177">다음 데이터를 제공하여 ID 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-177">You configure identity server by providing the following data:</span></span>

-   <span data-ttu-id="e9298-178">서명에 사용할 [자격 증명](https://identityserver4.readthedocs.io/en/release/topics/crypto.html)</span><span class="sxs-lookup"><span data-stu-id="e9298-178">The [credentials](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) to use for signing.</span></span>

-   <span data-ttu-id="e9298-179">액세스를 위해 사용자가 요청할 수 있는 [ID 및 API 리소스](https://identityserver4.readthedocs.io/en/release/topics/resources.html)</span><span class="sxs-lookup"><span data-stu-id="e9298-179">The [Identity and API resources](https://identityserver4.readthedocs.io/en/release/topics/resources.html) that users might request access to:</span></span>

<!-- -->

-   <span data-ttu-id="e9298-180">API 리소스는 사용자가 액세스 토큰을 사용하여 액세스할 수 있는 보호된 데이터 또는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-180">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="e9298-181">웹 API 리소스의 예로는 권한 부여가 필요한 웹 API(또는 API 집합)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-181">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

-   <span data-ttu-id="e9298-182">ID 리소스는 사용자를 식별하기 위해 클라이언트에게 제공되는 정보(클레임)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-182">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="e9298-183">클레임에는 사용자 이름, 전자 메일 주소 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-183">The claims might include the user name, email address, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="e9298-184">토큰을 요청하기 위해 [클라이언트](https://identityserver4.readthedocs.io/en/release/topics/clients.html)가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-184">The [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) that will be connecting in order to request tokens.</span></span>

-   <span data-ttu-id="e9298-185">[ASP.NET Core ID](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) 또는 대체 요소와 같은 사용자 정보에 대한 저장소 메커니즘</span><span class="sxs-lookup"><span data-stu-id="e9298-185">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) or an alternative.</span></span>

<span data-ttu-id="e9298-186">IdentityServer4에 대해 사용하려는 클라이언트와 리소스를 지정할 때 적절한 형식의 IEnumerable&lt;T&gt; 컬렉션을 메모리 내 클라이언트 또는 리소스 저장소를 사용하는 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-186">When you specify clients and resources for IdentityServer4 to use, you can pass an IEnumerable&lt;T&gt; collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="e9298-187">또는 더 복잡한 시나리오의 경우 종속성 주입을 통해 클라이언트 또는 리소스 공급자 형식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-187">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="e9298-188">사용자 지정 IClientStore 형식에서 제공한 메모리 내 리소스 및 클라이언트를 사용하는 IdentityServer4를 위한 샘플 구성은 다음 예제처럼 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-188">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a><span data-ttu-id="e9298-189">보안 토큰 사용</span><span class="sxs-lookup"><span data-stu-id="e9298-189">Consuming security tokens</span></span>

<span data-ttu-id="e9298-190">OpenID Connect 끝점에 대해 인증하거나 고유 보안 토큰을 발행하는 방법은 일부 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-190">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="e9298-191">그러나 다른 서비스에서 제공받은 유효한 보안 토큰이 있는 사용자의 액세스를 제한해야 하는 서비스에는 어떤 방법을 사용해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="e9298-191">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="e9298-192">이 시나리오의 경우 JWT 토큰을 처리하는 인증 미들웨어를 Microsoft.AspNetCore.Authentication.JwtBearer 패키지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-192">For that scenario, authentication middleware that handles JWT tokens is available in the Microsoft.AspNetCore.Authentication.JwtBearer package.</span></span> <span data-ttu-id="e9298-193">JWT는 “[JSON Web Token](https://tools.ietf.org/html/rfc7519)”을 의미하며 보안 클레임 통신을 위한 일반적인 보안 토큰 형식(RFC 7519에 의해 정의됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-193">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="e9298-194">미들웨어를 사용하여 이러한 토큰을 사용하는 방법의 간단한 예는 다음 예제처럼 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-194">A simple example of how to use middleware to consume such tokens might look like the following example.</span></span> <span data-ttu-id="e9298-195">이 코드는 ASP.NET Core MVC 미들웨어(app.UseMvc)에 대한 호출 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-195">This code must precede calls to ASP.NET Core MVC middleware (app.UseMvc).</span></span>

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

<span data-ttu-id="e9298-196">이 사용에 대한 매개 변수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-196">The parameters in this usage are:</span></span>

-   <span data-ttu-id="e9298-197">대상 그룹은 들어오는 토큰의 수신기 또는 토큰에서 액세스 권한을 부여받는 리소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-197">Audience represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="e9298-198">이 매개 변수에서 지정한 값이 토큰의 aud 매개 변수와 일치하지 않는 경우 토큰이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-198">If the value specified in this parameter does not match the aud parameter in the token, the token will be rejected.</span></span>

-   <span data-ttu-id="e9298-199">인증 기관은 토큰 발행 인증 서버의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-199">Authority is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="e9298-200">JWT 전달자 인증 미들웨어는 이 URI를 사용하여 토큰 시그니처의 유효성을 검사하는 데 사용되는 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-200">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="e9298-201">또한 미들웨어는 토큰의 iss 매개 변수가 이 URI와 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-201">The middleware also confirms that the iss parameter in the token matches this URI.</span></span>

-   <span data-ttu-id="e9298-202">AutomaticAuthenticate는 토큰에 의해 정의된 사용자가 자동으로 로그인해야 하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-202">AutomaticAuthenticate is a Boolean value that indicates whether the user defined by the token should be automatically signed in.</span></span>

<span data-ttu-id="e9298-203">이 예에서는 다른 매개 변수인 RequireHttpsMetadata가 사용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-203">Another parameter, RequireHttpsMetadata, is not used in this example.</span></span> <span data-ttu-id="e9298-204">이 매개 변수는 테스트 목적으로 사용하는 것이 적합합니다. 이 매개 변수를 false로 설정하여 인증서가 없는 환경에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-204">It is useful for testing purposes; you set this parameter to false so that you can test in environments where you do not have certificates.</span></span> <span data-ttu-id="e9298-205">실제 배포에서 JWT 전달자 토큰은 항상 HTTPS를 통해서만 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-205">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="e9298-206">미들웨어가 준비되면 JWT 토큰은 인증 헤더에서 자동으로 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-206">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="e9298-207">그런 다음, 토큰은 deserialize되고 (대상 그룹 및 인증 기관 매개 변수를 사용하여) 유효성 검사가 진행되며 나중에 MVC 작업 또는 인증 필터에서 참조하는 사용자 정보로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-207">They are then deserialized, validated (using the values in the Audience and Authority parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="e9298-208">JWT 전달자 인증 미들웨어는 인증 기관을 사용할 수 없는 경우 로컬 인증서를 사용하여 토큰의 유효성을 검사하는 상황과 같은 고급 시나리오도 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-208">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="e9298-209">이 시나리오에 대해서는 JwtBearerOptions 개체에서 TokenValidationParameters 개체를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9298-209">For this scenario, you can specify a TokenValidationParameters object in the JwtBearerOptions object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9298-210">추가 자료</span><span class="sxs-lookup"><span data-stu-id="e9298-210">Additional resources</span></span>

-   <span data-ttu-id="e9298-211">**응용 프로그램 간 쿠키 공유하기**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span><span class="sxs-lookup"><span data-stu-id="e9298-211">**Sharing cookies between applications**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span></span>

-   <span data-ttu-id="e9298-212">**ID 소개**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="e9298-212">**Introduction to Identity**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="e9298-213">**Rick Anderson. SMS를 사용한 2단계 인증**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span><span class="sxs-lookup"><span data-stu-id="e9298-213">**Rick Anderson. Two-factor authentication with SMS**
[*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span></span>

-   <span data-ttu-id="e9298-214">**Facebook, Google 및 기타 외부 공급자를 통해 인증 사용**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span><span class="sxs-lookup"><span data-stu-id="e9298-214">**Enabling authentication using Facebook, Google and other external providers**
[*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span></span>

-   <span data-ttu-id="e9298-215">**Michell Anicas. OAuth 2 소개**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span><span class="sxs-lookup"><span data-stu-id="e9298-215">**Michell Anicas. An Introduction to OAuth 2**
[*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span></span>

-   <span data-ttu-id="e9298-216">**AspNet.Security.OAuth.Providers**(ASP.NET OAuth 공급자를 위한 GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="e9298-216">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span>
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   <span data-ttu-id="e9298-217">**Danny Strockis. ASP.NET Core 웹앱에 Azure AD 통합**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span><span class="sxs-lookup"><span data-stu-id="e9298-217">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app**
[*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span></span>

-   <span data-ttu-id="e9298-218">**IdentityServer4. 공식 문서**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span><span class="sxs-lookup"><span data-stu-id="e9298-218">**IdentityServer4. Official documentation**
[*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e9298-219">[이전] (../implement-resilient-applications/monitor-app-health.md) [다음] (authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e9298-219">[Previous] (../implement-resilient-applications/monitor-app-health.md) [Next] (authorization-net-microservices-web-applications.md)</span></span>
