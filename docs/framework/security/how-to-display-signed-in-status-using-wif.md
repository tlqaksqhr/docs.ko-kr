---
title: "방법: WIF를 사용하여 로그인 상태 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f6951eb6c9df7a3fef09f5972f3cb5fcabe5496f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-signed-in-status-using-wif"></a><span data-ttu-id="9bec0-102">방법: WIF를 사용하여 로그인 상태 표시</span><span class="sxs-lookup"><span data-stu-id="9bec0-102">How To: Display Signed In Status Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="9bec0-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="9bec0-103">Applies To</span></span>  
  
-   <span data-ttu-id="9bec0-104">Microsoft® Windows® Identity Foundation(WIF) 4.5</span><span class="sxs-lookup"><span data-stu-id="9bec0-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span></span>  
  
-   <span data-ttu-id="9bec0-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="9bec0-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="9bec0-106">요약</span><span class="sxs-lookup"><span data-stu-id="9bec0-106">Summary</span></span>  
 <span data-ttu-id="9bec0-107">이 항목에서는 WIF 사용 가능 ASP.NET 응용 프로그램에서 로그인 상태를 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-107">This topic describes how to display the sign in status in a WIF-enabled ASP.NET application.</span></span> <span data-ttu-id="9bec0-108">WIF는 응용 프로그램이 클레임을 인식하도록 설정하고 응용 프로그램 리소스에 대한 인증 및 권한 부여를 관리하기 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-108">WIF provides the mechanism for making your application claims-aware, and managing authentication and authorization for application resources.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="9bec0-109">목차</span><span class="sxs-lookup"><span data-stu-id="9bec0-109">Contents</span></span>  
  
-   <span data-ttu-id="9bec0-110">개요</span><span class="sxs-lookup"><span data-stu-id="9bec0-110">Overview</span></span>  
  
-   <span data-ttu-id="9bec0-111">단계 요약</span><span class="sxs-lookup"><span data-stu-id="9bec0-111">Summary of Steps</span></span>  
  
-   <span data-ttu-id="9bec0-112">1단계 – ID 및 액세스 도구 확장 설치</span><span class="sxs-lookup"><span data-stu-id="9bec0-112">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="9bec0-113">2단계 – 신뢰 당사자 ASP.NET 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9bec0-113">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="9bec0-114">3단계 – 로컬 개발 STS를 사용하여 사용자 인증</span><span class="sxs-lookup"><span data-stu-id="9bec0-114">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="9bec0-115">4단계 – ASP.NET 응용 프로그램을 수정하여 로그인 상태 표시</span><span class="sxs-lookup"><span data-stu-id="9bec0-115">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="9bec0-116">5단계 – WIF 및 ASP.NET 응용 프로그램 간 통합 테스트</span><span class="sxs-lookup"><span data-stu-id="9bec0-116">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="overview"></a><span data-ttu-id="9bec0-117">개요</span><span class="sxs-lookup"><span data-stu-id="9bec0-117">Overview</span></span>  
 <span data-ttu-id="9bec0-118">이 항목에서는 WIF를 사용하여 간단한 클레임 인식 응용 프로그램을 만드는 방법 및 사용자가 로그인되어 있는지 여부를 쉽게 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-118">This topic demonstrates how to create a simple claims-aware application using WIF and how to easily display whether a user is signed in or not.</span></span> <span data-ttu-id="9bec0-119">다음 단계에서는 ID 및 액세스 Visual Studio 확장과 함께 제공되는 로컬 개발 STS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-119">The following steps use the Local Development STS that is included with the Identity and Access Visual Studio Extension.</span></span> <span data-ttu-id="9bec0-120">로컬 개발 STS는 클레임을 응용 프로그램에 통합하는 간단한 메서드를 제공하기 위해 테스트 및 개발 환경에서 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-120">The Local Development STS is intended for a testing and development environment to provide a simple method of integrating claims into your application.</span></span> <span data-ttu-id="9bec0-121">실제 인증을 수행하지 않고 자격 증명이 필요하지 않으므로 프로덕션 환경에서 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-121">It should never be used in a production environment, as it does not perform real authentication and credentials are not required.</span></span> <span data-ttu-id="9bec0-122">그러나 실제 인증을 사용하는 프로덕션 준비 응용 프로그램의 경우 다음 단계의 명령형 코드가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-122">However, the imperative code in the following steps is the same for a production-ready application using real authentication.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="9bec0-123">단계 요약</span><span class="sxs-lookup"><span data-stu-id="9bec0-123">Summary of Steps</span></span>  
  
