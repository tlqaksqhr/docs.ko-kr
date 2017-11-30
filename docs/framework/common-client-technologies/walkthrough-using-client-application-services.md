---
title: "연습: 클라이언트 응용 프로그램 서비스 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application services host [client application services]
- client application services, walkthroughs
ms.assetid: bb7c8950-4517-4dae-b705-b74a14059b26
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fba53a19810a91a2e679616e73ea8c5fc8d38da1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-using-client-application-services"></a><span data-ttu-id="13f29-102">연습: 클라이언트 응용 프로그램 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="13f29-102">Walkthrough: Using Client Application Services</span></span>
<span data-ttu-id="13f29-103">이 항목에서는 클라이언트 응용 프로그램 서비스를 사용하여 사용자를 인증하고 사용자 역할 및 설정을 검색하는 Windows 응용 프로그램을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-103">This topic describes how to create a Windows application that uses client application services to authenticate users and retrieve user roles and settings.</span></span>  
  
 <span data-ttu-id="13f29-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="13f29-105">Windows Forms 응용 프로그램을 만들고 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 디자이너를 통해 클라이언트 응용 프로그램 서비스를 사용하도록 설정 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-105">Create a Windows Forms application and use the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project designer to enable and configure client application services.</span></span>  
  
-   <span data-ttu-id="13f29-106">응용 프로그램 서비스를 호스트하고 클라이언트 구성을 테스트할 단순한 ASP.NET 웹 서비스 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-106">Create a simple ASP.NET Web Service application to host the application services and test your client configuration.</span></span>  
  
-   <span data-ttu-id="13f29-107">응용 프로그램에 폼 인증을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-107">Add forms authentication to your application.</span></span> <span data-ttu-id="13f29-108">먼저 하드 코드된 사용자 이름 및 암호를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-108">You will start by using a hard-coded user name and password to test the service.</span></span> <span data-ttu-id="13f29-109">그런 다음 응용 프로그램 구성에서 자격 증명 공급자로 지정하여 로그인 폼을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-109">You will then add a login form by specifying it as a credentials provider in your application configuration.</span></span>  
  
-   <span data-ttu-id="13f29-110">역할 기반 기능을 추가하고 "manager" 역할의 사용자에 대해서만 단추를 사용하도록 설정 및 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-110">Add role-based functionality, enabling and displaying a button only for users in the "manager" role.</span></span>  
  
-   <span data-ttu-id="13f29-111">웹 설정에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-111">Access Web settings.</span></span> <span data-ttu-id="13f29-112">먼저 프로젝트 디자이너의 **설정** 페이지에서 인증된(테스트) 사용자에 대한 웹 설정을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-112">You will start by loading Web settings for an authenticated (test) user on the **Settings** page of the project designer.</span></span> <span data-ttu-id="13f29-113">그런 다음 Windows Forms 디자이너를 사용하여 텍스트 상자를 웹 설정에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-113">You will then use the Windows Forms Designer to bind a text box to a Web setting.</span></span> <span data-ttu-id="13f29-114">끝으로, 수정된 값을 서버에 다시 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-114">Finally, you will save the modified value back to the server.</span></span>  
  
-   <span data-ttu-id="13f29-115">로그아웃을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-115">Implement logout.</span></span> <span data-ttu-id="13f29-116">로그아웃 옵션을 폼에 추가하고 로그아웃 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-116">You will add a logout option to the form and call a logout method.</span></span>  
  
-   <span data-ttu-id="13f29-117">오프라인 모드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-117">Enable offline mode.</span></span> <span data-ttu-id="13f29-118">사용자가 연결 상태를 지정할 수 있도록 확인란을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-118">You will provide a check box so that users can specify their connection status.</span></span> <span data-ttu-id="13f29-119">그런 다음 이 값을 사용하여 클라이언트 응용 프로그램 서비스 공급자가 해당 웹 서비스에 액세스하는 대신 로컬에 캐시된 데이터를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-119">You will then use this value to specify whether the client application service providers will use locally cached data instead of accessing their Web services.</span></span> <span data-ttu-id="13f29-120">끝으로, 응용 프로그램이 온라인 모드로 돌아가면 현재 사용자를 다시 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-120">Finally, you will re-authenticate the current user when the application returns to online mode.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="13f29-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="13f29-121">Prerequisites</span></span>  
 <span data-ttu-id="13f29-122">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-122">You need the following component to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="13f29-123">.</span><span class="sxs-lookup"><span data-stu-id="13f29-123">.</span></span>  
  
## <a name="creating-the-client-application"></a><span data-ttu-id="13f29-124">클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="13f29-124">Creating the Client Application</span></span>  
 <span data-ttu-id="13f29-125">먼저 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-125">The first thing that you will do is create a Windows Forms project.</span></span> <span data-ttu-id="13f29-126">이 연습에서는 익숙한 사용자가 더 많기 때문에 Windows Forms를 사용하지만 WPF(Windows Presentation Foundation) 프로젝트에 대한 프로세스는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-126">This walkthrough uses Windows Forms because more people are familiar with it, but the process is similar for Windows Presentation Foundation (WPF) projects.</span></span>  
  
#### <a name="to-create-a-client-application-and-enable-client-application-services"></a><span data-ttu-id="13f29-127">클라이언트 응용 프로그램을 만들고 클라이언트 응용 프로그램 서비스를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-127">To create a client application and enable client application services</span></span>  
  
1.  <span data-ttu-id="13f29-128">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 **파일 &#124; 새로 만들기 &#124; 프로젝트** 메뉴 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-128">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], select the **File &#124; New &#124; Project** menu option.</span></span>  
  
2.  <span data-ttu-id="13f29-129">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic** 또는 **Visual C#** 노드를 확장하고 **Windows** 프로젝트 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-129">In the **New Project** dialog box, in the **Project types** pane, expand the **Visual Basic** or **Visual C#** node and select the **Windows** project type.</span></span>  
  
3.  <span data-ttu-id="13f29-130">**.NET Framework 3.5** 가 선택되었는지 확인하고 **Windows Forms 응용 프로그램** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-130">Make sure that **.NET Framework 3.5** is selected, and then select the **Windows Forms Application** template.</span></span>  
  
4.  <span data-ttu-id="13f29-131">프로젝트 **이름** 을 `ClientAppServicesDemo`로 변경하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-131">Change the project **Name** to `ClientAppServicesDemo`, and then click **OK**.</span></span>  
  
     <span data-ttu-id="13f29-132">새 Windows Forms 프로젝트가 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-132">A new Windows Forms project is opened in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
5.  <span data-ttu-id="13f29-133">**프로젝트** 메뉴에서 **ClientAppServicesDemo 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-133">On the **Project** menu, select **ClientAppServicesDemo Properties**.</span></span>  
  
     <span data-ttu-id="13f29-134">프로젝트 디자이너가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-134">The project designer appears.</span></span>  
  
6.  <span data-ttu-id="13f29-135">**서비스** 탭에서 **클라이언트 응용 프로그램 서비스 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-135">On the **Services** tab, select **Enable client application services**.</span></span>  
  
7.  <span data-ttu-id="13f29-136">**폼 인증 사용** 이 선택되었는지 확인하고 **인증 서비스 위치**, **역할 서비스 위치**및 **웹 설정 서비스 위치** 를 `http://localhost:55555/AppServices`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-136">Make sure that **Use Forms authentication** is selected, and then set **Authentication service location**, **Roles service location**, and **Web settings service location** to `http://localhost:55555/AppServices`.</span></span>  
  
