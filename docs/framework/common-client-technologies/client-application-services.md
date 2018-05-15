---
title: 클라이언트 응용 프로그램 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
ms.openlocfilehash: d67b7467bdacdfca054d0ecd11a81c7d25b158f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="client-application-services"></a><span data-ttu-id="ffeb4-102">클라이언트 응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="ffeb4-102">Client Application Services</span></span>
<span data-ttu-id="ffeb4-103">클라이언트 응용 프로그램 서비스를 통해 Microsoft ASP.NET 2.0 AJAX 확장에 포함된 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 로그인, 역할 및 프로필 응용 프로그램 서비스를 사용하는 Windows 기반 응용 프로그램을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-103">Client application services make it easy for you to create Windows-based applications that use the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] login, roles, and profile application services included in the Microsoft ASP.NET 2.0 AJAX Extensions.</span></span> <span data-ttu-id="ffeb4-104">이 서비스를 통해 여러 웹 응용 프로그램과 Windows 기반 응용 프로그램이 단일 서버에서 사용자 정보와 사용자 관리 기능을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-104">These services enable multiple Web and Windows-based applications to share user information and user-management functionality from a single server.</span></span> <span data-ttu-id="ffeb4-105">예를 들어 이 서비스를 통해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-105">For example, you can use these services to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ffeb4-106">사용자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-106">Authenticate a user.</span></span> <span data-ttu-id="ffeb4-107">인증 서비스를 통해 사용자 ID를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-107">You can use the authentication service to verify a user's identity.</span></span>  
  
-   <span data-ttu-id="ffeb4-108">인증된 사용자의 역할을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-108">Determine the role or roles of an authenticated user.</span></span> <span data-ttu-id="ffeb4-109">역할 서비스를 통해 사용자 역할에 따라 응용 프로그램의 사용자 인터페이스를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-109">You can use the roles service to change the user interface of your application depending on the user's role.</span></span> <span data-ttu-id="ffeb4-110">예를 들어 관리자 역할에 있는 사용자에게 추가 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-110">For example, you can provide additional features for users who are in an administrator role.</span></span>  
  
-   <span data-ttu-id="ffeb4-111">서버에 있는 사용자별 응용 프로그램 설정을 저장하고 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-111">Store and access per-user application settings located on the server.</span></span> <span data-ttu-id="ffeb4-112">웹 설정 서비스(프로필 서비스라고도 함)를 통해 여러 응용 프로그램과 위치에서 설정을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-112">You can use the Web settings service (also known as the profile service) to share settings across multiple applications and locations.</span></span>  
  
 <span data-ttu-id="ffeb4-113">클라이언트 응용 프로그램 서비스는 응용 프로그램 구성 파일에서 지정할 수 있는 클라이언트 서비스 공급자를 통해 웹 서비스 확장성 모델을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-113">Client application services take advantage of the Web services extensibility model through client service providers that you can specify in your application configuration files.</span></span> <span data-ttu-id="ffeb4-114">이 서비스는 네트워크 연결을 사용할 수 없는 경우 인증, 역할 및 설정 데이터를 위해 로컬 캐시를 사용하는 오프라인 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-114">These service providers include offline functionality that uses a local cache for authentication, roles, and settings data when a network connection is unavailable.</span></span>  
  
 <span data-ttu-id="ffeb4-115">[!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 응용 프로그램 서비스에 대한 자세한 내용은 [ASP.NET 응용 프로그램 서비스 개요](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-115">For more information about the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] application services, see [ASP.NET Application Services Overview](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffeb4-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ffeb4-116">In This Section</span></span>  
 [<span data-ttu-id="ffeb4-117">클라이언트 응용 프로그램 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="ffeb4-117">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 <span data-ttu-id="ffeb4-118">클라이언트 응용 프로그램 서비스 공급자를 통해 제공되는 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-118">Describes the features available through the client application service providers.</span></span>  
  
 [<span data-ttu-id="ffeb4-119">방법: 클라이언트 응용 프로그램 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="ffeb4-119">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 <span data-ttu-id="ffeb4-120">Visual Studio 프로젝트 디자이너를 사용하여 응용 프로그램 서비스를 사용하도록 설정하고 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-120">Describes how to use the Visual Studio project designer to enable and configuration application services.</span></span> <span data-ttu-id="ffeb4-121">또한 App.config 파일에 대한 해당 변경 내용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-121">Also describes the corresponding changes to your App.config file.</span></span>  
  
 [<span data-ttu-id="ffeb4-122">방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현</span><span class="sxs-lookup"><span data-stu-id="ffeb4-122">How to: Implement User Login with Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 <span data-ttu-id="ffeb4-123">응용 프로그램이 클라이언트 인증 서비스 공급자를 사용하도록 구성된 경우 사용자의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-123">Describes how to validate a user when your application is configured to use a client authentication service provider.</span></span>  
  
 [<span data-ttu-id="ffeb4-124">연습: 클라이언트 응용 프로그램 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="ffeb4-124">Walkthrough: Using Client Application Services</span></span>](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 <span data-ttu-id="ffeb4-125">모든 클라이언트 응용 프로그램 서비스 기능을 단일 응용 프로그램에 결합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-125">Describes how to combine all client application services features in a single application.</span></span> <span data-ttu-id="ffeb4-126">이 연습에서는 완벽한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-126">This walkthrough provides end-to-end guidance.</span></span> <span data-ttu-id="ffeb4-127">예를 들어 클라이언트 응용 프로그램 서비스를 테스트하는 데 사용할 수 있는 ASP.NET 웹 서비스 응용 프로그램을 만드는 방법에 대한 지침을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeb4-127">For example, it includes instructions on how to create an ASP.NET Web Service Application that you can use to test client application services.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ffeb4-128">참조</span><span class="sxs-lookup"><span data-stu-id="ffeb4-128">Reference</span></span>  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a><span data-ttu-id="ffeb4-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffeb4-129">See Also</span></span>  
 [<span data-ttu-id="ffeb4-130">ASP.NET 응용 프로그램 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="ffeb4-130">ASP.NET Application Services Overview</span></span>](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [<span data-ttu-id="ffeb4-131">Microsoft Ajax에서 양식 인증 사용</span><span class="sxs-lookup"><span data-stu-id="ffeb4-131">Using Forms Authentication with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [<span data-ttu-id="ffeb4-132">Microsoft Ajax에서 역할 정보 사용</span><span class="sxs-lookup"><span data-stu-id="ffeb4-132">Using Roles Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [<span data-ttu-id="ffeb4-133">Microsoft Ajax에서 프로필 정보 사용</span><span class="sxs-lookup"><span data-stu-id="ffeb4-133">Using Profile Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [<span data-ttu-id="ffeb4-134">ASP.NET 인증</span><span class="sxs-lookup"><span data-stu-id="ffeb4-134">ASP.NET Authentication</span></span>](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 <span data-ttu-id="ffeb4-135">[역할을 사용하여 인증 관리](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span><span class="sxs-lookup"><span data-stu-id="ffeb4-135">[Managing Authorization Using Roles](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span></span>  
 [<span data-ttu-id="ffeb4-136">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="ffeb4-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)
