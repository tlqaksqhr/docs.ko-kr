---
title: '방법: Windows 서비스 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
manager: douge
ms.openlocfilehash: 7719af9393bee816665040d6e4ced191419d0855
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517864"
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="76045-102">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="76045-102">How to: Create Windows Services</span></span>
<span data-ttu-id="76045-103">서비스를 만들 때는 **Windows 서비스**라는 Visual Studio 프로젝트 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76045-103">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="76045-104">이 템플릿은 적절한 클래스 및 네임스페이스를 참조하고, 서비스의 기본 클래스에서 상속을 설정하고, 개발자가 재정의할 가능성이 높은 여러 메서드를 재정의하여 대부분의 작업을 자동으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-104">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="76045-105">Visual Studio Express 버전에서는 Windows 서비스 프로젝트 템플릿을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76045-105">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="76045-106">작동하는 서비스를 만들려면 최소한 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-106">At a minimum, to create a functional service you must:</span></span>  
  
-   <span data-ttu-id="76045-107"><xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-107">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
-   <span data-ttu-id="76045-108">서비스 응용 프로그램에 필요한 설치 관리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76045-108">Create the necessary installers for your service application.</span></span>  
  
-   <span data-ttu-id="76045-109"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드의 코드를 재정의 및 지정하여 서비스 동작 방식을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-109">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="76045-110">Windows 서비스 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="76045-110">To create a Windows Service application</span></span>  
  
1.  <span data-ttu-id="76045-111">**Windows 서비스** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76045-111">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76045-112">템플릿을 사용하지 않고 서비스를 작성하는 방법에 대한 지침은 [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)(방법: 프로그래밍 방식으로 서비스 작성)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76045-112">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
2.  <span data-ttu-id="76045-113">**속성** 창에서 서비스의 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-113">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="76045-114">![ServiceName 속성을 설정합니다.](../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span><span class="sxs-lookup"><span data-stu-id="76045-114">![Set the ServiceName property.](../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76045-115"><xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성의 값은 항상 설치 관리자 클래스에 기록된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-115">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="76045-116">이 속성을 변경하는 경우에는 설치 관리자 클래스의 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성도 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-116">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3.  <span data-ttu-id="76045-117">다음 속성을 설정하여 서비스 작동 방식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-117">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="76045-118">속성</span><span class="sxs-lookup"><span data-stu-id="76045-118">Property</span></span>|<span data-ttu-id="76045-119">설정</span><span class="sxs-lookup"><span data-stu-id="76045-119">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="76045-120">서비스가 실행 중지 요청을 수락함을 나타내려면 `True`로 설정하고 서비스 중지를 차단하려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-120">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="76045-121">서비스가 활성화되어 있는 컴퓨터가 종료될 때 서비스에서 알림을 수신하여 `True` 프로시저를 호출할 수 있도록 설정할 것임을 나타내려면 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-121">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="76045-122">서비스가 실행 일시 중지 또는 다시 시작 요청을 수락함을 나타내려면 `True`로 설정하고 서비스 일시 중지 및 다시 시작을 차단하려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-122">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="76045-123">서비스가 컴퓨터의 전원 상태 변경 알림을 처리할 수 있음을 나타내려면 `True`로 설정하고 이러한 변경에 대한 알림을 받지 않도록 하려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-123">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="76045-124">서비스에서 작업을 수행할 때 응용 프로그램 이벤트 로그에 정보 항목을 기록하려면 `True`로 설정하고 이 기능을 사용하지 않도록 설정하려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-124">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="76045-125">자세한 내용은 [방법: 서비스에 대한 정보 로깅](../../../docs/framework/windows-services/how-to-log-information-about-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76045-125">For more information, see [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md).</span></span> <span data-ttu-id="76045-126">**참고:** 기본적으로 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A>는 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76045-126">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="76045-127"><xref:System.ServiceProcess.ServiceBase.CanStop%2A> 또는 <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>가 `false`로 설정되면 **서비스 제어 관리자**가 서비스를 중지, 일시 중지 또는 계속하도록 하는 해당 메뉴 옵션을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-127">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4.  <span data-ttu-id="76045-128">코드 편집기에 액세스하여 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 프로시저에 대해 원하는 처리를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-128">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5.  <span data-ttu-id="76045-129">기능을 정의할 다른 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-129">Override any other methods for which you want to define functionality.</span></span>  
  
6.  <span data-ttu-id="76045-130">서비스 응용 프로그램에 필요한 설치 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-130">Add the necessary installers for your service application.</span></span> <span data-ttu-id="76045-131">자세한 내용은 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)(방법: 서비스 응용 프로그램에 설치 관리자 추가)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76045-131">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
7.  <span data-ttu-id="76045-132">**빌드** 메뉴에서 **솔루션 빌드**를 선택하여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-132">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76045-133">F5 키를 눌러 프로젝트를 실행하지 마세요. 서비스 프로젝트는 이러한 방식으로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76045-133">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8.  <span data-ttu-id="76045-134">서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="76045-134">Install the service.</span></span> <span data-ttu-id="76045-135">자세한 내용은 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76045-135">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76045-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76045-136">See Also</span></span>  
 [<span data-ttu-id="76045-137">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="76045-137">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="76045-138">방법: 프로그래밍 방식으로 서비스 작성</span><span class="sxs-lookup"><span data-stu-id="76045-138">How to: Write Services Programmatically</span></span>](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)  
 [<span data-ttu-id="76045-139">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="76045-139">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="76045-140">방법: 서비스에 대한 정보 로깅</span><span class="sxs-lookup"><span data-stu-id="76045-140">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="76045-141">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="76045-141">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="76045-142">방법: 서비스에 대한 보안 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="76045-142">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)  
 [<span data-ttu-id="76045-143">방법: 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="76045-143">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="76045-144">연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="76045-144">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
