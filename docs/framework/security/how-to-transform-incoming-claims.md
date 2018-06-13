---
title: '방법: 들어오는 클레임 변환'
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: cb71e320116c3af73139f1a8083fa62e8a7e21a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400174"
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="5be2a-102">방법: 들어오는 클레임 변환</span><span class="sxs-lookup"><span data-stu-id="5be2a-102">How To: Transform Incoming Claims</span></span>
## <a name="applies-to"></a><span data-ttu-id="5be2a-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="5be2a-103">Applies To</span></span>  
  
-   <span data-ttu-id="5be2a-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="5be2a-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="5be2a-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="5be2a-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="5be2a-106">요약</span><span class="sxs-lookup"><span data-stu-id="5be2a-106">Summary</span></span>  
 <span data-ttu-id="5be2a-107">이 방법은 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들고 들어오는 클레임을 변환하기 위한 자세한 단계별 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="5be2a-108">또한, 응용 프로그램이 실행될 때 변환된 클레임이 제공되는지 확인하기 위해 응용 프로그램을 테스트하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="5be2a-109">목차</span><span class="sxs-lookup"><span data-stu-id="5be2a-109">Contents</span></span>  
  
-   <span data-ttu-id="5be2a-110">목표</span><span class="sxs-lookup"><span data-stu-id="5be2a-110">Objectives</span></span>  
  
-   <span data-ttu-id="5be2a-111">개요</span><span class="sxs-lookup"><span data-stu-id="5be2a-111">Overview</span></span>  
  
-   <span data-ttu-id="5be2a-112">단계 요약</span><span class="sxs-lookup"><span data-stu-id="5be2a-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5be2a-113">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5be2a-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="5be2a-114">2단계 – 사용자 지정 ClaimsAuthenticationManager를 사용하여 클레임 변환 구현</span><span class="sxs-lookup"><span data-stu-id="5be2a-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="5be2a-115">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5be2a-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="5be2a-116">목표</span><span class="sxs-lookup"><span data-stu-id="5be2a-116">Objectives</span></span>  
  
-   <span data-ttu-id="5be2a-117">클레임 기반 인증에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5be2a-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="5be2a-118">관리자 역할 클레임을 추가하여 들어오는 클레임 변환</span><span class="sxs-lookup"><span data-stu-id="5be2a-118">Transform incoming claims by adding an Administrator role claim</span></span>  
  
-   <span data-ttu-id="5be2a-119">ASP.NET Web Forms 응용 프로그램 테스트하여 제대로 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="5be2a-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="5be2a-120">개요</span><span class="sxs-lookup"><span data-stu-id="5be2a-120">Overview</span></span>  
 <span data-ttu-id="5be2a-121">WIF는 RP(신뢰 당사자) 응용 프로그램에 제공되기 전에 사용자가 클레임을 수정할 수 있는 <xref:System.Security.Claims.ClaimsAuthenticationManager>라는 클래스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="5be2a-122"><xref:System.Security.Claims.ClaimsAuthenticationManager>는 인증 및 기본 응용 프로그램 코드 간에 문제를 분리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="5be2a-123">아래 예제에서는 RP에 필요할 수 있는 들어오는 <xref:System.Security.Claims.ClaimsPrincipal>의 클레임에 역할을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="5be2a-124">단계 요약</span><span class="sxs-lookup"><span data-stu-id="5be2a-124">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5be2a-125">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5be2a-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="5be2a-126">2단계 – 사용자 지정 ClaimsAuthenticationManager를 사용하여 클레임 변환 구현</span><span class="sxs-lookup"><span data-stu-id="5be2a-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="5be2a-127">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5be2a-127">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="5be2a-128">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5be2a-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="5be2a-129">이 단계에서는 새로운 ASP.NET Web Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="5be2a-130">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5be2a-130">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="5be2a-131">관리자로 승격된 모드에서 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-131">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="5be2a-132">Visual Studio에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="5be2a-133">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
