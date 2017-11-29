---
title: "방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d5b81e20ed1b39c7750329718729905484eb7fa1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="11462-102">방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="11462-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="11462-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="11462-103">Applies To</span></span>  
  
-   <span data-ttu-id="11462-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="11462-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="11462-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="11462-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="11462-106">요약</span><span class="sxs-lookup"><span data-stu-id="11462-106">Summary</span></span>  
 <span data-ttu-id="11462-107">이 방법은 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들기 위한 자세한 단계별 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="11462-108">또한 페더레이션 인증을 성공적으로 구현하기 위해 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 테스트하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="11462-109">이 방법에 STS(보안 토큰 서비스)를 만들기 위한 자세한 지침은 없으며, STS를 이미 구성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="11462-110">목차</span><span class="sxs-lookup"><span data-stu-id="11462-110">Contents</span></span>  
  
-   <span data-ttu-id="11462-111">목표</span><span class="sxs-lookup"><span data-stu-id="11462-111">Objectives</span></span>  
  
-   <span data-ttu-id="11462-112">단계 요약</span><span class="sxs-lookup"><span data-stu-id="11462-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="11462-113">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="11462-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="11462-114">2단계 – 클레임 기반 인증에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="11462-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="11462-115">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="11462-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="11462-116">목표</span><span class="sxs-lookup"><span data-stu-id="11462-116">Objectives</span></span>  
  
-   <span data-ttu-id="11462-117">클레임 기반 인증에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="11462-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="11462-118">성공적인 클레임 인식 ASP.NET Web Forms 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="11462-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="11462-119">단계 요약</span><span class="sxs-lookup"><span data-stu-id="11462-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="11462-120">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="11462-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="11462-121">2단계 - 페더레이션 인증에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="11462-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
-   <span data-ttu-id="11462-122">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="11462-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="11462-123">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="11462-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="11462-124">이 단계에서는 새로운 ASP.NET Web Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11462-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="11462-125">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="11462-125">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="11462-126">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="11462-127">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="11462-128">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="11462-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="11462-129">2단계 – 클레임 기반 인증에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="11462-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="11462-130">이 단계에서는 ASP.NET Web Forms 응용 프로그램의 *Web.config* 구성 파일에 구성 항목을 추가하여 클레임을 인식하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="11462-131">클레임 기반 인증에 대한 ASP.NET 응용 프로그램을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="11462-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="11462-132">*Web.config* 구성 파일의 **\<configuration>** 여는 요소 바로 뒤에 다음 구성 섹션 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="11462-133">응용 프로그램의 페더레이션 메타데이터에 액세스할 수 있는 **\<location>** 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="11462-134">**\<system.web>** 요소 내에 다음 구성 항목을 추가하여 사용자를 거부하고, 기본 인증을 사용하지 않도록 설정하고, WIF로 인증을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="11462-135">페더레이션 인증에 대한 모듈을 정의하는 **\<system.webServer>** 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="11462-136">*PublicKeyToken* 특성은 이전에 추가된 **\<configSections>** 항목에 대한 *PublicKeyToken* 특성과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  <span data-ttu-id="11462-137">다음 Windows Identity Foundation 관련 구성 항목을 추가하고 ASP.NET 응용 프로그램의 URL 및 포트 번호가 **\<audienceUris>** 항목, **\<wsFederation>** 요소의 **realm** 특성 및 **\<wsFederation>** 요소의 **reply** 특성 값과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="11462-138">또한 **issuer** 값이 STS(보안 토큰 서비스) URL과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
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
  
6.  <span data-ttu-id="11462-139"><xref:System.IdentityModel> 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7.  <span data-ttu-id="11462-140">솔루션을 컴파일하여 오류가 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="11462-141">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="11462-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="11462-142">이 단계에서는 클레임 기반 인증에 대해 구성된 ASP.NET Web Forms 응용 프로그램을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="11462-143">기본 테스트를 수행하려면 STS(보안 토큰 서비스)에서 발급된 토큰에 클레임을 표시하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="11462-144">클레임 기반 인증에 대한 ASP.NET Web Forms 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="11462-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="11462-145">**TestApp** 프로젝트 아래에서 **Default.aspx** 파일을 열고 기존 태그를 다음 태그로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="11462-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  <span data-ttu-id="11462-146">**Default.aspx**를 저장하고 나서 **Default.aspx.cs**라는 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11462-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11462-147">**Default.aspx.cs**는 솔루션 탐색기에서 **Default.aspx** 아래에 숨겨질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11462-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="11462-148">**Default.aspx.cs**가 표시되지 않으면 옆에 있는 삼각형을 클릭하여 **Default.aspx**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3.  <span data-ttu-id="11462-149">**Default.aspx.cs**의 **Page_Load** 메서드에 있는 기존 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="11462-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="11462-150">**Default.aspx.cs**를 저장하고 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5.  <span data-ttu-id="11462-151">**F5** 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-151">Run the solution by pressing the **F5** key.</span></span>  
  
6.  <span data-ttu-id="11462-152">STS(보안 토큰 서비스)에서 발급된 토큰에 클레임을 표시하는 페이지가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11462-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>
