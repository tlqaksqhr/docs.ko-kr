---
title: '방법: WIF를 사용하여 클레임 인식 ASP.NET MVC 웹 응용 프로그램 빌드'
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 146724f31e1d09f09f94d102366539dc79ddfe02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399151"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a><span data-ttu-id="1a4a1-102">방법: WIF를 사용하여 클레임 인식 ASP.NET MVC 웹 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="1a4a1-102">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="1a4a1-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1a4a1-103">Applies To</span></span>  
  
-   <span data-ttu-id="1a4a1-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="1a4a1-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="1a4a1-105">ASP.NET® MVC</span><span class="sxs-lookup"><span data-stu-id="1a4a1-105">ASP.NET® MVC</span></span>  
  
## <a name="summary"></a><span data-ttu-id="1a4a1-106">요약</span><span class="sxs-lookup"><span data-stu-id="1a4a1-106">Summary</span></span>  
 <span data-ttu-id="1a4a1-107">이 방법은 간단한 클레임 인식 ASP.NET MVC 웹 응용 프로그램을 만들기 위한 자세한 단계별 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET MVC web application.</span></span> <span data-ttu-id="1a4a1-108">또한 클레임 기반 인증을 성공적으로 구현하기 위해 간단한 클레임 인식 ASP.NET MVC 웹 응용 프로그램을 테스트하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-108">It also provides instructions how to test the simple claims-aware ASP.NET MVC web application for successful implementation of claims-based authentication.</span></span> <span data-ttu-id="1a4a1-109">이 방법에 STS(보안 토큰 서비스)를 만들기 위한 자세한 지침은 없으며, STS를 이미 구성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="1a4a1-110">목차</span><span class="sxs-lookup"><span data-stu-id="1a4a1-110">Contents</span></span>  
  
-   <span data-ttu-id="1a4a1-111">목표</span><span class="sxs-lookup"><span data-stu-id="1a4a1-111">Objectives</span></span>  
  
-   <span data-ttu-id="1a4a1-112">단계 요약</span><span class="sxs-lookup"><span data-stu-id="1a4a1-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="1a4a1-113">1단계 – 간단한 ASP.NET MVC 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="1a4a1-113">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="1a4a1-114">2단계 – 클레임 기반 인증에 대한 ASP.NET MVC 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="1a4a1-114">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="1a4a1-115">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="1a4a1-115">Step 3 – Test Your Solution</span></span>  
  
-   <span data-ttu-id="1a4a1-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1a4a1-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="1a4a1-117">목표</span><span class="sxs-lookup"><span data-stu-id="1a4a1-117">Objectives</span></span>  
  
-   <span data-ttu-id="1a4a1-118">클레임 기반 인증에 대한 ASP.NET MVC 웹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="1a4a1-118">Configure ASP.NET MVC web application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="1a4a1-119">성공적인 클레임 인식 ASP.NET MVC 웹 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="1a4a1-119">Test successful claims-aware ASP.NET MVC web application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="1a4a1-120">단계 요약</span><span class="sxs-lookup"><span data-stu-id="1a4a1-120">Summary of Steps</span></span>  
  
-   <span data-ttu-id="1a4a1-121">1단계 – 간단한 ASP.NET MVC 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="1a4a1-121">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="1a4a1-122">2단계 – 클레임 기반 인증에 대한 ASP.NET MVC 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="1a4a1-122">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="1a4a1-123">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="1a4a1-123">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a><span data-ttu-id="1a4a1-124">1단계 – 간단한 ASP.NET MVC 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="1a4a1-124">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
 <span data-ttu-id="1a4a1-125">이 단계에서는 새로운 ASP.NET MVC 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-125">In this step, you will create a new ASP.NET MVC application.</span></span>  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a><span data-ttu-id="1a4a1-126">간단한 ASP.NET MVC 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1a4a1-126">To create simple ASP.NET MVC application</span></span>  
  
1.  <span data-ttu-id="1a4a1-127">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-127">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="1a4a1-128">**새 프로젝트** 창에서 **ASP.NET MVC 3 웹 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-128">In the **New Project** window, click **ASP.NET MVC 3 Web Application**.</span></span>  
  
3.  <span data-ttu-id="1a4a1-129">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-129">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="1a4a1-130">**새 ASP.NET MVC 3 프로젝트** 대화 상자에서 사용 가능한 템플릿 중에 **인터넷 응용 프로그램**을 선택하고, **뷰 엔진**이 **Razor**로 설정되어 있는지 확인하고 나서, **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-130">In the **New ASP.NET MVC 3 Project** dialog, select **Internet Application** from the available templates, ensure **View Engine** is set to **Razor**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="1a4a1-131">새 프로젝트가 열리면 **솔루션 탐색기**에서 **TestApp**을 마우스 오른쪽 단추로 클릭하고 **속성** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-131">When the new project opens, right-click the **TestApp** project in **Solution Explorer** and select the **Properties** option.</span></span>  
  
