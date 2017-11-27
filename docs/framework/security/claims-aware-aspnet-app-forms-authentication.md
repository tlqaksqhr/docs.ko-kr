---
title: "방법: 양식 기반 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 987157bc3663330d9c610c1016787890e9dc6137
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="5c53f-102">방법: 양식 기반 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="5c53f-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="5c53f-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="5c53f-103">Applies To</span></span>  
  
-   <span data-ttu-id="5c53f-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="5c53f-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="5c53f-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="5c53f-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="5c53f-106">요약</span><span class="sxs-lookup"><span data-stu-id="5c53f-106">Summary</span></span>  
 <span data-ttu-id="5c53f-107">이 방법은 Forms 인증을 사용하는 간단한 클레임 인식 ASP.NET Web Forms 응용 프로그램을 만들기 위한 자세한 단계별 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="5c53f-108">또한 응용 프로그램을 테스트하여 사용자가 Forms 인증으로 로그인할 때 클레임이 제공되는지 확인하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="5c53f-109">목차</span><span class="sxs-lookup"><span data-stu-id="5c53f-109">Contents</span></span>  
  
-   <span data-ttu-id="5c53f-110">목표</span><span class="sxs-lookup"><span data-stu-id="5c53f-110">Objectives</span></span>  
  
-   <span data-ttu-id="5c53f-111">개요</span><span class="sxs-lookup"><span data-stu-id="5c53f-111">Overview</span></span>  
  
-   <span data-ttu-id="5c53f-112">단계 요약</span><span class="sxs-lookup"><span data-stu-id="5c53f-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5c53f-113">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5c53f-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="5c53f-114">2단계 – Forms 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5c53f-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="5c53f-115">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5c53f-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="5c53f-116">목표</span><span class="sxs-lookup"><span data-stu-id="5c53f-116">Objectives</span></span>  
  
-   <span data-ttu-id="5c53f-117">Forms 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5c53f-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
-   <span data-ttu-id="5c53f-118">ASP.NET Web Forms 응용 프로그램 테스트하여 제대로 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="5c53f-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="5c53f-119">개요</span><span class="sxs-lookup"><span data-stu-id="5c53f-119">Overview</span></span>  
 <span data-ttu-id="5c53f-120">.NET 4.5에서 WIF 및 해당 클레임 기반 권한 부여는 프레임워크의 필수적인 부분으로 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="5c53f-121">이전에는 ASP.NET 사용자의 클레임을 원할 경우 WIF를 설치하고 나서 인터페이스를 주체 개체(예: `Thread.CurrentPrincipal` 또는 `HttpContext.Current.User`)로 캐스팅해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="5c53f-122">이제 클레임은 이러한 주체 개체를 통해 자동으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="5c53f-123">Forms로 인증된 모든 사용자는 클레임이 자동으로 연결되므로 .NET 4.5에 포함된 WIF를 Forms 인증에 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="5c53f-124">이 방법에서 설명하는 것처럼 Forms 인증을 사용하는 ASP.NET 응용 프로그램에서 즉시 이러한 클레임을 사용하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="5c53f-125">단계 요약</span><span class="sxs-lookup"><span data-stu-id="5c53f-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5c53f-126">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5c53f-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="5c53f-127">2단계 – Forms 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5c53f-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="5c53f-128">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5c53f-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="5c53f-129">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5c53f-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="5c53f-130">이 단계에서는 새로운 ASP.NET Web Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="5c53f-131">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c53f-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="5c53f-132">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="5c53f-133">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="5c53f-134">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="5c53f-135">2단계 – Forms 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5c53f-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
 <span data-ttu-id="5c53f-136">이 단계에서는 *Web.config* 구성 파일에 구성 항목을 추가하고 *Default.aspx* 파일을 편집하여 계정에 대한 클레임 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="5c53f-137">Forms 인증을 사용하여 클레임에 대한 ASP.NET 응용 프로그램을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="5c53f-137">To configure ASP.NET application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="5c53f-138">*Default.aspx* 파일에서 기존 태그를 다음과 같이 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
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
  
     <span data-ttu-id="5c53f-139">이 단계에서는 Forms 인증에서 검색된 클레임으로 채워질 *Default.aspx* 페이지에 GridView 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>  
  
2.  <span data-ttu-id="5c53f-140">*Default.aspx* 파일을 저장하고 나서 *Default.aspx.cs*라는 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="5c53f-141">기존 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-141">Replace the existing code with the following:</span></span>  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="5c53f-142">위의 코드는 Forms 인증으로 식별된 사용자를 포함하여 인증된 사용자에 대한 클레임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="5c53f-143">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="5c53f-143">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="5c53f-144">이 단계에서는 ASP.NET Web Forms 응용 프로그램을 테스트하고 사용자가 Forms 인증으로 로그인할 때 클레임이 제공되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="5c53f-145">Forms 인증을 사용하여 클레임에 대한 ASP.NET Web Forms 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="5c53f-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="5c53f-146">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="5c53f-147">페이지의 오른쪽 위에 **등록** 및 **로그인** 링크가 있는 *Default.aspx*가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="5c53f-148">**등록**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-148">Click **Register**.</span></span>  
  
2.  <span data-ttu-id="5c53f-149">**등록** 페이지에서 사용자 계정을 만든 다음 **등록**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="5c53f-150">Forms 인증을 사용하여 계정이 만들어지며, 자동으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>  
  
3.  <span data-ttu-id="5c53f-151">홈페이지로 리디렉션된 후 계정에 대한 **Issuer**, **OriginalIssuer**, **Type**, **Value** 및 **ValueType** 클레임 정보를 포함하는 표가 **클레임** 제목 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c53f-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>
