---
title: '방법: 서비스 시작'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: 16
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 47e27f579c0ed7d1be0b061bc6e79bba0c060abb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-start-services"></a><span data-ttu-id="18c79-102">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="18c79-102">How to: Start Services</span></span>
<span data-ttu-id="18c79-103">서비스를 설치한 후에 시작 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="18c79-104">호출을 시작는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 서비스 클래스에 메서드.</span><span class="sxs-lookup"><span data-stu-id="18c79-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="18c79-105">일반적으로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드는 서비스에서 수행할 유용한 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="18c79-106">서비스 시작 후 수동으로 일시 중지 또는 중지 될 때까지 활성 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="18c79-107">자동 또는 수동으로 시작 하려면 서비스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="18c79-108">자동으로 시작 하는 서비스는 설치 된 컴퓨터를 다시 부팅 하거나 처음 켤 때 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="18c79-109">사용자는 수동으로 시작 하는 서비스를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18c79-110">기본적으로 Visual Studio를 사용 하 여 만든 서비스를 수동으로 시작 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-110">By default, services created with Visual Studio are set to start manually.</span></span>  
  
 <span data-ttu-id="18c79-111">여러 가지 방법으로 서비스를 수동으로 시작할 수 있습니다-에서 **서버 탐색기**에서 **서비스 제어 관리자**, 라는 구성 요소를 사용 하 여 코드에서 또는 <xref:System.ServiceProcess.ServiceController>합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="18c79-112">설정한는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성에는 <xref:System.ServiceProcess.ServiceInstaller> 수동 또는 자동으로 서비스가 다시 시작 해야 하는지 여부를 결정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="18c79-113">서비스 시작 방법을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="18c79-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="18c79-114">서비스를 만든 후에 필요한 설치 관리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="18c79-115">자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="18c79-116">디자이너를 사용 하는 서비스에 대 한 서비스 설치 관리자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="18c79-117">에 **속성** 창에서 설정 된 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 다음 중 하나:</span><span class="sxs-lookup"><span data-stu-id="18c79-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="18c79-118">서비스를 설치 하도록 하는</span><span class="sxs-lookup"><span data-stu-id="18c79-118">To have your service install</span></span>|<span data-ttu-id="18c79-119">이 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="18c79-120">컴퓨터 다시 시작 되 면</span><span class="sxs-lookup"><span data-stu-id="18c79-120">When the computer is restarted</span></span>|<span data-ttu-id="18c79-121">**자동**</span><span class="sxs-lookup"><span data-stu-id="18c79-121">**Automatic**</span></span>|  
    |<span data-ttu-id="18c79-122">명시적 사용자 동작에서 서비스를 시작 하는 경우</span><span class="sxs-lookup"><span data-stu-id="18c79-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="18c79-123">**수동**</span><span class="sxs-lookup"><span data-stu-id="18c79-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="18c79-124">서비스에서 시작 되는 것을 방지 하려면 설정할 수 있습니다는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 **비활성화**합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="18c79-125">서버를 여러 번 다시 부팅을 시작 정상적으로 시작 하는 서비스를 방지 하 여 시간 절약을 위해 하려는 경우 이렇게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18c79-126">서비스를 설치한 후 이러한 오류 코드 및 기타 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="18c79-127">여러 가지 방법으로 서비스를 시작할 수는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 프로세스로 설정 **수동** -에서 **서버 탐색기**에서 **Windows 서비스 제어 관리자**, 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="18c79-128">이러한 메서드의 일부 실제로 시작 서비스의 컨텍스트에서 해야는 **서비스 제어 관리자**; **서버 탐색기** 및 서비스를 시작 하는 프로그래밍 방법도 실제로 컨트롤러를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="18c79-129">서버 탐색기에서 서비스를 수동으로 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="18c79-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="18c79-130">**서버 탐색기**, 표시 되어 있지 않으면 하는 경우 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="18c79-131">자세한 내용은 참조 하는 방법: 액세스 및 서버 탐색기 데이터베이스 탐색기를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="18c79-132">확장 된 **서비스** 노드를 한 다음 시작 하려면 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="18c79-133">서비스의 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="18c79-134">서비스 제어 관리자에서 서비스를 수동으로 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="18c79-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="18c79-135">열기는 **서비스 제어 관리자** 다음 중 하나를 수행 하 여:</span><span class="sxs-lookup"><span data-stu-id="18c79-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="18c79-136">Windows XP 및 2000 Professional에서 마우스 오른쪽 단추로 클릭 **내 컴퓨터** 바탕 화면, 클릭 한 다음에 **관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="18c79-137">표시 되는 대화 상자에서 확장 된 **서비스 및 응용 프로그램** 노드.</span><span class="sxs-lookup"><span data-stu-id="18c79-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="18c79-138">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="18c79-138">\- or -</span></span>  
  
    -   <span data-ttu-id="18c79-139">Windows Server 2003 및 Windows 2000 Server에서 클릭 **시작**, 가리킨 **프로그램**, 클릭 **관리 도구**, 클릭 하 고 **서비스**.</span><span class="sxs-lookup"><span data-stu-id="18c79-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="18c79-140">Windows nt 버전 4.0에서이 대화 상자를 열 수 있습니다 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="18c79-141">에 서비스 목록이 표시 됩니다는 **서비스** 창의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="18c79-142">목록에서 서비스를 선택 하 고 마우스 오른쪽 단추로 클릭 한 다음 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="18c79-143">코드에서 서비스를 수동으로 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="18c79-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="18c79-144">인스턴스를 만들고는 <xref:System.ServiceProcess.ServiceController> 클래스를 관리 하려면 서비스와 상호 작용 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="18c79-145"><xref:System.ServiceProcess.ServiceController.Start%2A> 메서드를 호출하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="18c79-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c79-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18c79-146">See Also</span></span>  
 [<span data-ttu-id="18c79-147">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="18c79-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="18c79-148">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="18c79-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="18c79-149">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="18c79-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
