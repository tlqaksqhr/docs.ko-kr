---
title: "방법: WIF 추적 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 516e065bc360538e7b62807a5492c0c6c9d16e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="2344a-102">방법: WIF 추적 사용</span><span class="sxs-lookup"><span data-stu-id="2344a-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="2344a-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="2344a-103">Applies To</span></span>  
  
-   <span data-ttu-id="2344a-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="2344a-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="2344a-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="2344a-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="2344a-106">요약</span><span class="sxs-lookup"><span data-stu-id="2344a-106">Summary</span></span>  
 <span data-ttu-id="2344a-107">이 방법은 ASP.NET 응용 프로그램에서 WIF 추적을 사용하도록 설정하기 위한 자세한 단계별 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="2344a-108">또한 추적 수신기 및 로그가 제대로 작동하는지 확인하기 위해 응용 프로그램을 테스트하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="2344a-109">이 방법 설명에 보안 토큰 서비스(STS)를 만들기 위한 자세한 지침은 없으며, 그 대신 ID 및 액세스 도구와 함께 제공되는 개발 STS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="2344a-110">개발 STS가 실제 인증을 수행하는 것은 아니며, 테스트 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="2344a-111">이 방법을 완료하려면 ID 및 액세스 도구를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="2344a-112">[ID 및 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-112">It can be downloaded from the following location: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2344a-113">WS-Federation 프로토콜을 사용하는 수동 응용 프로그램에 WIF 추적을 사용하면 응용 프로그램이 DoS(서비스 거부) 공격에 노출되거나 악의적인 주체에게 정보가 공개될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="2344a-114">여기에는 수동 RP 및 수동 STS가 둘 다 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="2344a-115">따라서 프로덕션 환경에서는 수동 RP 또는 STS에 WIF 추적을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="2344a-116">목차</span><span class="sxs-lookup"><span data-stu-id="2344a-116">Contents</span></span>  
  
-   <span data-ttu-id="2344a-117">목표</span><span class="sxs-lookup"><span data-stu-id="2344a-117">Objectives</span></span>  
  
-   <span data-ttu-id="2344a-118">개요</span><span class="sxs-lookup"><span data-stu-id="2344a-118">Overview</span></span>  
  
-   <span data-ttu-id="2344a-119">단계 요약</span><span class="sxs-lookup"><span data-stu-id="2344a-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="2344a-120">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기 및 추적 사용</span><span class="sxs-lookup"><span data-stu-id="2344a-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="2344a-121">2단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="2344a-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="2344a-122">목표</span><span class="sxs-lookup"><span data-stu-id="2344a-122">Objectives</span></span>  
  
-   <span data-ttu-id="2344a-123">ID 및 액세스 도구에서 WIF 및 개발 STS를 사용하는 간단한 ASP.NET 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="2344a-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="2344a-124">추적 사용 및 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="2344a-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="2344a-125">개요</span><span class="sxs-lookup"><span data-stu-id="2344a-125">Overview</span></span>  
 <span data-ttu-id="2344a-126">추적을 사용하면 토큰, 쿠키, 클레임, 프로토콜 메시지 등을 포함하여 WIF에 관련된 다양한 문제를 디버그 및 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="2344a-127">WIF 추적은 WCF 추적과 비슷합니다. 예를 들어 추적의 자세한 정도를 선택하여 중요 메시지에서 모든 메시지까지 모든 것을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="2344a-128">WIF 추적은 Service Trace Viewer 도구를 사용하여 볼 수 있는 **.xml** 파일 또는 **.svclog** 파일에서 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="2344a-129">이 도구는 컴퓨터에서 Windows SDK 설치 경로의 **bin** 디렉터리에 있습니다(예: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**).</span><span class="sxs-lookup"><span data-stu-id="2344a-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="2344a-130">단계 요약</span><span class="sxs-lookup"><span data-stu-id="2344a-130">Summary of Steps</span></span>  
  
-   <span data-ttu-id="2344a-131">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기 및 추적 사용</span><span class="sxs-lookup"><span data-stu-id="2344a-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="2344a-132">2단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="2344a-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="2344a-133">1단계 – 간단한 ASP.NET Web Forms 응용 프로그램 만들기 및 추적 사용</span><span class="sxs-lookup"><span data-stu-id="2344a-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="2344a-134">이 단계에서는 새 ASP.NET Web Forms 응용 프로그램을 만들고 *Web.config* 파일을 수정하여 추적을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="2344a-135">간단한 ASP.NET 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="2344a-135">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="2344a-136">Visual Studio를 시작하고 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="2344a-137">**새 프로젝트** 창에서 **ASP.NET Web Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="2344a-138">**이름**에서 `TestApp`을 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="2344a-139">**솔루션 탐색기**에서 **TestApp** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **ID 및 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="2344a-140">**ID 및 액세스** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="2344a-141">**공급자**에서 **로컬 개발 STS로 응용 프로그램 테스트**를 선택한 다음 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="2344a-142">**C:** 드라이브 루트에 **logs** 폴더를 새로 만듭니다(예: **C:\logs**).</span><span class="sxs-lookup"><span data-stu-id="2344a-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7.  <span data-ttu-id="2344a-143">다음 **\<system.diagnostics>** 요소를 *Web.config* 구성 파일의 닫는 **\</configSections>** 요소 바로 뒤에 추가합니다. 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="2344a-144">**initializeData** 특성에 지정된 디렉터리 위치는 로깅을 시작하기 전에 이미 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="2344a-145">해당 위치가 없으면 로그가 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="2344a-146">위의 구성 설정은 WIF에 대한 **동사** 추적을 사용하도록 설정하고 결과 로그를 **C:logsWIF.xml** 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="2344a-147">2단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="2344a-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="2344a-148">이 단계에서는 WIF 사용 가능 ASP.NET 응용 프로그램을 테스트하여 로그가 기록되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="2344a-149">성공적인 추적을 위해 WIF 사용 가능 ASP.NET 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="2344a-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1.  <span data-ttu-id="2344a-150">**F5** 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="2344a-151">기본 ASP.NET 홈페이지가 표시되고 개발 STS에서 반환되는 기본 사용자인 사용자 이름 *Terry*로 자동으로 인증되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="2344a-152">브라우저 창을 닫고 **C:\logs** 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="2344a-153">텍스트 편집기를 사용하여 **C:\logs\WIF.xml** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3.  <span data-ttu-id="2344a-154">**WIF.xml** 파일을 검사하고 **\<E2ETraceEvent>**로 시작하는 항목이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2344a-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="2344a-155">이러한 추적에는 **\<TraceRecord>** 요소와 추적된 작업에 대한 설명이 포함됩니다(예: **SecurityToken 유효성 검사**).</span><span class="sxs-lookup"><span data-stu-id="2344a-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>
