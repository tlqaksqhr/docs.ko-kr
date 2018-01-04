---
title: "방법: Windows 서비스 응용 프로그램 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 86d90e4129f089a77e51e6e58233a1087fe5d0f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="ba5ad-102">방법: Windows 서비스 응용 프로그램 디버깅</span><span class="sxs-lookup"><span data-stu-id="ba5ad-102">How to: Debug Windows Service Applications</span></span>
<span data-ttu-id="ba5ad-103">서비스는 Visual Studio 내에서가 아니라 서비스 제어 관리자의 컨텍스트 내에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-103">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="ba5ad-104">따라서 서비스를 디버그하는 것은 다른 Visual Studio 응용 프로그램 형식을 디버그하는 것처럼 단순하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-104">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="ba5ad-105">서비스를 디버그하려면 서비스를 시작한 다음 서비스가 실행되는 프로세스에 디버거를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-105">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="ba5ad-106">그리고 나면 Visual Studio의 모든 표준 디버깅 기능을 사용하여 응용 프로그램을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-106">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ba5ad-107">프로세스에 대해 알고 있으며 해당 프로세스에 디버거를 연결하는 경우 프로세스가 종료될 수도 있음을 이해한 상태에서 프로세스에 디버거를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-107">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="ba5ad-108">예를 들어 WinLogon 프로세스에 연결한 후에 디버깅을 중지하면 시스템이 중단됩니다. 시스템은 WinLogon 없이는 작동할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-108">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="ba5ad-109">실행 중인 서비스에만 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-109">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="ba5ad-110">연결 프로세스에서는 현재 서비스 작동이 중단되지만 서비스 처리가 실제로 중지되거나 일시 중지되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-110">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="ba5ad-111">즉, 디버깅을 시작할 때 실행 중인 서비스는 디버그할 때도 기술적으로 계속 시작됨 상태이지만 처리는 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-111">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="ba5ad-112">프로세스에 연결한 후에는 중단점을 설정하여 코드를 디버그하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-112">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="ba5ad-113">프로세스에 연결하는 데 사용한 대화 상자를 종료하면 디버그 모드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-113">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="ba5ad-114">서비스 제어 관리자를 사용하여 서비스를 시작, 중지, 일시 중지 및 계속해 설정된 중단점을 적중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-114">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="ba5ad-115">나중에 디버깅이 정상적으로 완료되면 이 더미 서비스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-115">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="ba5ad-116">이 문서에서는 로컬 컴퓨터에서 실행되는 서비스를 디버그하는 방법에 대해 다루지만, 원격 컴퓨터에서 실행되는 Windows 서비스도 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-116">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="ba5ad-117">참조 [원격 디버깅](/visualstudio/debugger/debug-installed-app-package)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-117">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba5ad-118">서비스 제어 관리자는 모든 서비스 시작 시도에 대해 30초의 제한을 적용하므로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 디버그하는 작업은 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-118">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="ba5ad-119">자세한 내용은 참조 [문제 해결: Windows 서비스 디버깅](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-119">For more information, see [Troubleshooting: Debugging Windows Services](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ba5ad-120">디버깅을 위한 의미 있는 정보를 가져오려면 Visual Studio 디버거가 디버그 중인 이진 파일에 대한 기호 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-120">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="ba5ad-121">Visual Studio에서 빌드한 서비스를 디버그하는 경우 기호 파일(.pdb 파일)은 실행 파일이나 라이브러리와 같은 폴더에 있으며 디버거는 이러한 파일을 자동으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-121">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="ba5ad-122">직접 빌드하지 않은 서비스를 디버그할 때는 먼저 서비스의 기호를 찾아 디버거가 해당 기호를 검색할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-122">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="ba5ad-123">참조 [기호 (.pdb)을 지정 하 고 소스 파일과](http://msdn.microsoft.com/library/1105e169-5272-4e7c-b3e7-cda1b7798a6b)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-123">See [Specify Symbol (.pdb) and Source Files](http://msdn.microsoft.com/library/1105e169-5272-4e7c-b3e7-cda1b7798a6b).</span></span> <span data-ttu-id="ba5ad-124">시스템 프로세스를 디버그하거나 서비스에 시스템 호출을 위한 기호를 포함하려는 경우에는 Microsoft 기호 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-124">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="ba5ad-125">참조 [디버깅 기호가](http://msdn.microsoft.com/windows/desktop/ee416588.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-125">See [Debugging Symbols](http://msdn.microsoft.com/windows/desktop/ee416588.aspx).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="ba5ad-126">서비스를 디버깅하려면</span><span class="sxs-lookup"><span data-stu-id="ba5ad-126">To debug a service</span></span>  
  
1.  <span data-ttu-id="ba5ad-127">디버그 구성에서 서비스를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-127">Build your service in the Debug configuration.</span></span>  
  
2.  <span data-ttu-id="ba5ad-128">서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-128">Install your service.</span></span> <span data-ttu-id="ba5ad-129">자세한 내용은 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-129">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
3.  <span data-ttu-id="ba5ad-130">서비스를 시작 **서비스 제어 관리자**, **서버 탐색기**, 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-130">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="ba5ad-131">자세한 내용은 참조 [하는 방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-131">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>  
  
4.  <span data-ttu-id="ba5ad-132">시스템 프로세스에 연결할 수 있도록 관리 자격 증명을 사용하여 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-132">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5.  <span data-ttu-id="ba5ad-133">(선택 사항) Visual Studio 메뉴 모음에서 **도구**, **옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-133">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="ba5ad-134">에 **옵션** 대화 상자에서 선택 **디버깅**, **기호**을 선택는 **Microsoft 기호 서버** 확인란을 선택한 후는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-134">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="ba5ad-135">메뉴 모음에서 **프로세스에 연결** 에서 **디버그** 또는 **도구** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-135">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="ba5ad-136">선택합니다(키보드: Ctrl+Alt+P).</span><span class="sxs-lookup"><span data-stu-id="ba5ad-136">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="ba5ad-137">**프로세스** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-137">The **Processes** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="ba5ad-138">선택 된 **모든 사용자의 프로세스 표시** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-138">Select the **Show processes from all users** check box.</span></span>  
  
8.  <span data-ttu-id="ba5ad-139">에 **사용 가능한 프로세스** 섹션, 서비스에 대 한 프로세스를 선택 하 고, 선택 **연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-139">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="ba5ad-140">프로세스의 이름은 서비스의 실행 파일 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-140">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="ba5ad-141">**프로세스에 연결** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-141">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="ba5ad-142">적절 한 옵션을 선택한 다음 선택 **확인** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-142">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba5ad-143">이제 디버그 모드가 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-143">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="ba5ad-144">코드에서 사용할 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-144">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="ba5ad-145">서비스 제어 관리자에 액세스하고 서비스를 조작하여 중단점을 적중하는 중지, 일시 중지 및 계속 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-145">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="ba5ad-146">서비스 제어 관리자를 실행 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-146">For more information about running the Services Control Manager, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span> <span data-ttu-id="ba5ad-147">참고: [문제 해결: Windows 서비스 디버깅](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-147">Also, see [Troubleshooting: Debugging Windows Services](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="ba5ad-148">Windows 서비스 디버깅 팁</span><span class="sxs-lookup"><span data-stu-id="ba5ad-148">Debugging Tips for Windows Services</span></span>  
 <span data-ttu-id="ba5ad-149">서비스의 프로세스에 연결하면 해당 서비스의 코드를 대부분 디버그할 수 있지만 모든 코드를 디버그할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-149">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="ba5ad-150">예를 들어 서비스가 이미 시작되었기 때문에 이러한 방식으로 서비스를 로드하는 데 사용되는 서비스의 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드 내 코드나 `Main` 메서드 내의 코드는 디버그할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-150">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="ba5ad-151">이 제한을 해결하는 한 가지 방법은 디버그에만 사용되는 두 번째 임시 서비스를 서비스 응용 프로그램에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-151">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="ba5ad-152">두 서비스를 모두 설치하고서 이 더미 서비스를 시작하여 서비스 프로세스를 로드할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-152">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="ba5ad-153">임시 서비스가 프로세스를 시작 하 고, 사용할 수 있습니다는 **디버그** 서비스 프로세스에 연결 하려면 Visual Studio에서 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-153">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="ba5ad-154">프로세스에 연결할 수 있을 때까지 <xref:System.Threading.Thread.Sleep%2A> 메서드에 대한 호출을 추가하여 작업을 지연시켜 봅니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-154">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="ba5ad-155">프로그램을 일반 콘솔 응용 프로그램으로 변경해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-155">Try changing the program to a regular console application.</span></span> <span data-ttu-id="ba5ad-156">이렇게 하려면 `Main` 메서드를 시작하는 방법에 따라 Windows 서비스와 콘솔 응용 프로그램 둘 다로 실행할 수 있도록 다음과 같이 다시 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-156">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="ba5ad-157">방법: 콘솔 응용 프로그램으로 Windows 서비스 실행</span><span class="sxs-lookup"><span data-stu-id="ba5ad-157">How to: Run a Windows Service as a console application</span></span>  
  
1.  <span data-ttu-id="ba5ad-158"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드를 실행하는 서비스에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-158">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2.  <span data-ttu-id="ba5ad-159">`Main` 메서드를 다음과 같이 다시 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-159">Rewrite the `Main` method as follows:</span></span>  
  
    ```  
    static void Main(string[] args)  
            {  
                if (Environment.UserInteractive)  
                {  
                    MyNewService service1 = new MyNewService(args);  
                    service1.TestStartupAndStop(args);  
                }  
                else  
                {  
                    // Put the body of your old Main method here.  
                }  
    ```  
  
3.  <span data-ttu-id="ba5ad-160">에 **응용 프로그램** 프로젝트의 속성의 탭 설정에서 **출력 형식이** 를 **콘솔 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-160">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4.  <span data-ttu-id="ba5ad-161">선택 **디버깅을 시작** (F5).</span><span class="sxs-lookup"><span data-stu-id="ba5ad-161">Choose **Start Debugging** (F5).</span></span>  
  
5.  <span data-ttu-id="ba5ad-162">프로그램을 Windows 서비스로 다시 실행하려면 해당 프로그램을 설치하고 Windows 서비스를 시작하는 일반적인 방법으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-162">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="ba5ad-163">이러한 변경 내용을 되돌릴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-163">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="ba5ad-164">시스템 시작 시에만 발생하는 문제를 디버그하려는 등의 일부 경우에는 Windows 디버거를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-164">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="ba5ad-165">설치 [Windows 용 디버깅 도구](http://msdn.microsoft.com/windows/hardware/hh852365) 참조 및 [Windows 서비스를 디버그 하는 방법을](http://support.microsoft.com/kb/824344)합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-165">Install [Debugging Tools for Windows](http://msdn.microsoft.com/windows/hardware/hh852365) and see [How to debug Windows Services](http://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba5ad-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba5ad-166">See Also</span></span>  
 [<span data-ttu-id="ba5ad-167">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="ba5ad-167">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="ba5ad-168">방법: 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="ba5ad-168">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="ba5ad-169">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="ba5ad-169">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="ba5ad-170">서비스 디버깅</span><span class="sxs-lookup"><span data-stu-id="ba5ad-170">Debugging a Service</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms682546.aspx)