-   <span data-ttu-id="9bec0-124">1단계 – ID 및 액세스 도구 확장 설치</span><span class="sxs-lookup"><span data-stu-id="9bec0-124">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="9bec0-125">2단계 – 신뢰 당사자 ASP.NET 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9bec0-125">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="9bec0-126">3단계 – 로컬 개발 STS를 사용하여 사용자 인증</span><span class="sxs-lookup"><span data-stu-id="9bec0-126">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="9bec0-127">4단계 – ASP.NET 응용 프로그램을 수정하여 로그인 상태 표시</span><span class="sxs-lookup"><span data-stu-id="9bec0-127">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="9bec0-128">5단계 – WIF 및 ASP.NET 응용 프로그램 간 통합 테스트</span><span class="sxs-lookup"><span data-stu-id="9bec0-128">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="step-1--install-the-identity-and-access-extension"></a><span data-ttu-id="9bec0-129">1단계 – ID 및 액세스 도구 확장 설치</span><span class="sxs-lookup"><span data-stu-id="9bec0-129">Step 1 – Install the Identity and Access Extension</span></span>  
 <span data-ttu-id="9bec0-130">이 단계에서는 Visual Studio 2012에 대한 ID 및 액세스 확장을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-130">This step describes how to configure the Identity and Access extension to Visual Studio 2012.</span></span> <span data-ttu-id="9bec0-131">이 확장은 STS 끝점과 통신하도록 응용 프로그램을 구성하는 프로세스를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-131">This extension automates the process of configuring your application to communicate with STS endpoints.</span></span>  
  
#### <a name="to-install-the-identity-and-access-extension"></a><span data-ttu-id="9bec0-132">ID 및 액세스 확장을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="9bec0-132">To install the Identity and Access extension</span></span>  
  
1.  <span data-ttu-id="9bec0-133">관리자로 승격된 모드에서 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-133">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="9bec0-134">Visual Studio에서 **도구**, **확장 관리자**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-134">In Visual Studio, click **Tools** and click **Extension Manager**.</span></span> <span data-ttu-id="9bec0-135">**확장 관리자** 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-135">The **Extension Manager** window appears.</span></span>  
  
3.  <span data-ttu-id="9bec0-136">**확장 관리자**의 왼쪽 메뉴에서 **온라인 확장**을 클릭하고 **Visual Studio 갤러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-136">In **Extension Manager**, click **Online Extensions** from the left menu, then select **Visual Studio Gallery**.</span></span>  
  
4.  <span data-ttu-id="9bec0-137">**확장 관리자**의 오른쪽 위에서 *ID 및 액세스*를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-137">In the top right corner of **Extension Manager**, search for *Identity and Access*.</span></span>  
  
5.  <span data-ttu-id="9bec0-138">**ID 및 액세스** 항목이 검색 결과에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-138">The **Identity and Access** item will appear in the search results.</span></span> <span data-ttu-id="9bec0-139">해당 항목을 클릭하고 **다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-139">Click it, and then click **Download**.</span></span>  
  
6.  <span data-ttu-id="9bec0-140">**다운로드 및 설치** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-140">The **Download and Install** dialog appears.</span></span> <span data-ttu-id="9bec0-141">사용 약관에 동의하면 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-141">If you agree with the license terms, click **Install**.</span></span>  
  
7.  <span data-ttu-id="9bec0-142">**ID 및 액세스** 확장이 설치를 완료하면 관리자 모드에서 Visual Studio를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-142">When the **Identity and Access** extension has finished installing, restart Visual Studio in administrator mode.</span></span>  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a><span data-ttu-id="9bec0-143">2단계 – 신뢰 당사자 ASP.NET 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9bec0-143">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
 <span data-ttu-id="9bec0-144">이 단계에서는 WIF와 통합될 신뢰 당사자 ASP.NET Web Forms 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-144">This step describes how to create a relying party ASP.NET Web Forms application that will integrate with WIF.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="9bec0-145">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9bec0-145">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="9bec0-146">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-146">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="9bec0-147">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-147">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="9bec0-148">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-148">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a><span data-ttu-id="9bec0-149">3단계 – 로컬 개발 STS를 사용하여 사용자 인증</span><span class="sxs-lookup"><span data-stu-id="9bec0-149">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
 <span data-ttu-id="9bec0-150">이 단계에서는 응용 프로그램에서 로컬 개발 STS를 사용하도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-150">This step describes how to enable Local Development STS in your application.</span></span> <span data-ttu-id="9bec0-151">로컬 개발 STS는 Visual Studio용 ID 및 액세스 확장을 통해 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-151">Local Development STS is enabled by using the Identity and Access extension for Visual Studio.</span></span>  
  
#### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a><span data-ttu-id="9bec0-152">ASP.NET 응용 프로그램에서 로컬 개발 STS를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9bec0-152">To enable Local Development STS in your ASP.NET application</span></span>  
  
1.  <span data-ttu-id="9bec0-153">Visual Studio의 **솔루션 탐색기**에서 **TestApp** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **ID 및 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-153">In Visual Studio, right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
2.  <span data-ttu-id="9bec0-154">**ID 및 액세스** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-154">The **Identity and Access** window appears.</span></span> <span data-ttu-id="9bec0-155">**공급자**에서 **로컬 개발 STS로 응용 프로그램 테스트**를 선택한 다음 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-155">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a><span data-ttu-id="9bec0-156">4단계 – ASP.NET 응용 프로그램을 수정하여 로그인 상태 표시</span><span class="sxs-lookup"><span data-stu-id="9bec0-156">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
 <span data-ttu-id="9bec0-157">이 단계에서는 ASP.NET 응용 프로그램을 수정하여 현재 사용자가 로그인되어 있는지 여부를 동적으로 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-157">This step describes how to modify your ASP.NET application to dynamically display whether the current user is signed in.</span></span> <span data-ttu-id="9bec0-158">STS 공급자가 구성되면 WIF가 들어오는 클레임을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-158">Once your STS provider has been configured, WIF handles the incoming claims.</span></span> <span data-ttu-id="9bec0-159">이제 인증 결과를 표시하도록 응용 프로그램 코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-159">Now you need to configure your application’s code to display the result of the authentication.</span></span>  
  
#### <a name="to-display-sign-in-status"></a><span data-ttu-id="9bec0-160">로그인 상태를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="9bec0-160">To display sign in status</span></span>  
  
1.  <span data-ttu-id="9bec0-161">Visual Studio의 **TestApp** 프로젝트에서 **Default.aspx** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-161">In Visual Studio, open the **Default.aspx** file under the **TestApp** project.</span></span>  
  
2.  <span data-ttu-id="9bec0-162">**Default.aspx** 파일의 기존 태그를 다음 태그로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-162">Replace the existing markup in the **Default.aspx** file with the following markup:</span></span>  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  <span data-ttu-id="9bec0-163">**Default.aspx**를 저장하고 나서 **Default.aspx.cs**라는 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-163">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bec0-164">**Default.aspx.cs**는 솔루션 탐색기에서 **Default.aspx** 아래에 숨겨질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-164">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="9bec0-165">**Default.aspx.cs**가 표시되지 않으면 옆에 있는 삼각형을 클릭하여 **Default.aspx**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-165">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
4.  <span data-ttu-id="9bec0-166">**Default.aspx.cs**의 기존 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-166">Replace the existing code in **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="9bec0-167">**Default.aspx.cs**를 저장하고 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-167">Save **Default.aspx.cs**, and build the application.</span></span>  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a><span data-ttu-id="9bec0-168">5단계 – WIF 및 ASP.NET 응용 프로그램 간 통합 테스트</span><span class="sxs-lookup"><span data-stu-id="9bec0-168">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
 <span data-ttu-id="9bec0-169">이 단계에서는 WIF 및 ASP.NET 응용 프로그램 간 통합을 테스트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-169">This step describes how you can test the integration between WIF and your ASP.NET application.</span></span>  
  
#### <a name="to-test-the-integration-between-wif-and-aspnet"></a><span data-ttu-id="9bec0-170">WIF 및 ASP.NET 응용 프로그램 간 통합을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="9bec0-170">To test the integration between WIF and ASP.NET</span></span>  
  
1.  <span data-ttu-id="9bec0-171">Visual Studio에서 **F5** 키를 눌러 응용 프로그램 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-171">In Visual Studio, press **F5** to start debugging your application.</span></span> <span data-ttu-id="9bec0-172">오류가 발견되지 않으면 새 브라우저 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-172">If no errors are found, a new browser window will open.</span></span>  
  
2.  <span data-ttu-id="9bec0-173">브라우저가 요청을 STS로 자동으로 리디렉션하고 나서 Default.aspx 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9bec0-173">You may notice that the browser silently redirects your request to the STS, and then opens the Default.aspx page.</span></span> <span data-ttu-id="9bec0-174">WIF가 제대로 구성되면 사이트에 다음 텍스트가 표시되어야 합니다. **“로그인했습니다.”**</span><span class="sxs-lookup"><span data-stu-id="9bec0-174">If WIF is properly configured, you should see the site display the following text: **"You are signed in"**.</span></span>
