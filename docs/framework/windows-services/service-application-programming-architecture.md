---
title: 서비스 응용 프로그램 프로그래밍 아키텍처
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
author: ghogen
manager: douge
ms.openlocfilehash: f0c760d0f9b65fc9b612a8bee8abb68fa5b4ecae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516109"
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="929cf-102">서비스 응용 프로그램 프로그래밍 아키텍처</span><span class="sxs-lookup"><span data-stu-id="929cf-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="929cf-103">Windows 서비스 응용 프로그램은 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 클래스에서 상속되는 클래스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="929cf-104">이 클래스의 메서드를 재정의하고 이 메서드에서 서비스 동작 방식을 결정하는 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="929cf-105">서비스 만들기와 관련된 기본 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="929cf-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> - 서비스를 만들 때 <xref:System.ServiceProcess.ServiceBase> 클래스의 메서드를 재정의하고 이 상속된 클래스에서 서비스가 작동하는 방식을 결정하는 코드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="929cf-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> 및 <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> - 이러한 클래스를 사용하여 서비스를 설치 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="929cf-108">또한 <xref:System.ServiceProcess.ServiceController>라는 클래스를 사용하여 서비스 자체를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="929cf-109">이 클래스는 서비스 만들기와는 관련이 없지만 서비스를 시작 및 중지하고 서비스에 명령을 전달하고 일련의 열거형을 반환하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="929cf-110">서비스 동작 정의</span><span class="sxs-lookup"><span data-stu-id="929cf-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="929cf-111">서비스 클래스에서 기본 클래스 함수를 재정의하여 서비스 제어 관리자에서 서비스 상태를 변경하는 경우 어떤 작업을 수행할지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="929cf-112"><xref:System.ServiceProcess.ServiceBase> 클래스는 다음과 같은 메서드를 노출하며, 이들 메서드를 재정의하여 사용자 지정 동작을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="929cf-113">메서드</span><span class="sxs-lookup"><span data-stu-id="929cf-113">Method</span></span>|<span data-ttu-id="929cf-114">재정의 목적</span><span class="sxs-lookup"><span data-stu-id="929cf-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="929cf-115">서비스 실행이 시작될 때 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="929cf-116">서비스가 유용한 작업을 수행하려면 이 프로시저에 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="929cf-117">서비스가 일시 중지될 경우 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="929cf-118">서비스 실행이 중지될 경우 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="929cf-119">서비스가 일시 중지되었다가 정상 작동을 재개할 경우 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="929cf-120">서비스가 실행 중일 때 시스템이 종료될 경우 종료 직전에 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="929cf-121">서비스가 사용자 지정 명령을 받을 경우 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="929cf-122">사용자 지정 명령에 대한 자세한 내용은 MSDN Online을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="929cf-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="929cf-123">배터리 부족 또는 일시 중단된 작업과 같은 전원 관리 이벤트가 수신될 경우 서비스가 응답할 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="929cf-124">이러한 메서드는 서비스가 수명 동안 진행되는 상태를 나타냅니다. 즉, 서비스는 한 상태에서 다음 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="929cf-125">예를 들어 <xref:System.ServiceProcess.ServiceBase.OnStart%2A>가 호출되기 전에는 서비스가 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 명령에 응답하도록 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="929cf-126">중요한 여러 다른 속성 및 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="929cf-127">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-127">These include:</span></span>  
  
-   <span data-ttu-id="929cf-128"><xref:System.ServiceProcess.ServiceBase> 클래스의 <xref:System.ServiceProcess.ServiceBase.Run%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="929cf-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="929cf-129">서비스의 주 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-129">This is the main entry point for the service.</span></span> <span data-ttu-id="929cf-130">Windows 서비스 템플릿을 사용하여 서비스를 만드는 경우 응용 프로그램의 `Main` 메서드에 코드를 삽입하여 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="929cf-131">이 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="929cf-132">이러한 예제에서는 <xref:System.ServiceProcess.ServiceBase> 형식의 배열을 사용합니다. 이 배열에 응용 프로그램에 포함되는 각 서비스를 추가한 다음, 모든 서비스를 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="929cf-133">하지만 단일 서비스만 만드는 경우에는 배열을 사용하지 않고 <xref:System.ServiceProcess.ServiceBase>에서 상속되는 새 개체를 선언하고 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="929cf-134">예제는 [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)(방법: 프로그래밍 방식으로 서비스 작성)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="929cf-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="929cf-135"><xref:System.ServiceProcess.ServiceBase> 클래스에 대한 일련의 속성.</span><span class="sxs-lookup"><span data-stu-id="929cf-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="929cf-136">이러한 속성은 서비스에서 호출할 수 있는 메서드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="929cf-137">예를 들어 <xref:System.ServiceProcess.ServiceBase.CanStop%2A> 속성을 `true`로 설정하면 서비스의 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="929cf-138"><xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> 속성을 `true`로 설정하면 <xref:System.ServiceProcess.ServiceBase.OnPause%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="929cf-139">이러한 속성 중 하나를 `true`로 설정하는 경우 관련 메서드에 대한 처리를 재정의 및 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="929cf-140">서비스가 유용하려면 적어도 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A>을 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="929cf-141"><xref:System.ServiceProcess.ServiceController>라는 구성 요소를 사용하여 기존 서비스와 통신하고 서비스의 동작을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929cf-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929cf-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="929cf-142">See Also</span></span>  
 [<span data-ttu-id="929cf-143">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="929cf-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="929cf-144">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="929cf-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