6.  <span data-ttu-id="1a4a1-132">프로젝트 속성 페이지에서 왼쪽에 있는 **웹** 탭을 클릭하고 **로컬 IIS 웹 서버 사용** 옵션이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-132">On the project’s properties page, click on the **Web** tab on the left and ensure that the **Use Local IIS Web Server** option is selected.</span></span>  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="1a4a1-133">2단계 – 클레임 기반 인증에 대한 ASP.NET MVC 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="1a4a1-133">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="1a4a1-134">이 단계에서는 ASP.NET MVC 웹 응용 프로그램의 *Web.config* 구성 파일에 구성 항목을 추가하여 클레임을 인식하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-134">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET MVC web application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="1a4a1-135">클레임 기반 인증에 대한 ASP.NET MVC 응용 프로그램을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="1a4a1-135">To configure ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="1a4a1-136">*Web.config* 구성 파일에 다음 구성 섹션 정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-136">Add the following configuration section definitions to the *Web.config* configuration file.</span></span> <span data-ttu-id="1a4a1-137">이를 통해 Windows Identity Foundation에 필요한 구성 섹션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-137">These define configuration sections required by Windows Identity Foundation.</span></span> <span data-ttu-id="1a4a1-138">**\<configuration>** 여는 요소 바로 뒤에 정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-138">Add the definitions immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="1a4a1-139">응용 프로그램의 페더레이션 메타데이터에 액세스할 수 있는 **\<location>** 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-139">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="1a4a1-140">**\<system.web>** 요소 내에 다음 구성 항목을 추가하여 사용자를 거부하고, 기본 인증을 사용하지 않도록 설정하고, WIF로 인증을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-140">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="1a4a1-141">다음 Windows Identity Foundation 관련 구성 항목을 추가하고 ASP.NET 응용 프로그램의 URL 및 포트 번호가 **\<audienceUris>** 항목, **\<wsFederation>** 요소의 **realm** 특성 및 **\<wsFederation>** 요소의 **reply** 특성 값과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-141">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="1a4a1-142">또한 **issuer** 값이 STS(보안 토큰 서비스) URL과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-142">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
5.  <span data-ttu-id="1a4a1-143"><xref:System.IdentityModel> 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-143">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
6.  <span data-ttu-id="1a4a1-144">솔루션을 컴파일하여 오류가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-144">Compile the solution to make sure there are errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="1a4a1-145">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="1a4a1-145">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="1a4a1-146">이 단계에서는 클레임 기반 인증에 대해 구성된 ASP.NET MVC 웹 응용 프로그램을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-146">In this step you will test your ASP.NET MVC web application configured for claims-based authentication.</span></span> <span data-ttu-id="1a4a1-147">기본 테스트를 수행하려면 STS(보안 토큰 서비스)에서 발급된 토큰에 클레임을 표시하는 간단한 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-147">To perform basic test you will add simple code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="1a4a1-148">클레임 기반 인증에 대한 ASP.NET MVC 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="1a4a1-148">To test your ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="1a4a1-149">**솔루션 탐색기**에서 **컨트롤러** 폴더를 확장하고 편집기에서 *HomeController.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-149">In the **Solution Explorer**, expand the **Controllers** folder and open *HomeController.cs* file in the editor.</span></span> <span data-ttu-id="1a4a1-150">**Index** 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-150">Add the following code to the **Index** method:</span></span>  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  <span data-ttu-id="1a4a1-151">**솔루션 탐색기**에서 **뷰**, **홈** 폴더를 차례로 확장하고, 편집기에서 *Index.cshtml* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-151">In the **Solution Explorer** expand **Views** and then **Home** folders and open *Index.cshtml* file in the editor.</span></span> <span data-ttu-id="1a4a1-152">콘텐츠를 삭제하고 다음 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-152">Delete its contents and add the following markup:</span></span>  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3.  <span data-ttu-id="1a4a1-153">**F5** 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-153">Run the solution by pressing the **F5** key.</span></span>  
  
4.  <span data-ttu-id="1a4a1-154">STS(보안 토큰 서비스)에서 발급된 토큰에 클레임을 표시하는 페이지가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4a1-154">You should be presented with the page that displays the claims in the token that was issued to you by Security Token Service.</span></span>  
  
## <a name="related-items"></a><span data-ttu-id="1a4a1-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1a4a1-155">Related Items</span></span>  
  
-   [<span data-ttu-id="1a4a1-156">방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="1a4a1-156">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
