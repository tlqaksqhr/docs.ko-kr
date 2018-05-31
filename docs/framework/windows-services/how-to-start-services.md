---
title: '방법: 서비스 시작'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
manager: douge
ms.openlocfilehash: 3c8382d2e425d11dc8aa8b22e361b3cc5637744f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516219"
---
# <a name="how-to-start-services"></a><span data-ttu-id="8e901-102">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="8e901-102">How to: Start Services</span></span>
<span data-ttu-id="8e901-103">서비스가 설치되면 서비스를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="8e901-104">시작하면 서비스 클래스의 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="8e901-105">일반적으로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드는 서비스가 수행할 유용한 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="8e901-106">시작된 후 서비스는 수동으로 일시 중지하거나 중지할 때까지 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="8e901-107">자동 또는 수동으로 시작하도록 서비스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="8e901-108">자동으로 시작하는 서비스는 설치된 컴퓨터가 재부팅되거나 처음으로 켜질 때 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="8e901-109">수동으로 시작하는 서비스는 사용자가 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e901-110">기본적으로 Visual Studio에서 만드는 서비스는 수동으로 시작하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-110">By default, services created with Visual Studio are set to start manually.</span></span>  
  
 <span data-ttu-id="8e901-111">서비스를 수동으로 시작할 수 있는 방법은 **서버 탐색기**나 **서비스 제어 관리자**에서 시작하거나 <xref:System.ServiceProcess.ServiceController>라는 구성 요소를 사용하는 코드에서 시작하는 등 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="8e901-112"><xref:System.ServiceProcess.ServiceInstaller> 클래스의 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 설정하여 서비스를 수동으로 시작할지 자동으로 시작할지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="8e901-113">서비스 시작 방식을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="8e901-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="8e901-114">서비스를 만든 후 서비스에 필요한 설치 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="8e901-115">자세한 내용은 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)(방법: 서비스 응용 프로그램에 설치 관리자 추가)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e901-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="8e901-116">디자이너에서 작업 중인 서비스에 대한 서비스 설치 관리자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="8e901-117">**속성** 창에서 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 다음 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="8e901-118">서비스 설치 시기</span><span class="sxs-lookup"><span data-stu-id="8e901-118">To have your service install</span></span>|<span data-ttu-id="8e901-119">설정 값</span><span class="sxs-lookup"><span data-stu-id="8e901-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="8e901-120">컴퓨터가 다시 시작될 때</span><span class="sxs-lookup"><span data-stu-id="8e901-120">When the computer is restarted</span></span>|<span data-ttu-id="8e901-121">**자동**</span><span class="sxs-lookup"><span data-stu-id="8e901-121">**Automatic**</span></span>|  
    |<span data-ttu-id="8e901-122">명시적 사용자 작업으로 서비스가 시작될 때</span><span class="sxs-lookup"><span data-stu-id="8e901-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="8e901-123">**수동**</span><span class="sxs-lookup"><span data-stu-id="8e901-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="8e901-124">서비스가 시작되지 않게 하려면 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 **사용 안 함**으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="8e901-125">서버를 여러 번 재부팅할 경우 이렇게 설정하면 통상 시작되는 서비스가 시작되지 않도록 하여 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e901-126">이러한 속성과 기타 속성을 서비스가 설치된 후 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="8e901-127"><xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 프로세스가 **수동**으로 설정된 서비스를 시작하는 방법은 **서버 탐색기**, **Windows 서비스 제어 관리자**, 코드 등 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="8e901-128">이러한 방법 중 일부는 실제로 **서비스 제어 관리자**의 컨텍스트에서 서비스를 시작하지 않습니다. **서버 탐색기** 및 서비스를 시작하는 프로그래밍 방법은 실제로 컨트롤러를 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="8e901-129">서버 탐색기에서 서비스를 수종으로 시작하려면</span><span class="sxs-lookup"><span data-stu-id="8e901-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="8e901-130">**서버 탐색기**에서 원하는 서버가 아직 나열되지 않는 경우 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="8e901-131">자세한 내용은 방법: 서버 탐색기-데이터베이스 탐색기 액세스 및 초기화를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e901-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="8e901-132">**서비스** 노드를 확장한 다음 시작할 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="8e901-133">서비스 이름을 마우스 오른쪽 단추로 클릭하고 **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="8e901-134">서비스 제어 관리자에서 서비스를 수동으로 시작하려면</span><span class="sxs-lookup"><span data-stu-id="8e901-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="8e901-135">다음 중 하나를 수행하여 **서비스 제어 관리자**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="8e901-136">Windows XP 및 2000 Professional의 경우 바탕 화면에서 **내 컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음, **관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="8e901-137">대화 상자가 나타나면 **서비스 및 응용 프로그램** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="8e901-138">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="8e901-138">\- or -</span></span>  
  
    -   <span data-ttu-id="8e901-139">Windows Server 2003 및 Windows 2000 Server에서 **시작**을 클릭하여 **프로그램**을 가리키고 **관리 도구**를 클릭한 다음, **서비스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="8e901-140">Windows NT 버전 4.0의 경우 **제어판**에서 이 대화 상자를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="8e901-141">이제 창의 **서비스** 섹션에 서비스가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="8e901-142">목록에서 서비스를 선택하고 마우스 오른쪽 단추로 클릭한 다음, **시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="8e901-143">코드에서 서비스를 수동으로 시작하려면</span><span class="sxs-lookup"><span data-stu-id="8e901-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="8e901-144"><xref:System.ServiceProcess.ServiceController> 클래스의 인스턴스를 만들고 관리할 서비스와 상호 작용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="8e901-145"><xref:System.ServiceProcess.ServiceController.Start%2A> 메서드를 호출하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8e901-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e901-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e901-146">See Also</span></span>  
 [<span data-ttu-id="8e901-147">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="8e901-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="8e901-148">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="8e901-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="8e901-149">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="8e901-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