4.  <span data-ttu-id="5be2a-134">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="5be2a-135">**솔루션 탐색기**에서 **TestApp** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **ID 및 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="5be2a-136">**ID 및 액세스** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="5be2a-137">**공급자**에서 **로컬 개발 STS로 응용 프로그램 테스트**를 선택한 다음 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
7.  <span data-ttu-id="5be2a-138">*Default.aspx* 파일에서 기존 태그를 다음 태그로 바꾸고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
8.  <span data-ttu-id="5be2a-139">*Default.aspx.cs*라는 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="5be2a-140">기존 코드를 다음으로 바꾸고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-140">Replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="5be2a-141">2단계 – 사용자 지정 ClaimsAuthenticationManager를 사용하여 클레임 변환 구현</span><span class="sxs-lookup"><span data-stu-id="5be2a-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
 <span data-ttu-id="5be2a-142">이 단계에서는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스에서 기본 기능을 재정의하여 들어오는 주체에 관리자 역할을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="5be2a-143">사용자 지정 ClaimsAuthenticationManager를 사용하여 클레임 변환을 구현하려면</span><span class="sxs-lookup"><span data-stu-id="5be2a-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>  
  
1.  <span data-ttu-id="5be2a-144">Visual Studio에서 솔루션을 마우스 오른쪽 단추로 클릭하고, **추가**를 클릭한 다음, **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="5be2a-145">**새 프로젝트 추가** 창의 **Visual C#** 템플릿 목록에서 **클래스 라이브러리**를 선택하고, `ClaimsTransformation`을 입력한 다음, **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="5be2a-146">새 프로젝트가 솔루션 폴더에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-146">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="5be2a-147">**ClaimsTransformation** 프로젝트에서 **참조**를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="5be2a-148">**참조 관리자** 창에서 **System.IdentityModel**을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5be2a-149">**Class1.cs**를 열거나 이 파일이 없는 경우 **ClaimsTransformation**을 마우스 오른쪽 단추로 클릭하고 **추가**, **클래스…** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>  
  
6.  <span data-ttu-id="5be2a-150">지시문을 사용하여 다음을 코드 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-150">Add the following using directives to the code file:</span></span>  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  <span data-ttu-id="5be2a-151">다음 클래스 및 메서드를 코드 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-151">Add the following class and method in the code file.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="5be2a-152">다음 코드는 데모용으로만 제공됩니다. 프로덕션 코드에서 필요한 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="5be2a-153">파일을 저장하고 **ClaimsTransformation** 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-153">Save the file and build the **ClaimsTransformation** project.</span></span>  
  
9. <span data-ttu-id="5be2a-154">**TestApp** ASP.NET 프로젝트에서 참조를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>  
  
10. <span data-ttu-id="5be2a-155">**참조 관리자** 창의 왼쪽 메뉴에서 **솔루션**을 선택하고, 채워진 옵션에서 **ClaimsTransformation**을 선택하고 나서, **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="5be2a-156">루트 **Web.config** 파일에서 **\<system.identityModel>** 항목으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="5be2a-157">**\<identityConfiguration>** 요소 내에 다음 줄을 추가하고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="5be2a-158">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5be2a-158">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="5be2a-159">이 단계에서는 ASP.NET Web Forms 응용 프로그램을 테스트하고 사용자가 Forms 인증으로 로그인할 때 클레임이 제공되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="5be2a-160">Forms 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="5be2a-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="5be2a-161">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="5be2a-162">*Default.aspx*가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-162">You should be presented with *Default.aspx*.</span></span>  
  
2.  <span data-ttu-id="5be2a-163">*Default.aspx* 페이지에서 계정에 대한 **Issuer**, **OriginalIssuer**, **Type**, **Value** 및 **ValueType** 클레임 정보를 포함하는 표가 **클레임** 제목 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="5be2a-164">마지막 행은 다음 방식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be2a-164">The last row should be presented in the following way:</span></span>  
  
    ||||||  
    |-|-|-|-|-|  
    |<span data-ttu-id="5be2a-165">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="5be2a-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="5be2a-166">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="5be2a-166">LOCAL AUTHORITY</span></span>|http://schemas.microsoft.com/ws/2008/06/identity/claims/role|<span data-ttu-id="5be2a-167">관리</span><span class="sxs-lookup"><span data-stu-id="5be2a-167">Admin</span></span>|http://www.w3.org/2001/XMLSchema#string|
