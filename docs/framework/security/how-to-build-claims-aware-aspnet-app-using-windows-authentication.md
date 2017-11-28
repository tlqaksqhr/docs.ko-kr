---
title: "방법: Windows 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 676a03678cbdf6fe08e628806df2a1853fb71718
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a><span data-ttu-id="369ca-102">방법: Windows 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="369ca-102">How To: Build Claims-Aware ASP.NET Application Using Windows Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="369ca-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="369ca-103">Applies To</span></span>  
  
-   <span data-ttu-id="369ca-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="369ca-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="369ca-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="369ca-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="369ca-106">요약</span><span class="sxs-lookup"><span data-stu-id="369ca-106">Summary</span></span>  
 <span data-ttu-id="369ca-107">이 방법은 Windows 인증을 사용하는 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들기 위한 자세한 단계별 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Windows authentication.</span></span> <span data-ttu-id="369ca-108">또한 응용 프로그램을 테스트하여 사용자가 Windows 인증으로 로그인할 때 클레임이 제공되는지 확인하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in using Windows authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="369ca-109">목차</span><span class="sxs-lookup"><span data-stu-id="369ca-109">Contents</span></span>  
  
-   <span data-ttu-id="369ca-110">목표</span><span class="sxs-lookup"><span data-stu-id="369ca-110">Objectives</span></span>  
  
-   <span data-ttu-id="369ca-111">개요</span><span class="sxs-lookup"><span data-stu-id="369ca-111">Overview</span></span>  
  
-   <span data-ttu-id="369ca-112">단계 요약</span><span class="sxs-lookup"><span data-stu-id="369ca-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="369ca-113">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="369ca-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="369ca-114">2단계 – Windows 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="369ca-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="369ca-115">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="369ca-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="369ca-116">목표</span><span class="sxs-lookup"><span data-stu-id="369ca-116">Objectives</span></span>  
  
-   <span data-ttu-id="369ca-117">Windows 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="369ca-117">Configure an ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
-   <span data-ttu-id="369ca-118">ASP.NET Web Forms 응용 프로그램 테스트하여 제대로 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="369ca-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="369ca-119">개요</span><span class="sxs-lookup"><span data-stu-id="369ca-119">Overview</span></span>  
 <span data-ttu-id="369ca-120">.NET 4.5에서 WIF 및 해당 클레임 기반 권한 부여는 프레임워크의 필수적인 부분으로 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="369ca-121">이전에는 ASP.NET 사용자의 클레임을 원할 경우 WIF를 설치하고 나서 인터페이스를 주체 개체(예: `Thread.CurrentPrincipal` 또는 `HttpContext.Current.User`)로 캐스팅해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="369ca-122">이제 클레임은 이러한 주체 개체를 통해 자동으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="369ca-123">Windows 자격 증명으로 인증된 모든 사용자에게 연결된 클레임이 자동으로 포함되므로 .NET 4.5에 포함된 WIF를 Windows 인증에 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-123">Windows authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Windows credentials automatically have claims associated with them.</span></span> <span data-ttu-id="369ca-124">이 방법에서 설명하는 것처럼 Windows 인증을 사용하는 ASP.NET 응용 프로그램에서 즉시 이러한 클레임을 사용하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-124">You can begin using these claims immediately in an ASP.NET application that uses Windows authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="369ca-125">단계 요약</span><span class="sxs-lookup"><span data-stu-id="369ca-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="369ca-126">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="369ca-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="369ca-127">2단계 – Windows 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="369ca-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="369ca-128">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="369ca-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="369ca-129">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="369ca-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="369ca-130">이 단계에서는 새로운 ASP.NET Web Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="369ca-131">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="369ca-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="369ca-132">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-132">Start Visual Studio, then click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="369ca-133">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="369ca-134">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="369ca-135">**TestApp** 프로젝트가 만들어진 후 **솔루션 탐색기**에서 해당 프로젝트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-135">After the **TestApp** project has been created, click on it in **Solution Explorer**.</span></span> <span data-ttu-id="369ca-136">프로젝트의 속성이 **솔루션 탐색기** 아래 **속성** 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-136">The project’s properties will appear in the **Properties** pane below **Solution Explorer**.</span></span> <span data-ttu-id="369ca-137">**Windows 인증** 속성을 **사용**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-137">Set the **Windows Authentication** property to **Enabled**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="369ca-138">Windows 인증은 새 ASP.NET 응용 프로그램에서 기본적으로 사용되지 않으므로 수동으로 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-138">Windows authentication is disabled by default in new ASP.NET applications, so you must manually enable it.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="369ca-139">2단계 – Windows 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="369ca-139">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
 <span data-ttu-id="369ca-140">이 단계에서는 *Web.config* 구성 파일에 구성 항목을 추가하고 *Default.aspx* 파일을 수정하여 계정에 대한 클레임 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-140">In this step you will add a configuration entry to the *Web.config* configuration file and modify the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a><span data-ttu-id="369ca-141">Windows 인증을 사용하여 클레임에 대한 ASP.NET 응용 프로그램을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="369ca-141">To configure ASP.NET application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="369ca-142">**TestApp** 프로젝트의 *Default.aspx* 파일에서 기존 태그를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-142">In the **TestApp** project’s *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
     <span data-ttu-id="369ca-143">이 단계에서는 Windows 인증에서 검색된 클레임으로 채워질 *Default.aspx* 페이지에 GridView 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-143">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Windows authentication.</span></span>  
  
2.  <span data-ttu-id="369ca-144">*Default.aspx* 파일을 저장하고 나서 *Default.aspx.cs*라는 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-144">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="369ca-145">기존 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-145">Replace the existing code with the following:</span></span>  
  
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
  
     <span data-ttu-id="369ca-146">위 코드는 인증된 사용자에 대한 클레임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-146">The above code will display claims about an authenticated user.</span></span>  
  
3.  <span data-ttu-id="369ca-147">응용 프로그램의 인증 형식을 변경하려면 다음 구성 항목만 포함하도록 프로젝트의 루트 *Web.config* 파일에서 **\<system.web>** 섹션의 **\<authentication>** 블록을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-147">To change the application’s authentication type, modify the **\<authentication>** block in the **\<system.web>** section of the project’s root *Web.config* file so that it only includes the following configuration entry:</span></span>  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  <span data-ttu-id="369ca-148">마지막으로 동일한 *Web.config* 파일에서 **\<system.web>** 섹션의 **\<authorization>** 블록을 수정하여 인증을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-148">Finally, modify the **\<authorization>** block in the **\<system.web>** section of the same *Web.config* file to force authentication:</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="369ca-149">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="369ca-149">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="369ca-150">이 단계에서는 ASP.NET Web Forms 응용 프로그램을 테스트하고 사용자가 Windows 인증으로 로그인할 때 클레임이 제공되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-150">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Windows authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="369ca-151">Windows 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="369ca-151">To test your ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="369ca-152">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-152">Press **F5** to build and run the application.</span></span> <span data-ttu-id="369ca-153">*Default.aspx*가 있어야 하고 Windows 계정 이름(도메인 이름)이 페이지의 오른쪽 위에 인증된 사용자로 표시되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-153">You should be presented with *Default.aspx*, and your Windows account name (including domain name) should already appear as the authenticated user in the top right of the page.</span></span> <span data-ttu-id="369ca-154">페이지의 콘텐츠에 Windows 계정에서 검색된 클레임으로 채워진 표가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="369ca-154">The page’s content should include a table filled with claims retrieved from your Windows account.</span></span>