8.  <span data-ttu-id="13f29-137">[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 **응용 프로그램** 탭에서 **인증 모드** 를 **응용 프로그램 정의**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-137">For [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], on the **Application** tab, set **Authentication mode** to **Application-defined**.</span></span>  
  
 <span data-ttu-id="13f29-138">디자이너가 응용 프로그램의 app.config 파일에 지정된 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-138">The designer stores the specified settings in the application's app.config file.</span></span>  
  
 <span data-ttu-id="13f29-139">지금은 응용 프로그램이 동일한 호스트에서 세 서비스에 모두 액세스하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-139">At this point, the application is configured to access all three services from the same host.</span></span> <span data-ttu-id="13f29-140">다음 섹션에서는 호스트를 단순한 웹 서비스 응용 프로그램으로 만들어 클라이언트 구성을 테스트할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-140">In the next section, you will create the host as a simple Web service application, enabling you to test your client configuration.</span></span>  
  
## <a name="creating-the-application-services-host"></a><span data-ttu-id="13f29-141">응용 프로그램 서비스 호스트 만들기</span><span class="sxs-lookup"><span data-stu-id="13f29-141">Creating the Application Services Host</span></span>  
 <span data-ttu-id="13f29-142">이 섹션에서는 로컬 SQL Server Compact 데이터베이스 파일에서 사용자 데이터에 액세스하는 단순한 웹 서비스 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-142">In this section, you will create a simple Web service application that accesses user data from a local SQL Server Compact database file.</span></span> <span data-ttu-id="13f29-143">그런 다음 [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)를 사용하여 데이터베이스를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-143">Then, you will populate the database using the [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec).</span></span> <span data-ttu-id="13f29-144">이 간단한 구성을 통해 클라이언트 응용 프로그램을 신속하게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-144">This simple configuration enables you to quickly test your client application.</span></span> <span data-ttu-id="13f29-145">또는 전체 SQL Server 데이터베이스 또는 사용자 지정 <xref:System.Web.Security.MembershipProvider> 및 <xref:System.Web.Security.RoleProvider> 클래스를 통해 사용자 데이터에 액세스하도록 웹 서비스 호스트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-145">As an alternative, you can configure the Web service host to access user data from a full SQL Server database or through custom <xref:System.Web.Security.MembershipProvider> and <xref:System.Web.Security.RoleProvider> classes.</span></span> <span data-ttu-id="13f29-146">자세한 내용은 [Creating and Configuring the Application Services Database for SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13f29-146">For more information, see [Creating and Configuring the Application Services Database for SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2).</span></span>  
  
 <span data-ttu-id="13f29-147">다음 절차에서는 AppServices 웹 서비스를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-147">In the following procedure, you create and configure the AppServices Web service.</span></span>  
  
#### <a name="to-create-and-configure-the-application-services-host"></a><span data-ttu-id="13f29-148">응용 프로그램 서비스 호스트를 만들고 구성하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-148">To create and configure the application services host</span></span>  
  
1.  <span data-ttu-id="13f29-149">**솔루션 탐색기**에서 ClientAppServicesDemo 솔루션을 선택한 다음 **파일** 메뉴에서 **추가 &#124; 새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-149">In **Solution Explorer**, select the ClientAppServicesDemo solution, and then on the **File** menu, select **Add &#124; New Project**.</span></span>  
  
2.  <span data-ttu-id="13f29-150">**새 프로젝트 추가** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic** 또는 **Visual C#** 노드를 확장하고 **웹** 프로젝트 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-150">In the **Add New Project** dialog box, in the **Project types** pane, expand the **Visual Basic** or **Visual C#** node and select the **Web** project type.</span></span>  
  
3.  <span data-ttu-id="13f29-151">**.NET Framework 3.5** 가 선택되었는지 확인하고 **ASP.NET 웹 서비스 응용 프로그램** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-151">Make sure that **.NET Framework 3.5** is selected, and then select the **ASP.NET Web Service Application** template.</span></span>  
  
4.  <span data-ttu-id="13f29-152">프로젝트 **이름** 을 `AppServices` 로 변경하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-152">Change the project **Name** to `AppServices` and then click **OK**.</span></span>  
  
     <span data-ttu-id="13f29-153">새 ASP.NET 웹 서비스 응용 프로그램 프로젝트가 솔루션에 추가되고 Service1.asmx.vb 또는 service1.asmx.cs 파일이 편집기에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-153">A new ASP.NET Web service application project is added to the solution, and the Service1.asmx.vb or Service1.asmx.cs file appears in the editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13f29-154">이 예제에서는 Service1.asmx.vb 또는 service1.asmx.cs 파일이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-154">The Service1.asmx.vb or Service1.asmx.cs file is not used in this example.</span></span> <span data-ttu-id="13f29-155">작업 환경을 깔끔하게 유지하려는 경우 파일을 닫고 **솔루션 탐색기**에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-155">If you want to keep your work environment uncluttered, you can close it and delete it from **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="13f29-156">**솔루션 탐색기**에서 AppServices 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **AppServices 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-156">In **Solution Explorer**, select the AppServices project, and then on the **Project** menu, select **AppServices Properties**.</span></span>  
  
     <span data-ttu-id="13f29-157">프로젝트 디자이너가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-157">The project designer appears.</span></span>  
  
6.  <span data-ttu-id="13f29-158">**웹** 탭에서 **Visual Studio 개발 서버 사용** 이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-158">On the **Web** tab, make sure that **Use Visual Studio Development Server** is selected.</span></span>  
  
7.  <span data-ttu-id="13f29-159">**특정 포트**를 선택하고 값 `55555`를 지정한 다음 **가상 경로** 를 `/AppServices`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-159">Select **Specific port**, specify a value of `55555`, and then set **Virtual path** to `/AppServices`.</span></span>  
  
8.  <span data-ttu-id="13f29-160">모든 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-160">Save all files.</span></span>  
  
9. <span data-ttu-id="13f29-161">**솔루션 탐색기**에서 Web.config를 열고 `<system.web>` 여는 태그를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-161">In **Solution Explorer**, open Web.config and find the `<system.web>` opening tag.</span></span>  
  
10. <span data-ttu-id="13f29-162">다음 태그를 `<system.web>` 태그 앞에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-162">Add the following markup before the `<system.web>` tag.</span></span>  
  
     <span data-ttu-id="13f29-163">이 태그의 `authenticationService`, `profileService`및 `roleService` 요소는 응용 프로그램 서비스를 사용하도록 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-163">The `authenticationService`, `profileService`, and `roleService` elements in this markup enable and configure the application services.</span></span> <span data-ttu-id="13f29-164">테스트 목적으로 `requireSSL` 요소의 `authenticationService` 특성이 "false"로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-164">For testing purposes, the `requireSSL` attribute of the `authenticationService` element is set to "false".</span></span> <span data-ttu-id="13f29-165">`readAccessProperties` 요소의 `writeAccessProperties` 및 `profileService` 특성은 `WebSettingsTestText` 속성이 읽기/쓰기임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-165">The `readAccessProperties` and `writeAccessProperties` attributes of the `profileService` element indicate that the `WebSettingsTestText` property is read/write.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13f29-166">프로덕션 코드에서는 항상 SSL(Secure Sockets Layer, HTTPS 프로토콜 사용)을 통해 인증 서비스에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-166">In production code, you should always access the authentication service over the secure sockets layer (SSL, by using the HTTPS protocol).</span></span> <span data-ttu-id="13f29-167">SSL을 설정하는 방법에 대한 자세한 내용은 [SSL(Secure Sockets Layer) 구성(IIS 6.0 운영 가이드)](http://go.microsoft.com/fwlink/?LinkId=91844)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f29-167">For information about how to set up SSL, see [Configuring Secure Sockets Layer (IIS 6.0 Operations Guide)](http://go.microsoft.com/fwlink/?LinkId=91844).</span></span>  
  
    ```xml  
    <system.web.extensions>  
      <scripting>  
        <webServices>  
          <authenticationService enabled="true" requireSSL = "false"/>  
          <profileService enabled="true"  
            readAccessProperties="WebSettingsTestText"  
            writeAccessProperties="WebSettingsTestText" />  
          <roleService enabled="true"/>  
        </webServices>  
      </scripting>  
    </system.web.extensions>  
    ```  
  
11. <span data-ttu-id="13f29-168">`<system.web>` 요소 내에 있도록 다음 태그를 `<system.web>` 여는 태그 뒤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-168">Add the following markup after the `<system.web>` opening tag so that it is within the `<system.web>` element.</span></span>  
  
     <span data-ttu-id="13f29-169">`profile` 요소는 `WebSettingsTestText`라는 단일 웹 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-169">The `profile` element configures a single Web setting named `WebSettingsTestText`.</span></span>  
  
    ```xml  
    <profile enabled="true" >  
      <properties>  
        <add name="WebSettingsTestText" type="string"   
          readOnly="false" defaultValue="DefaultText"   
          serializeAs="String" allowAnonymous="false" />  
      </properties>  
    </profile>  
    ```  
  
 <span data-ttu-id="13f29-170">다음 절차에서는 ASP.NET 웹 사이트 관리 도구를 사용하여 서비스 구성을 완료하고 로컬 데이터베이스 파일을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-170">In the following procedure, you use the ASP.NET Web Site Administration tool to complete the service configuration and populate the local database file.</span></span> <span data-ttu-id="13f29-171">같은 이름의 두 역할에 속하는 `employee` 및 `manager` 라는 두 명의 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-171">You will add two users named `employee` and `manager` belonging to two roles with the same names.</span></span> <span data-ttu-id="13f29-172">사용자 암호는 각각 `employee!` 및 `manager!` 입니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-172">The user passwords are `employee!` and `manager!` respectively.</span></span>  
  
#### <a name="to-configure-membership-and-roles"></a><span data-ttu-id="13f29-173">멤버 자격 및 역할을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-173">To configure membership and roles</span></span>  
  
1.  <span data-ttu-id="13f29-174">**솔루션 탐색기**에서 AppServices 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **ASP.NET 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-174">In **Solution Explorer**, select the AppServices project, and then on the **Project** menu, select **ASP.NET Configuration**.</span></span>  
  
     <span data-ttu-id="13f29-175">**ASP.NET 웹 사이트 관리 도구** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-175">The **ASP.NET Web Site Administration Tool** appears.</span></span>  
  
2.  <span data-ttu-id="13f29-176">**보안** 탭에서 **보안 설정 마법사를 사용하여 보안을 단계별로 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-176">On the **Security** tab, click **Use the security Setup Wizard to configure security step by step**.</span></span>  
  
     <span data-ttu-id="13f29-177">**보안 설정 마법사** 가 나타나고 **시작** 단계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-177">The **Security Setup Wizard** appears and displays the **Welcome** step.</span></span>  
  
3.  <span data-ttu-id="13f29-178">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-178">Click **Next**.</span></span>  
  
     <span data-ttu-id="13f29-179">**액세스 방법 선택** 단계가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-179">The **Select Access Method** step appears.</span></span>  
  
4.  <span data-ttu-id="13f29-180">**인터넷에서**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-180">Select **From the internet**.</span></span> <span data-ttu-id="13f29-181">이렇게 하면 Windows 인증 대신 폼 인증을 사용하도록 서비스가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-181">This configures the service to use Forms authentication instead of Windows authentication.</span></span>  
  
5.  <span data-ttu-id="13f29-182">**다음** 을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-182">Click **Next** twice.</span></span>  
  
     <span data-ttu-id="13f29-183">**역할 정의** 단계가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-183">The **Define Roles** step appears.</span></span>  
  
6.  <span data-ttu-id="13f29-184">**이 웹 사이트에 역할 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-184">Select **Enable roles for this Web site**.</span></span>  
  
7.  <span data-ttu-id="13f29-185">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-185">Click **Next**.</span></span> <span data-ttu-id="13f29-186">**새 역할 만들기** 폼이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-186">The **Create New Role** form appears.</span></span>  
  
8.  <span data-ttu-id="13f29-187">**새 역할 이름** 텍스트 상자에 `manager` 를 입력하고 **역할 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-187">In the **New Role Name** text box, type `manager` and then click **Add Role**.</span></span>  
  
     <span data-ttu-id="13f29-188">**기존 역할** 테이블이 지정된 값으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-188">The **Existing Roles** table appears with the specified value.</span></span>  
  
9. <span data-ttu-id="13f29-189">**새 역할 이름** 텍스트 상자에서 `manager` 를 `employee` 로 바꾸고 **역할 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-189">In the **New Role Name** text box, replace `manager` with `employee` and then click **Add Role**.</span></span>  
  
     <span data-ttu-id="13f29-190">새 값이 **기존 역할** 테이블에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-190">The new value appears in the **Existing Roles** table.</span></span>  
  
10. <span data-ttu-id="13f29-191">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-191">Click **Next**.</span></span>  
  
     <span data-ttu-id="13f29-192">**새 사용자 추가** 단계가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-192">The **Add New Users** step appears.</span></span>  
  
11. <span data-ttu-id="13f29-193">**사용자 만들기** 폼에서 다음 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-193">In the **Create User** form, specify the following values.</span></span>  
  
  	|||  
  	|-|-|  
  	|<span data-ttu-id="13f29-194">**사용자 이름**</span><span class="sxs-lookup"><span data-stu-id="13f29-194">**User Name**</span></span>|`manager`|  
  	|<span data-ttu-id="13f29-195">**암호**</span><span class="sxs-lookup"><span data-stu-id="13f29-195">**Password**</span></span>|`manager!`|  
  	|<span data-ttu-id="13f29-196">**암호 확인**</span><span class="sxs-lookup"><span data-stu-id="13f29-196">**Confirm Password**</span></span>|`manager!`|  
  	|<span data-ttu-id="13f29-197">**전자 메일**</span><span class="sxs-lookup"><span data-stu-id="13f29-197">**E-mail**</span></span>|`manager@contoso.com`|  
  	|<span data-ttu-id="13f29-198">**보안 질문**</span><span class="sxs-lookup"><span data-stu-id="13f29-198">**Security Question**</span></span>|`manager`|  
  	|<span data-ttu-id="13f29-199">**보안 대답**</span><span class="sxs-lookup"><span data-stu-id="13f29-199">**Security Answer**</span></span>|`manager`|  
  
12. <span data-ttu-id="13f29-200">**사용자 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-200">Click **Create User**.</span></span>  
  
     <span data-ttu-id="13f29-201">성공 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-201">A success message appears.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13f29-202">**메일**, **보안 질문**및 **보안 대답** 값은 폼에 필요하지만 이 예제에서는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-202">The **E-mail**, **Security Question**, and **Security Answer** values are required by the form, but are not used in this example.</span></span>  
  
13. <span data-ttu-id="13f29-203">**계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-203">Click **Continue**.</span></span>  
  
     <span data-ttu-id="13f29-204">**사용자 만들기** 폼이 다시 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-204">The **Create User** form reappears.</span></span>  
  
14. <span data-ttu-id="13f29-205">**사용자 만들기** 폼에서 다음 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-205">In the **Create User** form, specify the following values.</span></span>  
  
  	|||  
  	|-|-|  
  	|<span data-ttu-id="13f29-206">**사용자 이름**</span><span class="sxs-lookup"><span data-stu-id="13f29-206">**User Name**</span></span>|`employee`|  
  	|<span data-ttu-id="13f29-207">**암호**</span><span class="sxs-lookup"><span data-stu-id="13f29-207">**Password**</span></span>|`employee!`|  
  	|<span data-ttu-id="13f29-208">**암호 확인**</span><span class="sxs-lookup"><span data-stu-id="13f29-208">**Confirm Password**</span></span>|`employee!`|  
  	|<span data-ttu-id="13f29-209">**전자 메일**</span><span class="sxs-lookup"><span data-stu-id="13f29-209">**E-mail**</span></span>|`employee@contoso.com`|  
  	|<span data-ttu-id="13f29-210">**보안 질문**</span><span class="sxs-lookup"><span data-stu-id="13f29-210">**Security Question**</span></span>|`Employee`|  
  	|<span data-ttu-id="13f29-211">**보안 대답**</span><span class="sxs-lookup"><span data-stu-id="13f29-211">**Security Answer**</span></span>|`employee`|  
  
15. <span data-ttu-id="13f29-212">**사용자 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-212">Click **Create User**.</span></span>  
  
     <span data-ttu-id="13f29-213">성공 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-213">A success message appears.</span></span>  
  
16. <span data-ttu-id="13f29-214">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-214">Click **Finish**.</span></span>  
  
     <span data-ttu-id="13f29-215">**웹 사이트 관리 도구** 가 다시 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-215">The **Web Site Administration Tool** reappears.</span></span>  
  
17. <span data-ttu-id="13f29-216">**사용자 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-216">Click **Manager users**.</span></span>  
  
     <span data-ttu-id="13f29-217">사용자 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-217">The list of users appears.</span></span>  
  
18. <span data-ttu-id="13f29-218">**employee** 사용자에 대해 **역할 편집** 을 클릭하고 **employee** 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-218">Click **Edit roles** for the **employee** user, and then select the **employee** role.</span></span>  
  
19. <span data-ttu-id="13f29-219">**manager** 사용자에 대해 **역할 편집** 을 클릭하고 **manager** 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-219">Click **Edit roles** for the **manager** user, and then select the **manager** role.</span></span>  
  
20. <span data-ttu-id="13f29-220">**웹 사이트 관리 도구**를 호스트하는 브라우저 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-220">Close the browser window that hosts the **Web Site Administration Tool**.</span></span>  
  
21. <span data-ttu-id="13f29-221">수정된 Web.config 파일을 다시 로드할지 여부를 묻는 메시지 상자가 나타나면 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-221">If a message box appears asking if you want to reload the modified Web.config file, click **Yes**.</span></span>  
  
 <span data-ttu-id="13f29-222">이제 웹 서비스 설정이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-222">This completes the Web service setup.</span></span> <span data-ttu-id="13f29-223">이제 F5 키를 눌러 클라이언트 응용 프로그램을 실행할 수 있으며, **ASP.NET 개발 서버** 가 클라이언트 응용 프로그램과 함께 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-223">At this point, you can press F5 to run the client application, and the **ASP.NET Development Server** will start automatically along with your client application.</span></span> <span data-ttu-id="13f29-224">응용 프로그램을 종료하면 서버가 계속 실행되지만 응용 프로그램을 다시 시작하면 서버가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-224">The server will continue to run after you exit the application, but will restart when you restart the application.</span></span> <span data-ttu-id="13f29-225">이렇게 하면 Web.config에 대한 변경 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-225">This allows it to detect any changes you have made to Web.config.</span></span>  
  
 <span data-ttu-id="13f29-226">서버를 수동으로 중지하려면 작업 표시줄의 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **중지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-226">To stop the server manually, right-click the ASP.NET Development Server icon in the notification area of the taskbar and then click **Stop**.</span></span> <span data-ttu-id="13f29-227">때때로 이 기능은 새로 다시 시작되는지 확인하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-227">This is useful occasionally to make sure that a clean restart occurs.</span></span>  
  
## <a name="adding-forms-authentication"></a><span data-ttu-id="13f29-228">폼 인증 추가</span><span class="sxs-lookup"><span data-stu-id="13f29-228">Adding Forms Authentication</span></span>  
 <span data-ttu-id="13f29-229">다음 절차에서는 사용자의 유효성을 검사하고 사용자가 잘못된 자격 증명을 제공하는 경우 액세스를 거부하는 코드를 기본 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-229">In the following procedure, you add code to the main form that attempts to validate the user, and denies access when the user supplies invalid credentials.</span></span> <span data-ttu-id="13f29-230">하드 코드된 사용자 이름 및 암호를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-230">You use a hard-coded user name and password to test the service.</span></span>  
  
#### <a name="to-validate-the-user-in-your-application-code"></a><span data-ttu-id="13f29-231">응용 프로그램 코드에서 사용자의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-231">To validate the user in your application code</span></span>  
  
1.  <span data-ttu-id="13f29-232">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트에 System.Web 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-232">In **Solution Explorer**, in the ClientAppServicesDemo project, add a reference to the System.Web assembly.</span></span>  
  
2.  <span data-ttu-id="13f29-233">Form1 파일을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-233">Select the Form1 file and then select **View &#124; Code** from the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] main menu.</span></span>  
  
3.  <span data-ttu-id="13f29-234">코드 편집기에서 Form1 파일의 맨 위에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-234">In the code editor, add the following statements to the top of the Form1 file.</span></span>  
  
     [!code-csharp[ClientApplicationServices#001](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#001)]
     [!code-vb[ClientApplicationServices#001](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#001)]  
  
4.  <span data-ttu-id="13f29-235">**솔루션 탐색기**에서 Form1을 두 번 클릭하여 디자이너를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-235">In **Solution Explorer**, double-click Form1 to display the designer.</span></span>  
  
5.  <span data-ttu-id="13f29-236">디자이너에서 폼 화면을 두 번 클릭하여 <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 라는 `Form1_Load`이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-236">In the designer, double-click the form surface to generate a <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler named `Form1_Load`.</span></span>  
  
     <span data-ttu-id="13f29-237">코드 편집기가 나타나고 커서가 `Form1_Load` 메서드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-237">The code editor appears with the cursor in the `Form1_Load` method.</span></span>  
  
6.  <span data-ttu-id="13f29-238">`Form1_Load` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-238">Add the following code to the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="13f29-239">이 코드는 응용 프로그램을 종료하여 인증되지 않은 사용자의 액세스를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-239">This code denies access to unauthenticated users by exiting the application.</span></span> <span data-ttu-id="13f29-240">또는 인증되지 않은 사용자가 폼에 액세스할 수 있게 하지만 특정 기능에 대한 액세스를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-240">Alternatively, you could allow unauthenticated users access to the form, but deny access to specific functionality.</span></span> <span data-ttu-id="13f29-241">일반적으로 사용자 이름 및 암호를 이렇게 하드 코드하지는 않지만 테스트 목적으로 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-241">Normally, you will not hard-code the user name and password like this, but it is useful for testing purposes.</span></span> <span data-ttu-id="13f29-242">다음 섹션에서는 로그인 대화 상자를 표시하고 예외 처리를 포함하는 보다 강력한 코드로 이 코드를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-242">In the next section, you will replace this code with more robust code that displays a login dialog box and includes exception handling.</span></span>  
  
     <span data-ttu-id="13f29-243">`static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드는 [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-243">Note that the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method is in the [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="13f29-244">이 메서드는 해당 작업을 구성된 인증 공급자에게 위임하고 인증에 성공하면 `true` 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-244">This method delegates its work to the configured authentication provider, and returns `true` if authentication is successful.</span></span> <span data-ttu-id="13f29-245">응용 프로그램에 클라이언트 인증 공급자에 대한 직접 참조가 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-245">Your application does not require a direct reference to the client authentication provider.</span></span>  
  
     [!code-csharp[ClientApplicationServices#300](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#300)]
     [!code-vb[ClientApplicationServices#300](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#300)]  
  
 <span data-ttu-id="13f29-246">이제 F5 키를 눌러 응용 프로그램을 실행할 수 있으며, 올바른 사용자 이름 및 암호를 제공하기 때문에 폼이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-246">You can now press F5 to run the application, and because you provide a correct user name and password, you will see the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13f29-247">응용 프로그램을 실행할 수 없는 경우 ASP.NET 개발 서버를 중지하세요.</span><span class="sxs-lookup"><span data-stu-id="13f29-247">If you are unable to run the application, try stopping the ASP.NET Development Server.</span></span> <span data-ttu-id="13f29-248">서버가 다시 시작되면 포트가 55555로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-248">When the server restarts, verify that the port is set to 55555.</span></span>  
  
 <span data-ttu-id="13f29-249">대신 오류 메시지를 확인하려면 <xref:System.Web.Security.Membership.ValidateUser%2A> 매개 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-249">To see the error message instead, change the <xref:System.Web.Security.Membership.ValidateUser%2A> parameters.</span></span> <span data-ttu-id="13f29-250">예를 들어 두 번째 `"manager!"` 매개 변수를 `"MANAGER"`와 같은 잘못된 암호로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-250">For example, replace the second `"manager!"` parameter with an incorrect password like `"MANAGER"`.</span></span>  
  
## <a name="adding-a-login-form-as-a-credentials-provider"></a><span data-ttu-id="13f29-251">자격 증명 공급자로 로그인 폼 추가</span><span class="sxs-lookup"><span data-stu-id="13f29-251">Adding a Login Form as a Credentials Provider</span></span>  
 <span data-ttu-id="13f29-252">응용 프로그램 코드에서 사용자 자격 증명을 획득하여 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-252">You can acquire the user credentials in your application code and pass them to the <xref:System.Web.Security.Membership.ValidateUser%2A> method.</span></span> <span data-ttu-id="13f29-253">그러나 나중에 변경하려는 경우를 위해 대체로 자격 증명을 획득하는 코드를 응용 프로그램 코드와 별도로 유지하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-253">However, it is often useful to keep your credentials-acquiring code separate from your application code, in case you want to change it later.</span></span>  
  
 <span data-ttu-id="13f29-254">다음 절차에서는 자격 증명 공급자를 사용하도록 응용 프로그램을 구성한 다음 두 매개 변수에 대해 모두 <xref:System.Web.Security.Membership.ValidateUser%2A> 를 전달하도록 <xref:System.String.Empty> 메서드 호출을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-254">In the following procedure, you configure your application to use a credentials provider, and then change your <xref:System.Web.Security.Membership.ValidateUser%2A> method call to pass <xref:System.String.Empty> for both parameters.</span></span> <span data-ttu-id="13f29-255">빈 문자열은 구성된 자격 증명 공급자의 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드를 호출하는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-255">The empty strings signal the <xref:System.Web.Security.Membership.ValidateUser%2A> method to call the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> method of the configured credentials provider.</span></span>  
  
#### <a name="to-configure-your-application-to-use-a-credentials-provider"></a><span data-ttu-id="13f29-256">자격 증명 공급자를 사용하도록 응용 프로그램을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-256">To configure your application to use a credentials provider</span></span>  
  
1.  <span data-ttu-id="13f29-257">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **ClientAppServicesDemo 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-257">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **ClientAppServicesDemo Properties**.</span></span>  
  
     <span data-ttu-id="13f29-258">프로젝트 디자이너가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-258">The project designer appears.</span></span>  
  
2.  <span data-ttu-id="13f29-259">**서비스** 탭에서 **선택 사항: 자격 증명 공급자** 를 다음 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-259">On the **Services** tab, set **Optional: Credential provider** to the following value.</span></span> <span data-ttu-id="13f29-260">이 값은 정규화된 어셈블리 형식 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-260">This value indicates the assembly-qualified type name.</span></span>  
  
    ```  
    ClientAppServicesDemo.Login, ClientAppServicesDemo  
    ```  
  
3.  <span data-ttu-id="13f29-261">Form1 코드 파일에서 `Form1_Load` 메서드의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-261">In the Form1 code file, replace the code in the `Form1_Load` method with the following code.</span></span>  
  
     <span data-ttu-id="13f29-262">이 코드는 환영 메시지를 표시한 후 다음 단계에서 추가할 `ValidateUsingCredentialsProvider` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-262">This code displays a welcome message and then calls the `ValidateUsingCredentialsProvider` method that you will add in the next step.</span></span> <span data-ttu-id="13f29-263">사용자가 인증되지 않은 경우 `ValidateUsingCredentialsProvider` 메서드가 `false` 를 반환하고 `Form1_Load` 메서드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-263">If the user is not authenticated, the `ValidateUsingCredentialsProvider` method returns `false` and the `Form1_Load` method returns.</span></span> <span data-ttu-id="13f29-264">이렇게 하면 응용 프로그램이 종료되기 전에 추가 코드가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-264">This prevents any additional code from running before the application exits.</span></span> <span data-ttu-id="13f29-265">환영 메시지는 응용 프로그램이 다시 시작될 때 이를 명확히 표시하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-265">The welcome message is useful to make it clear when the application restarts.</span></span> <span data-ttu-id="13f29-266">이 연습의 뒷부분에서 로그아웃을 구현할 때 응용 프로그램을 다시 시작하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-266">You will add code to restart the application when you implement logout later in this walkthrough.</span></span>  
  
     [!code-csharp[ClientApplicationServices#011](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#011)]
     [!code-vb[ClientApplicationServices#011](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#011)]  
  
4.  <span data-ttu-id="13f29-267">다음 메서드를 `Form1_Load` 메서드 뒤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-267">Add the following method after the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="13f29-268">이 메서드는 빈 문자열을 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 메서드에 전달하여 로그인 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-268">This method passes empty strings to the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method, which causes the Login dialog box to appear.</span></span> <span data-ttu-id="13f29-269">인증 서비스를 사용할 수 없는 경우 <xref:System.Web.Security.Membership.ValidateUser%2A> 메서드에서 <xref:System.Net.WebException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-269">If the authentication service is unavailable, the <xref:System.Web.Security.Membership.ValidateUser%2A> method will throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="13f29-270">이 경우 `ValidateUsingCredentialsProvider` 메서드는 경고 메시지를 표시하고 사용자에게 오프라인 모드에서 다시 시도할지 여부를 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-270">In this case, the `ValidateUsingCredentialsProvider` method displays a warning message and asks if the user wants to try again in offline mode.</span></span> <span data-ttu-id="13f29-271">이 기능을 사용하려면 **How to: Configure Client Application Services** 에 설명된 [오프라인으로 로그인할 수 있도록 로컬에 암호 해시 저장](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-271">This functionality requires the **Save password hash locally to enable offline login** feature described in [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span> <span data-ttu-id="13f29-272">이 기능은 기본적으로 새 프로젝트에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-272">This feature is enabled by default for new projects.</span></span>  
  
     <span data-ttu-id="13f29-273">사용자의 유효성이 검사되지 않은 경우 `ValidateUsingCredentialsProvider` 메서드는 오류 메시지를 표시하고 응용 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-273">If the user is not validated, the `ValidateUsingCredentialsProvider` method displays an error message and exits the application.</span></span> <span data-ttu-id="13f29-274">끝으로, 이 메서드는 인증 시도의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-274">Finally, this method returns the result of the authentication attempt.</span></span>  
  
     [!code-csharp[ClientApplicationServices#020](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#020)]
     [!code-vb[ClientApplicationServices#020](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#020)]  
  
### <a name="creating-a-login-form"></a><span data-ttu-id="13f29-275">로그인 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="13f29-275">Creating a Login Form</span></span>  
 <span data-ttu-id="13f29-276">자격 증명 공급자는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-276">A credentials provider is a class that implements the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> interface.</span></span> <span data-ttu-id="13f29-277">이 인터페이스에는 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 개체를 반환하는 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> 라는 단일 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-277">This interface has a single method named <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> that returns a <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> object.</span></span> <span data-ttu-id="13f29-278">다음 절차에서는 표시를 위해 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 를 구현하는 로그인 대화 상자를 만들고 사용자 지정 자격 증명을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-278">The following procedures describe how to create a login dialog box that implements <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> to display itself and return the user-specified credentials.</span></span>  
  
 <span data-ttu-id="13f29-279">[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 에서는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 로그인 폼 **템플릿을 제공하므로** 및 C#의 경우 별도 절차가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-279">Separate procedures are provided for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and C# because [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] provides a **Login Form** template.</span></span> <span data-ttu-id="13f29-280">이렇게 하면 시간과 코딩 활동을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-280">This saves some time and coding effort.</span></span>  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-visual-basic"></a><span data-ttu-id="13f29-281">Visual Basic에서 자격 증명 공급자로 로그인 대화 상자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="13f29-281">To create a login dialog box as a credentials provider in Visual Basic</span></span>  
  
1.  <span data-ttu-id="13f29-282">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-282">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="13f29-283">**새 항목 추가** 대화 상자에서 **로그인 폼** 템플릿을 선택하고 항목 **이름** 을 `Login.vb`로 변경한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-283">In the **Add New Item** dialog box, select the **Login Form** template, change the item **Name** to `Login.vb`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="13f29-284">Windows Forms 디자이너에서 로그인 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-284">The login dialog box appears in the Windows Forms Designer.</span></span>  
  
3.  <span data-ttu-id="13f29-285">디자이너에서 **확인** 단추를 선택한 다음 **속성** 창에서 `DialogResult` 를 `OK`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-285">In the designer, select the **OK** button and then, in the **Properties** window, set `DialogResult` to `OK`.</span></span>  
  
4.  <span data-ttu-id="13f29-286">디자이너에서 폼의 `CheckBox` 암호 **텍스트 상자 아래에** 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-286">In the designer, add a `CheckBox` control to the form under the **Password** text box.</span></span>  
  
5.  <span data-ttu-id="13f29-287">**속성** 창에서 **(이름)** 값으로 `rememberMeCheckBox`를 지정하고 **텍스트** 값으로 `&Remember me`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-287">In the **Properties** window, specify a **(Name)** value of `rememberMeCheckBox` and a **Text** value of `&Remember me`.</span></span>  
  
6.  <span data-ttu-id="13f29-288">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-288">Select **View &#124; Code** from the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] main menu.</span></span>  
  
7.  <span data-ttu-id="13f29-289">코드 편집기에서 파일의 맨 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-289">In the code editor, add the following code to the top of the file.</span></span>  
  
     [!code-vb[ClientApplicationServices#101](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#101)]  
  
8.  <span data-ttu-id="13f29-290">클래스가 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 인터페이스를 구현하도록 클래스 서명을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-290">Modify the class signature so that the class implements the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> interface.</span></span>  
  
     [!code-vb[ClientApplicationServices#110](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#110)]  
  
9. <span data-ttu-id="13f29-291">커서가 `IClientformsAuthenticationCredentialsProvider`뒤에 있는지 확인하고 Enter 키를 눌러 `GetCredentials` 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-291">Make sure that the cursor is after `IClientformsAuthenticationCredentialsProvider`, and then press ENTER to generate the `GetCredentials` method.</span></span>  
  
10. <span data-ttu-id="13f29-292"><xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 구현을 찾아 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-292">Locate the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> implementation and then replace it with the following code.</span></span>  
  
     [!code-vb[ClientApplicationServices#120](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#120)]  
  
 <span data-ttu-id="13f29-293">다음 C# 절차에서는 단순한 로그인 대화 상자에 대한 전체 코드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-293">The following C# procedure provides the entire code listing for a simple login dialog box.</span></span> <span data-ttu-id="13f29-294">이 대화 상자의 레이아웃은 다소 조잡하지만 중요한 부분은 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-294">The layout for this dialog box is a bit crude, but the important part is the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> implementation.</span></span>  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-c"></a><span data-ttu-id="13f29-295">C#에서 자격 증명 공급자로 로그인 대화 상자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="13f29-295">To create a login dialog box as a credentials provider in C#</span></span>  
  
1.  <span data-ttu-id="13f29-296">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **클래스 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-296">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **Add Class**.</span></span>  
  
2.  <span data-ttu-id="13f29-297">**새 항목 추가** 대화 상자에서 **이름** 을 `Login.cs`로 변경한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-297">In the **Add New Item** dialog box, change the **Name** to `Login.cs`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="13f29-298">Login.cs 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-298">The Login.cs file opens in the code editor.</span></span>  
  
3.  <span data-ttu-id="13f29-299">기본 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-299">Replace the default code with the following code.</span></span>  
  
     [!code-csharp[ClientApplicationServices#200](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#200)]  
  
 <span data-ttu-id="13f29-300">이제 응용 프로그램을 실행하고 로그인 대화 상자가 표시되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-300">You can now run the application and see the login dialog box appear.</span></span> <span data-ttu-id="13f29-301">이 코드를 테스트하려면 다른 자격 증명(유효한 자격 증명과 잘못된 자격 증명 둘 다)을 시도하고 유효한 자격 증명으로만 폼에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-301">To test this code, try different credentials, both valid and invalid, and confirm that you can access the form only with valid credentials.</span></span> <span data-ttu-id="13f29-302">유효한 사용자 이름은 `employee` 및 `manager` 이고 암호는 각각 `employee!` 및 `manager!` 입니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-302">Valid user names are `employee` and `manager` with passwords `employee!` and `manager!` respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13f29-303">지금은 **암호 저장** 을 선택하지 마세요. 그렇지 않으면 이 연습의 뒷부분에서 로그아웃을 구현할 때까지 다른 사용자로 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-303">Do not select **Remember me** at this point or you will not be able to login as another user until you implement logout later in this walkthrough.</span></span>  
  
## <a name="adding-role-based-functionality"></a><span data-ttu-id="13f29-304">역할 기반 기능 추가</span><span class="sxs-lookup"><span data-stu-id="13f29-304">Adding Role-Based Functionality</span></span>  
 <span data-ttu-id="13f29-305">다음 절차에서는 폼에 단추를 추가하고 manager 역할의 사용자에게만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-305">In the following procedure, you add a button to the form and display it only for users in the manager role.</span></span>  
  
#### <a name="to-change-the-user-interface-based-on-user-role"></a><span data-ttu-id="13f29-306">사용자 역할에 따라 사용자 인터페이스를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-306">To change the user interface based on user role</span></span>  
  
1.  <span data-ttu-id="13f29-307">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트의 Form1을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-307">In **Solution Explorer**, in the ClientAppServicesDemo project, select Form1 and then select **View &#124; Designer** from the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] main menu.</span></span>  
  
2.  <span data-ttu-id="13f29-308">디자이너에서 **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-308">In the designer, add a <xref:System.Windows.Forms.Button> control to the form from the **ToolBox**.</span></span>  
  
3.  <span data-ttu-id="13f29-309">**속성** 창에서 단추의 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-309">In the **Properties** window, set the following properties for the button.</span></span>  
  
  	|<span data-ttu-id="13f29-310">속성</span><span class="sxs-lookup"><span data-stu-id="13f29-310">Property</span></span>|<span data-ttu-id="13f29-311">값</span><span class="sxs-lookup"><span data-stu-id="13f29-311">Value</span></span>|  
  	|--------------|-----------|  
  	|<span data-ttu-id="13f29-312">**(이름)**</span><span class="sxs-lookup"><span data-stu-id="13f29-312">**(Name)**</span></span>|<span data-ttu-id="13f29-313">managerOnlyButton</span><span class="sxs-lookup"><span data-stu-id="13f29-313">managerOnlyButton</span></span>|  
  	|<span data-ttu-id="13f29-314">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="13f29-314">**Text**</span></span>|<span data-ttu-id="13f29-315">&Manager task</span><span class="sxs-lookup"><span data-stu-id="13f29-315">&Manager task</span></span>|  
  	|<span data-ttu-id="13f29-316">**표시**</span><span class="sxs-lookup"><span data-stu-id="13f29-316">**Visible**</span></span>|`False`|  
  
4.  <span data-ttu-id="13f29-317">Form1에 대한 코드 편집기에서 `Form1_Load` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-317">In the code editor for Form1, add the following code to the end of the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="13f29-318">이 코드는 다음 단계에서 추가할 `DisplayButtonForManagerRole` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-318">This code calls the `DisplayButtonForManagerRole` method that you will add in the next step.</span></span>  
  
     [!code-csharp[ClientApplicationServices#012](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#012)]
     [!code-vb[ClientApplicationServices#012](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#012)]  
  
5.  <span data-ttu-id="13f29-319">Form1 클래스의 끝에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-319">Add the following method to the end of the Form1 class.</span></span>  
  
     <span data-ttu-id="13f29-320">이 메서드는 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 통해 반환된 <xref:System.Security.Principal.IPrincipal>의 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-320">This method calls the <xref:System.Security.Principal.IPrincipal.IsInRole%2A> method of the <xref:System.Security.Principal.IPrincipal> returned by the `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="13f29-321">클라이언트 응용 프로그램 서비스를 사용하도록 구성된 응용 프로그램에 대해 이 속성은 <xref:System.Web.ClientServices.ClientRolePrincipal>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-321">For applications configured to use client application services, this property returns a <xref:System.Web.ClientServices.ClientRolePrincipal>.</span></span> <span data-ttu-id="13f29-322">이 클래스는 <xref:System.Security.Principal.IPrincipal> 인터페이스를 구현하기 때문에 명시적으로 참조할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-322">Because this class implements the <xref:System.Security.Principal.IPrincipal> interface, you do not need to reference it explicitly.</span></span>  
  
     <span data-ttu-id="13f29-323">사용자가 "manager" 역할인 경우 `DisplayButtonForManagerRole` 메서드는 <xref:System.Windows.Forms.Control.Visible%2A> 의 `managerOnlyButton` 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-323">If the user is in the "manager" role, the `DisplayButtonForManagerRole` method sets the <xref:System.Windows.Forms.Control.Visible%2A> property of the `managerOnlyButton` to `true`.</span></span> <span data-ttu-id="13f29-324">또한 이 메서드는 <xref:System.Net.WebException> 이 발생하여 역할 서비스를 사용할 수 없음을 나타내는 경우 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-324">This method also displays an error message if a <xref:System.Net.WebException> is thrown, which indicates that the roles service is unavailable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13f29-325"><xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> 메서드는 사용자 로그인이 만료된 경우 항상 `false` 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-325">The <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> method will always return `false` if the user login has expired.</span></span> <span data-ttu-id="13f29-326">이 연습에 대한 예제 코드에 표시된 것처럼 응용 프로그램이 인증 후 즉시 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 한 번 호출하는 경우에는 이 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-326">This will not occur if your application calls the <xref:System.Security.Principal.IPrincipal.IsInRole%2A> method one time shortly after authentication, as shown in the example code for this walkthrough.</span></span> <span data-ttu-id="13f29-327">다른 시간에 응용 프로그램이 사용자 역할을 검색해야 하는 경우 해당 로그인이 만료된 사용자의 유효성을 다시 검사하는 코드를 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-327">If your application must retrieve user roles at other times, you might want to add code to revalidate users whose login has expired.</span></span> <span data-ttu-id="13f29-328">모든 유효한 사용자가 역할에 할당되면 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> 메서드를 호출하여 로그인이 만료되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-328">If all valid users are assigned to roles, you can determine whether the login has expired by calling the <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="13f29-329">역할이 반환되지 않는 경우 로그인이 만료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-329">If no roles are returned, the login has expired.</span></span> <span data-ttu-id="13f29-330">이 기능의 예는 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f29-330">For an example of this functionality, see the <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> method.</span></span> <span data-ttu-id="13f29-331">이 기능은 응용 프로그램 구성에서 **서버 쿠키가 만료될 때마다 다시 사용자 로그온** 을 선택한 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-331">This functionality is only necessary if you have selected **Require users to log on again whenever the server cookie expires** in your application configuration.</span></span> <span data-ttu-id="13f29-332">자세한 내용은 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13f29-332">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span>  
  
     [!code-csharp[ClientApplicationServices#030](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#030)]
     [!code-vb[ClientApplicationServices#030](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#030)]  
  
 <span data-ttu-id="13f29-333">인증에 성공하면 클라이언트 인증 공급자가 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 <xref:System.Web.ClientServices.ClientRolePrincipal> 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-333">If authentication is successful, the client authentication provider sets the <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Web.ClientServices.ClientRolePrincipal> class.</span></span> <span data-ttu-id="13f29-334">이 클래스는 작업이 구성된 역할 공급자에게 위임되도록 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-334">This class implements the <xref:System.Security.Principal.IPrincipal.IsInRole%2A> method so that the work is delegated to the configured role provider.</span></span> <span data-ttu-id="13f29-335">이전처럼 응용 프로그램 코드에 서비스 공급자에 대한 직접 참조는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-335">As before, your application code does not require a direct reference to the service provider.</span></span>  
  
 <span data-ttu-id="13f29-336">이제 응용 프로그램을 실행하고 employee로 로그인하여 단추가 표시되지 않는 것을 확인한 다음 manager로 로그인하여 단추를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-336">You can now run the application and log in as employee to see that the button does not appear, and then log in as manager to see the button.</span></span>  
  
## <a name="accessing-web-settings"></a><span data-ttu-id="13f29-337">웹 설정 액세스</span><span class="sxs-lookup"><span data-stu-id="13f29-337">Accessing Web Settings</span></span>  
 <span data-ttu-id="13f29-338">다음 절차에서는 폼에 텍스트 상자를 추가하고 웹 설정에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-338">In the following procedure, you add a text box to the form and bind it to a Web setting.</span></span> <span data-ttu-id="13f29-339">인증 및 역할을 사용하는 이전 코드와 마찬가지로 설정 코드는 설정 공급자에 직접 액세스하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-339">Like the previous code that uses authentication and roles, your settings code does not access the settings provider directly.</span></span> <span data-ttu-id="13f29-340">대신, `Settings` 에서 프로젝트에 대해 생성된 강력한 형식의 `Properties.Settings.Default` 클래스(C#에서 `My.Settings` 로 액세스, [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]로 액세스)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-340">Instead, it uses the strongly-typed `Settings` class (accessed as `Properties.Settings.Default` in C# and `My.Settings` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) generated for your project by [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
#### <a name="to-use-web-settings-in-your-user-interface"></a><span data-ttu-id="13f29-341">사용자 인터페이스에서 웹 설정을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-341">To use Web settings in your user interface</span></span>  
  
1.  <span data-ttu-id="13f29-342">작업 표시줄의 알림 영역을 검사하여 **ASP.NET 웹 개발 서버** 가 계속 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-342">Make sure that the **ASP.NET Web Development Server** is still running by checking the notification area of the taskbar.</span></span> <span data-ttu-id="13f29-343">서버를 중지한 경우 응용 프로그램을 다시 시작(서버가 자동으로 시작됨)한 다음 로그인 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-343">If you have stopped the server, restart the application (which starts the server automatically) then close the login dialog box.</span></span>  
  
2.  <span data-ttu-id="13f29-344">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **ClientAppServicesDemo 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-344">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **ClientAppServicesDemo Properties**.</span></span>  
  
     <span data-ttu-id="13f29-345">프로젝트 디자이너가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-345">The project designer appears.</span></span>  
  
3.  <span data-ttu-id="13f29-346">**설정** 탭에서 **웹 설정 로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-346">On the **Settings** tab, click **Load Web Settings**.</span></span>  
  
     <span data-ttu-id="13f29-347">**로그인** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-347">A **Login** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="13f29-348">employee 또는 manager에 대한 자격 증명을 입력하고 **로그인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-348">Enter credentials for employee or manager and click **Log In**.</span></span> <span data-ttu-id="13f29-349">인증된 사용자만 액세스할 수 있도록 구성된 웹 설정을 사용하므로 **로그인 건너뛰기** 를 클릭하면 설정이 로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-349">The Web setting you will use is configured for access by authenticated users only, so clicking **Skip Login** will not load any settings.</span></span>  
  
     <span data-ttu-id="13f29-350">`WebSettingsTestText` 설정이 기본값 `DefaultText`로 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-350">The `WebSettingsTestText` setting appears in the designer with the default value of `DefaultText`.</span></span> <span data-ttu-id="13f29-351">또한 `WebSettingsTestText` 속성을 포함하는 `Settings` 클래스가 프로젝트에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-351">Additionally, a `Settings` class that contains a `WebSettingsTestText` property is generated for your project.</span></span>  
  
5.  <span data-ttu-id="13f29-352">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트의 Form1을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-352">In **Solution Explorer**, in the ClientAppServicesDemo project, select Form1 and then select **View &#124; Designer** from the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] main menu.</span></span>  
  
6.  <span data-ttu-id="13f29-353">디자이너에서 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-353">In the designer, add a <xref:System.Windows.Forms.TextBox> control to the form.</span></span>  
  
7.  <span data-ttu-id="13f29-354">**속성** 창에서 **(이름)** 값으로 `webSettingsTestTextBox`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-354">In the **Properties** window, specify a **(Name)** value of `webSettingsTestTextBox`.</span></span>  
  
8.  <span data-ttu-id="13f29-355">코드 편집기에서 `Form1_Load` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-355">In the code editor, add the following code to the end of the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="13f29-356">이 코드는 다음 단계에서 추가할 `BindWebSettingsTestTextBox` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-356">This code calls the `BindWebSettingsTestTextBox` method that you will add in the next step.</span></span>  
  
     [!code-csharp[ClientApplicationServices#013](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#013)]
     [!code-vb[ClientApplicationServices#013](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#013)]  
  
9. <span data-ttu-id="13f29-357">Form1 클래스의 끝에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-357">Add the following method to the end of the Form1 class.</span></span>  
  
     <span data-ttu-id="13f29-358">이 메서드는 <xref:System.Windows.Forms.TextBox.Text%2A> 의 `webSettingsTestTextBox` 속성을 이 절차의 앞부분에서 생성된 `WebSettingsTestText` 클래스의 `Settings` 속성에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-358">This method binds the <xref:System.Windows.Forms.TextBox.Text%2A> property of the `webSettingsTestTextBox` to the `WebSettingsTestText` property of the `Settings` class generated earlier in this procedure.</span></span> <span data-ttu-id="13f29-359">또한 이 메서드는 <xref:System.Net.WebException> 이 발생하여 웹 설정 서비스를 사용할 수 없음을 나타내는 경우 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-359">This method also displays an error message if a <xref:System.Net.WebException> is thrown, which indicates that the Web settings service is unavailable.</span></span>  
  
     [!code-csharp[ClientApplicationServices#040](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#040)]
     [!code-vb[ClientApplicationServices#040](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#040)]  
  
    > [!NOTE]
    >  <span data-ttu-id="13f29-360">일반적으로 데이터 바인딩을 통해 컨트롤과 웹 설정 간의 자동 양방향 통신을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-360">You will typically use data binding to enable automatic two-way communication between a control and a Web setting.</span></span> <span data-ttu-id="13f29-361">그러나 다음 예제와 같이 웹 설정에 직접 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-361">However, you can also access Web settings directly as shown in the following example:</span></span>  
  
     [!code-csharp[ClientApplicationServices#322](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#322)]
     [!code-vb[ClientApplicationServices#322](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#322)]  
  
10. <span data-ttu-id="13f29-362">디자이너에서 폼을 선택한 다음 **속성** 창에서 **이벤트** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-362">In the designer, select the form, and then, in the **Properties** window, click the **Events** button.</span></span>  
  
11. <span data-ttu-id="13f29-363"><xref:System.Windows.Forms.Form.FormClosing> 이벤트를 선택한 다음 Enter 키를 눌러 이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-363">Select the <xref:System.Windows.Forms.Form.FormClosing> event and then press ENTER to generate an event handler.</span></span>  
  
12. <span data-ttu-id="13f29-364">생성된 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-364">Replace the generated method with the following code.</span></span>  
  
     <span data-ttu-id="13f29-365"><xref:System.Windows.Forms.Form.FormClosing> 이벤트 처리기는 다음 섹션에서 추가할 로그아웃 기능에서도 사용되는 `SaveSettings` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-365">The <xref:System.Windows.Forms.Form.FormClosing> event handler calls the `SaveSettings` method, which is also used by the logout functionality that you will add in the next section.</span></span> <span data-ttu-id="13f29-366">`SaveSettings` 메서드는 먼저 사용자가 로그아웃하지 않았음을 확인합니다. 이 작업을 위해 현재 보안 주체가 반환한 <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> 의 <xref:System.Security.Principal.IIdentity> 속성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-366">The `SaveSettings` method first confirms that the user has not logged out. It does this by checking the <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> property of the <xref:System.Security.Principal.IIdentity> returned by the current principal.</span></span> <span data-ttu-id="13f29-367">현재 보안 주체는 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> 속성을 통해 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-367">The current principal is retrieved through the `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="13f29-368">클라이언트 응용 프로그램 서비스에 대해 사용자가 인증된 경우 인증 형식은 "ClientForms"입니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-368">If the user has been authenticated for client application services, the authentication type will be "ClientForms".</span></span> <span data-ttu-id="13f29-369">사용자가 로그아웃한 후 유효한 Windows ID를 가지고 있을 수도 있기 때문에 `SaveSettings` 메서드는 단순히 <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> 속성을 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-369">The `SaveSettings` method cannot just check the <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> property because the user might have a valid Windows identity after logout.</span></span>  
  
     <span data-ttu-id="13f29-370">사용자가 로그아웃하지 않은 경우 `SaveSettings` 메서드는 이 절차의 앞부분에서 생성된 <xref:System.Configuration.ApplicationSettingsBase.Save%2A> 클래스의 `Settings` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-370">If the user has not logged out, the `SaveSettings` method calls the <xref:System.Configuration.ApplicationSettingsBase.Save%2A> method of the `Settings` class generated earlier in this procedure.</span></span> <span data-ttu-id="13f29-371">인증 쿠키가 만료된 경우 이 메서드에서 <xref:System.Net.WebException> 이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-371">This method can throw a <xref:System.Net.WebException> if the authentication cookie has expired.</span></span> <span data-ttu-id="13f29-372">이 문제는 응용 프로그램 구성에서 **서버 쿠키가 만료될 때마다 다시 사용자 로그온** 을 선택한 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-372">This occurs only if you have selected **Require users to log on again whenever the server cookie expires** in your application configuration.</span></span> <span data-ttu-id="13f29-373">자세한 내용은 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13f29-373">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span> <span data-ttu-id="13f29-374">`SaveSettings` 메서드는 <xref:System.Web.Security.Membership.ValidateUser%2A> 호출을 통해 로그인 대화 상자를 표시하여 쿠키 만료를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-374">The `SaveSettings` method handles cookie expiration by calling <xref:System.Web.Security.Membership.ValidateUser%2A> to display the login dialog box.</span></span> <span data-ttu-id="13f29-375">사용자가 성공적으로 로그인하는 경우 `SaveSettings` 메서드는 자신을 호출하여 설정을 다시 저장하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-375">If the user logs in successfully, the `SaveSettings` method tries to save the settings again by calling itself.</span></span>  
  
     <span data-ttu-id="13f29-376">이전 코드와 같이 `SaveSettings` 메서드는 원격 서비스를 사용할 수 없는 경우 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-376">Like in previous code, the `SaveSettings` method displays an error message if the remote service is unavailable.</span></span> <span data-ttu-id="13f29-377">설정 공급자가 원격 서비스에 액세스할 수 없는 경우에도 설정이 로컬 캐시에 저장된 후 응용 프로그램이 다시 시작될 때 다시 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-377">If the settings provider cannot access the remote service, the settings are still saved to the local cache and reloaded when the application restarts.</span></span>  
  
     [!code-csharp[ClientApplicationServices#050](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#050)]
     [!code-vb[ClientApplicationServices#050](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#050)]  
  
13. <span data-ttu-id="13f29-378">Form1 클래스의 끝에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-378">Add the following method to the end of the Form1 class.</span></span>  
  
     <span data-ttu-id="13f29-379">이 코드에서는 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> 이벤트를 처리하고 설정을 저장할 수 없는 경우 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-379">This code handles the <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> event and displays a warning if any of the settings could not be saved.</span></span> <span data-ttu-id="13f29-380">설정 서비스를 사용할 수 없거나 인증 쿠키가 만료된 경우에는 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-380">The <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> event does not occur if the settings service is unavailable or if the authentication cookie has expired.</span></span> <span data-ttu-id="13f29-381"><xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트가 발생하는 경우의 한 가지 예는 사용자가 이미 로그아웃한 경우입니다. `SaveSettings` 메서드에서 <xref:System.Configuration.ApplicationSettingsBase.Save%2A> 메서드 호출 바로 앞에 로그아웃 코드를 추가하여 이 이벤트 처리기를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-381">One example of when the <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> event will occur is if the user has already logged out. You can test this event handler by adding logout code to the `SaveSettings` method directly before the <xref:System.Configuration.ApplicationSettingsBase.Save%2A> method call.</span></span> <span data-ttu-id="13f29-382">사용할 수 있는 로그아웃 코드는 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-382">Logout code that you can use is described in the next section.</span></span>  
  
     [!code-csharp[ClientApplicationServices#090](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#090)]
     [!code-vb[ClientApplicationServices#090](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#090)]  
  
14. <span data-ttu-id="13f29-383">C#의 경우 `Form1_Load` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-383">For C#, add the following code to the end of the `Form1_Load` method.</span></span> <span data-ttu-id="13f29-384">이 코드는 마지막 단계에서 추가한 메서드를 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-384">This code associates the method you added in the last step with the <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> event.</span></span>  
  
     [!code-csharp[ClientApplicationServices#015](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#015)]  
  
 <span data-ttu-id="13f29-385">이 시점에서 응용 프로그램을 테스트하려면 employee 및 manager 둘 다로 여러 번 실행하고 텍스트 상자에 다른 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-385">To test the application at this point, run it multiple times as both employee and manager, and type different values into the text box.</span></span> <span data-ttu-id="13f29-386">값은 사용자 단위로 세션 간에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-386">The values will persist across sessions on a per-user basis.</span></span>  
  
## <a name="implementing-logout"></a><span data-ttu-id="13f29-387">로그아웃 구현</span><span class="sxs-lookup"><span data-stu-id="13f29-387">Implementing Logout</span></span>  
 <span data-ttu-id="13f29-388">사용자가 로그인할 때 **암호 저장** 확인란을 선택하는 경우 응용 프로그램이 이후 실행 시 사용자를 자동으로 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-388">When the user selects the **Remember me** check box when logging in, the application will automatically authenticate the user on subsequent runs.</span></span> <span data-ttu-id="13f29-389">응용 프로그램이 오프라인 모드에 있는 동안 또는 인증 쿠키가 만료될 때까지 자동 인증이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-389">Automatic authentication will then continue while the application is in offline mode or until the authentication cookie expires.</span></span> <span data-ttu-id="13f29-390">그러나 때로는 여러 사용자가 응용 프로그램에 액세스해야 하거나 단일 사용자가 다른 자격 증명으로 로그인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-390">Sometimes, however, multiple users will need access to the application or a single user might occasionally log in with different credentials.</span></span> <span data-ttu-id="13f29-391">이 시나리오를 사용하려면 다음 절차에 설명된 대로 로그아웃 기능을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-391">To enable this scenario, you must implement logout functionality, as described in the following procedure.</span></span>  
  
#### <a name="to-implement-logout-functionality"></a><span data-ttu-id="13f29-392">로그아웃 기능을 구현하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-392">To implement logout functionality</span></span>  
  
1.  <span data-ttu-id="13f29-393">Form1 디자이너에서 **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-393">In the Form1 designer, add a <xref:System.Windows.Forms.Button> control to the form from the **ToolBox**.</span></span>  
  
2.  <span data-ttu-id="13f29-394">**속성** 창에서 **(이름)** 값으로 `logoutButton`를 지정하고 **텍스트** 값으로 **&Log Out**을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-394">In the **Properties** window, specify a **(Name)** value of `logoutButton` and a **Text** value of **&Log Out**.</span></span>  
  
3.  <span data-ttu-id="13f29-395">`logoutButton`을 두 번 클릭하여 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-395">Double-click the `logoutButton` to generate a <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     <span data-ttu-id="13f29-396">코드 편집기가 나타나고 커서가 `logoutButton_Click` 메서드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-396">The code editor appears with the cursor in the `logoutButton_Click` method.</span></span>  
  
4.  <span data-ttu-id="13f29-397">생성된 `logoutButton_Click` 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-397">Replace the generated `logoutButton_Click` method with the following code.</span></span>  
  
     <span data-ttu-id="13f29-398">이 이벤트 처리기는 먼저 이전 섹션에서 추가한 `SaveSettings` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-398">This event handler first calls the `SaveSettings` method that you added in the previous section.</span></span> <span data-ttu-id="13f29-399">그런 다음 이벤트 처리기에서 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-399">Then, the event handler calls the <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="13f29-400">인증 서비스를 사용할 수 없는 경우 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> 메서드에서 <xref:System.Net.WebException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-400">If the authentication service is unavailable, the <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> method will throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="13f29-401">이 경우 `logoutButton_Click` 메서드는 경고 메시지를 표시하고 일시적으로 오프라인 모드로 전환하여 사용자를 로그아웃합니다. 오프라인 모드는 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-401">In this case, the `logoutButton_Click` method displays a warning message and switches temporarily to offline mode to log the user out. Offline mode is described in the next section.</span></span>  
  
     <span data-ttu-id="13f29-402">로그아웃하면 로컬 인증 쿠키가 삭제되므로 응용 프로그램이 다시 시작될 때 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-402">Logout deletes the local authentication cookie so that login will be required when the application is restarted.</span></span> <span data-ttu-id="13f29-403">로그아웃한 후 이벤트 처리기에서 응용 프로그램을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-403">After logout, the event handler restarts the application.</span></span> <span data-ttu-id="13f29-404">응용 프로그램이 다시 시작되면 환영 메시지를 표시한 후 로그인 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-404">When the application restarts, it displays the welcome message followed by the login dialog box.</span></span> <span data-ttu-id="13f29-405">환영 메시지는 응용 프로그램이 다시 시작되었음을 명확히 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-405">The welcome message makes it clear that the application has restarted.</span></span> <span data-ttu-id="13f29-406">이렇게 하면 사용자가 설정을 저장하기 위해 로그인한 다음 응용 프로그램이 다시 시작되어 다시 로그인해야 하는 경우에 잠재적인 혼동을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-406">This prevents potential confusion if the user must log in to save settings, and then must log in again because the application has restarted.</span></span>  
  
     [!code-csharp[ClientApplicationServices#070](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#070)]
     [!code-vb[ClientApplicationServices#070](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#070)]  
  
 <span data-ttu-id="13f29-407">로그아웃 기능을 테스트하려면 응용 프로그램을 실행하고 로그인 대화 상자에서 **암호 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-407">To test the logout functionality, run the application and select **Remember me** on the Login dialog box.</span></span> <span data-ttu-id="13f29-408">응용 프로그램을 닫은 후 다시 시작하여 더 이상 로그인할 필요가 없음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-408">Next, close and restart the application to confirm that you no longer have to log in.</span></span> <span data-ttu-id="13f29-409">끝으로, 로그아웃을 클릭하여 응용 프로그램을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-409">Finally, restart the application by clicking Log out.</span></span>  
  
## <a name="enabling-offline-mode"></a><span data-ttu-id="13f29-410">오프라인 모드 사용</span><span class="sxs-lookup"><span data-stu-id="13f29-410">Enabling Offline Mode</span></span>  
 <span data-ttu-id="13f29-411">다음 절차에서는 사용자가 오프라인 모드로 전환할 수 있도록 폼에 확인란을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-411">In the following procedure, you add a check box to the form to enable the user to enter offline mode.</span></span> <span data-ttu-id="13f29-412">응용 프로그램은 `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> 속성을 `true`로 설정하여 오프라인 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-412">Your application indicates offline mode by setting the `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="13f29-413">오프라인 상태는 로컬 하드 디스크에서 <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> 속성이 나타내는 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-413">The offline status is stored on the local hard disk at the location indicated by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="13f29-414">즉, 오프라인 상태는 사용자 단위 및 응용 프로그램 단위로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-414">This means that the offline status is stored on a per-user, per-application basis.</span></span>  
  
 <span data-ttu-id="13f29-415">오프라인 모드에서는 모든 클라이언트 응용 프로그램 서비스 요청이 서비스에 액세스하는 대신 로컬 캐시에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-415">In offline mode, all client application service requests retrieve data from the local cache instead of trying to access the services.</span></span> <span data-ttu-id="13f29-416">기본 구성에서 로컬 데이터는 암호화된 형태의 사용자 암호를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-416">In the default configuration, the local data includes an encrypted form of the user's password.</span></span> <span data-ttu-id="13f29-417">이렇게 하면 응용 프로그램이 오프라인 모드에 있는 동안 사용자가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-417">This enables the user to log in while the application is in offline mode.</span></span> <span data-ttu-id="13f29-418">자세한 내용은 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13f29-418">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span>  
  
#### <a name="to-enable-offline-mode-in-your-application"></a><span data-ttu-id="13f29-419">응용 프로그램에서 오프라인 모드를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="13f29-419">To enable offline mode in your application</span></span>  
  
1.  <span data-ttu-id="13f29-420">**솔루션 탐색기**에서 ClientAppServicesDemo 프로젝트의 Form1을 선택한 다음 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 주 메뉴에서 **보기 &#124; 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-420">In **Solution Explorer**, in the ClientAppServicesDemo project, select Form1 and then select **View &#124; Designer** from the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] main menu.</span></span>  
  
2.  <span data-ttu-id="13f29-421">디자이너에서 <xref:System.Windows.Forms.CheckBox> 컨트롤을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-421">In the designer, add a <xref:System.Windows.Forms.CheckBox> control to the form.</span></span>  
  
3.  <span data-ttu-id="13f29-422">**속성** 창에서 **(이름)** 값으로 `workOfflineCheckBox`를 지정하고 **텍스트** 값으로 **&Work offline**을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-422">In the **Properties** window, specify a **(Name)** value of `workOfflineCheckBox` and a **Text** value of **&Work offline**.</span></span>  
  
4.  <span data-ttu-id="13f29-423">**속성** 창에서 **이벤트** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-423">In the **Properties** window, click the **Events** button.</span></span>  
  
5.  <span data-ttu-id="13f29-424"><xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트를 선택한 다음 Enter 키를 눌러 이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-424">Select the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event and then press ENTER to generate an event handler.</span></span>  
  
6.  <span data-ttu-id="13f29-425">생성된 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-425">Replace the generated method with the following code.</span></span>  
  
     <span data-ttu-id="13f29-426">이 코드는 <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> 값을 업데이트하고 온라인 모드로 돌아갈 때 사용자의 유효성을 자동으로 다시 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-426">This code updates the <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> value and silently revalidates the user when they return to online mode.</span></span> <span data-ttu-id="13f29-427"><xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> 메서드는 캐시된 자격 증명을 사용하므로 사용자가 명시적으로 로그인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-427">The <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> method uses the cached credentials so that the user does not have to explicitly log in.</span></span> <span data-ttu-id="13f29-428">인증 서비스를 사용할 수 없는 경우 경고 메시지가 나타나고 응용 프로그램이 오프라인 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-428">If the authentication service is unavailable, a warning message appears and the application stays offline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13f29-429"><xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> 메서드는 편의상의 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-429">The <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> method is for convenience only.</span></span> <span data-ttu-id="13f29-430">반환 값이 없기 때문에 유효성 재검사가 실패했는지 여부를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-430">Because it does not have a return value, it cannot indicate whether revalidation has failed.</span></span> <span data-ttu-id="13f29-431">예를 들어 서버에서 사용자 자격 증명이 변경된 경우 유효성 재검사가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-431">Revalidation can fail, for example, if the user credentials have changed on the server.</span></span> <span data-ttu-id="13f29-432">이 경우 서비스 호출이 실패한 후 명시적으로 사용자의 유효성을 검사하는 코드를 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-432">In this case, you might want to include code that explicitly validates users after a service call fails.</span></span> <span data-ttu-id="13f29-433">자세한 내용은 이 연습의 앞부분에 있는 웹 설정 액세스 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f29-433">For more information, see the Accessing Web Settings section earlier in this walkthrough.</span></span>  
  
     <span data-ttu-id="13f29-434">유효성 재검사 후에 이 코드는 이전에 추가한 `SaveSettings` 메서드를 호출하여 변경 내용을 로컬 웹 설정에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-434">After revalidation, this code saves any changes to the local Web settings by calling the `SaveSettings` method that you added previously.</span></span> <span data-ttu-id="13f29-435">그런 다음 프로젝트 <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> 클래스의 `Settings` 메서드(C#에서는 `Properties.Settings.Default` 로 액세스, `My.Settings` 에서는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]로 액세스)를 호출하여 서버에서 새 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-435">It then retrieves any new values on the server by calling the <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> method of the project's `Settings` class (accessed as `Properties.Settings.Default` in C# and `My.Settings` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[ClientApplicationServices#080](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#080)]
     [!code-vb[ClientApplicationServices#080](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#080)]  
  
7.  <span data-ttu-id="13f29-436">`Form1_Load` 메서드의 끝에 다음 코드를 추가하여 확인란이 현재 연결 상태를 표시하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-436">Add the following code to the end of the `Form1_Load` method to make sure that the check box displays the current connection state.</span></span>  
  
     [!code-csharp[ClientApplicationServices#014](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#014)]
     [!code-vb[ClientApplicationServices#014](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#014)]  
  
 <span data-ttu-id="13f29-437">이제 예제 응용 프로그램이 완성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-437">This completes the example application.</span></span> <span data-ttu-id="13f29-438">오프라인 기능을 테스트하려면 응용 프로그램을 실행하고 employee 또는 manager로 로그인한 다음 **오프라인으로 작업**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-438">To test the offline capability, run the application, log in as either employee or manager, and then select **Work offline**.</span></span> <span data-ttu-id="13f29-439">텍스트 상자의 값을 수정하고 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-439">Modify the value in the text box, and then close the application.</span></span> <span data-ttu-id="13f29-440">응용 프로그램을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-440">Restart the application.</span></span> <span data-ttu-id="13f29-441">로그인하기 전에 서버를 수동으로 중지하려면 작업 표시줄의 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **중지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-441">Before you log in, right-click the ASP.NET Development Server icon in the notification area of the taskbar and then click **Stop**.</span></span> <span data-ttu-id="13f29-442">그런 다음 일반적인 방법으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-442">Then, log in like normal.</span></span> <span data-ttu-id="13f29-443">서버가 실행되지 않는 경우에도 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-443">Even when the server is not running, you can still log in.</span></span> <span data-ttu-id="13f29-444">텍스트 상자 값을 수정하고 종료한 후 다시 시작하여 수정된 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-444">Modify the text box value, exit, and restart to see the modified value.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="13f29-445">요약</span><span class="sxs-lookup"><span data-stu-id="13f29-445">Summary</span></span>  
 <span data-ttu-id="13f29-446">이 연습에서는 Windows Forms 응용 프로그램에서 클라이언트 응용 프로그램 서비스를 사용하도록 설정 및 사용하는 방법을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-446">In this walkthrough, you learned how to enable and use client application services in a Windows Forms application.</span></span> <span data-ttu-id="13f29-447">테스트 서버를 설정한 후 사용자를 인증하고 서버에서 사용자 역할 및 응용 프로그램 설정을 검색하는 코드를 응용 프로그램에 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-447">After setting up a test server, you added code to your application to authenticate users and retrieve user roles and application settings from the server.</span></span> <span data-ttu-id="13f29-448">또한 연결을 사용할 수 없을 때 응용 프로그램에서 원격 서비스 대신 로컬 데이터 캐시를 사용하도록 오프라인 모드를 사용하는 방법을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-448">You also learned how to enable offline mode so that your application uses a local data cache instead of the remote services when connectivity is not available.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="13f29-449">다음 단계</span><span class="sxs-lookup"><span data-stu-id="13f29-449">Next Steps</span></span>  
 <span data-ttu-id="13f29-450">실제 응용 프로그램에서는 사용할 수 없는 경우가 있거나 통지 없이 다운될 수 있는 원격 서버에서 많은 사용자의 데이터에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-450">In a real-world application, you will access data for many users from a remote server that may not always be available, or may go down without notice.</span></span> <span data-ttu-id="13f29-451">강력한 응용 프로그램을 만들려면 서비스를 사용할 수 없는 상황에 적절하게 대응해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-451">To make your application robust, you must respond appropriately to situations where the service is not available.</span></span> <span data-ttu-id="13f29-452">이 연습에서는 try/catch 블록을 포함하여 <xref:System.Net.WebException> 을 catch하고 서비스를 사용할 수 없는 경우 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-452">This walkthrough includes try/catch blocks to catch a <xref:System.Net.WebException> and display an error message when the service is not available.</span></span> <span data-ttu-id="13f29-453">프로덕션 코드에서는 오프라인 모드로 전환하거나, 응용 프로그램을 종료하거나, 특정 기능에 대한 액세스를 거부하여 이러한 경우를 처리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-453">In production code, you might want to handle this case by switching to offline mode, exiting the application, or denying access to specific functionality.</span></span>  
  
 <span data-ttu-id="13f29-454">응용 프로그램 보안을 강화하려면 배포 전에 응용 프로그램과 서버를 철저히 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13f29-454">To increase the security of your application, make sure to thoroughly test the application and server before deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f29-455">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13f29-455">See Also</span></span>  
 [<span data-ttu-id="13f29-456">클라이언트 응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="13f29-456">Client Application Services</span></span>](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [<span data-ttu-id="13f29-457">클라이언트 응용 프로그램 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="13f29-457">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [<span data-ttu-id="13f29-458">방법: 클라이언트 응용 프로그램 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="13f29-458">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [<span data-ttu-id="13f29-459">ASP.NET 웹 사이트 관리 도구</span><span class="sxs-lookup"><span data-stu-id="13f29-459">ASP.NET Web Site Administration Tool</span></span>](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)  
 [<span data-ttu-id="13f29-460">SQL Server에 대한 응용 프로그램 서비스 데이터베이스 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="13f29-460">Creating and Configuring the Application Services Database for SQL Server</span></span>](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)  
 [<span data-ttu-id="13f29-461">연습: ASP.NET 응용 프로그램 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="13f29-461">Walkthrough: Using ASP.NET Application Services</span></span>](http://msdn.microsoft.com/library/f3f394f0-20d6-4361-aa8f-4b21bf4933eb)
