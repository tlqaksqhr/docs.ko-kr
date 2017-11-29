---
title: "방법: 토큰 재생을 검색하도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: cde32407f072f3d29af4a8d1aae559e46057ae3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-token-replay-detection"></a><span data-ttu-id="8cd6f-102">방법: 토큰 재생을 검색하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8cd6f-102">How To: Enable Token Replay Detection</span></span>
## <a name="applies-to"></a><span data-ttu-id="8cd6f-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8cd6f-103">Applies To</span></span>  
  
-   <span data-ttu-id="8cd6f-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="8cd6f-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="8cd6f-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="8cd6f-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="8cd6f-106">요약</span><span class="sxs-lookup"><span data-stu-id="8cd6f-106">Summary</span></span>  
 <span data-ttu-id="8cd6f-107">이 방법은 WIF를 사용하는 ASP.NET 응용 프로그램에서 토큰 재생 검색을 사용하도록 설정하기 위한 자세한 단계별 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-107">This How-To provides detailed step-by-step procedures for enabling token replay detection in an ASP.NET application that uses WIF.</span></span> <span data-ttu-id="8cd6f-108">또한 토큰 재생 검색이 사용되는지 확인하기 위해 응용 프로그램을 테스트하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-108">It also provides instructions for how to test the application to verify that token replay detection is enabled.</span></span> <span data-ttu-id="8cd6f-109">이 방법 설명에 보안 토큰 서비스(STS)를 만들기 위한 자세한 지침은 없으며, 그 대신 ID 및 액세스 도구와 함께 제공되는 개발 STS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="8cd6f-110">개발 STS가 실제 인증을 수행하는 것은 아니며, 테스트 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="8cd6f-111">이 방법을 완료하려면 ID 및 액세스 도구를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="8cd6f-112">[ID 및 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-112">It can be downloaded from the following location: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="8cd6f-113">목차</span><span class="sxs-lookup"><span data-stu-id="8cd6f-113">Contents</span></span>  
  
-   <span data-ttu-id="8cd6f-114">목표</span><span class="sxs-lookup"><span data-stu-id="8cd6f-114">Objectives</span></span>  
  
-   <span data-ttu-id="8cd6f-115">개요</span><span class="sxs-lookup"><span data-stu-id="8cd6f-115">Overview</span></span>  
  
-   <span data-ttu-id="8cd6f-116">단계 요약</span><span class="sxs-lookup"><span data-stu-id="8cd6f-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="8cd6f-117">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기 및 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8cd6f-117">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="8cd6f-118">2단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="8cd6f-118">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="8cd6f-119">목표</span><span class="sxs-lookup"><span data-stu-id="8cd6f-119">Objectives</span></span>  
  
-   <span data-ttu-id="8cd6f-120">ID 및 액세스 도구에서 WIF 및 개발 STS를 사용하는 간단한 ASP.NET 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="8cd6f-120">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="8cd6f-121">토큰 재생 검색 사용 및 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="8cd6f-121">Enable token replay detection and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="8cd6f-122">개요</span><span class="sxs-lookup"><span data-stu-id="8cd6f-122">Overview</span></span>  
 <span data-ttu-id="8cd6f-123">클라이언트에서 이미 사용한 STS 토큰을 사용하여 신뢰 당사자에 대해 인증을 시도할 경우 재생 공격이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-123">A replay attack occurs when a client attempts to authenticate to a relying party with an STS token that the client has already used.</span></span> <span data-ttu-id="8cd6f-124">이 공격을 방지하기 위해 WIF에는 이전에 사용된 STS 토큰의 재생 검색 캐시가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-124">To help prevent this attack, WIF contains a replay detection cache of previously used STS tokens.</span></span> <span data-ttu-id="8cd6f-125">사용하도록 설정된 재생 검색은 들어오는 요청의 토큰을 확인하고 토큰이 이전에 사용되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-125">When enabled, replay detection checks the token of the incoming request and verifies whether or not the token has been previously used.</span></span> <span data-ttu-id="8cd6f-126">토큰이 이미 사용된 경우 요청이 거부되고 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-126">If the token has been used already, the request is refused and a <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> exception is thrown.</span></span>  
  
 <span data-ttu-id="8cd6f-127">다음 단계에서는 재생 검색을 사용하는 데 필요한 구성 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-127">The following steps demonstrate the configuration changes required to enable replay detection.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="8cd6f-128">단계 요약</span><span class="sxs-lookup"><span data-stu-id="8cd6f-128">Summary of Steps</span></span>  
  
-   <span data-ttu-id="8cd6f-129">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기 및 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8cd6f-129">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="8cd6f-130">2단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="8cd6f-130">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a><span data-ttu-id="8cd6f-131">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기 및 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8cd6f-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
 <span data-ttu-id="8cd6f-132">이 단계에서는 새 ASP.NET Web Forms 응용 프로그램을 만들고 *Web.config* 파일을 수정하여 재생 검색을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-132">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable replay detection.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="8cd6f-133">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="8cd6f-133">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="8cd6f-134">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-134">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="8cd6f-135">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-135">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="8cd6f-136">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-136">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="8cd6f-137">**솔루션 탐색기**에서 **TestApp** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **ID 및 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-137">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="8cd6f-138">**ID 및 액세스** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-138">The **Identity and Access** window appears.</span></span> <span data-ttu-id="8cd6f-139">**공급자**에서 **로컬 개발 STS로 응용 프로그램 테스트**를 선택한 다음 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-139">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="8cd6f-140">표시된 것처럼 다음 **\<tokenReplayDetection>** 요소를 *Web.config* 구성 파일의 **\<system.identityModel>** 및 **\<identityConfiguration>** 요소 바로 뒤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-140">Add the following **\<tokenReplayDetection>** element to the *Web.config* configuration file immediately following the **\<system.identityModel>** and **\<identityConfiguration>** elements, like shown:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="8cd6f-141">2단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="8cd6f-141">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="8cd6f-142">이 단계에서는 WIF 사용 가능 ASP.NET 응용 프로그램을 테스트하여 재생 검색이 사용하도록 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-142">In this step, you will test your WIF-enabled ASP.NET application to verify that replay detection has been enabled.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a><span data-ttu-id="8cd6f-143">재생 검색에 대한 WIF 사용 가능 ASP.NET 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="8cd6f-143">To test your WIF-enabled ASP.NET application for replay detection</span></span>  
  
1.  <span data-ttu-id="8cd6f-144">**F5** 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-144">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="8cd6f-145">기본 ASP.NET 홈페이지가 표시되고 개발 STS에서 반환되는 기본 사용자인 사용자 이름 *Terry*로 자동으로 인증되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-145">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="8cd6f-146">브라우저의 **뒤로** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-146">Press the browser’s **Back** button.</span></span> <span data-ttu-id="8cd6f-147">*ID1062: 토큰: ‘System.IdentityModel.Tokens.SamlSecurityToken’에 대해 재생이 검색되었습니다.*라는 설명에 이어 *AssertionId* 및 *Issuer*가 포함된 **‘/’ 응용 프로그램 서버 오류** 페이지가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-147">You should be presented with a **Server Error in ‘/’ Application** page with the following description: *ID1062: Replay has been detected for: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, followed by an *AssertionId* and an *Issuer*.</span></span>  
  
     <span data-ttu-id="8cd6f-148">토큰 재생이 검색될 때 <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> 형식의 예외가 throw되었으므로 이 오류 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-148">You are seeing this error page because an exception of type <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> was thrown when the token replay was detected.</span></span> <span data-ttu-id="8cd6f-149">토큰이 먼저 제공된 경우 초기 POST 요청을 다시 보내려고 하므로 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-149">This error occurs because you are attempting to re-send the initial POST request when the token was first presented.</span></span> <span data-ttu-id="8cd6f-150">**뒤로** 단추를 선택해도 서버에 대한 후속 요청에서 이 동작이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd6f-150">The **Back** button will not cause this behavior on subsequent requests to the server.</span></span>
