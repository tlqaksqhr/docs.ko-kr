---
title: "서비스 응용 프로그램 프로그래밍 아키텍처"
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
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="8a2bd-102">서비스 응용 프로그램 프로그래밍 아키텍처</span><span class="sxs-lookup"><span data-stu-id="8a2bd-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="8a2bd-103">상속 되는 클래스를 기반으로 하는 Windows 서비스 응용 프로그램은 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8a2bd-104">이 클래스에서 메서드를 재정의 하 고이 정보를 서비스의 작동 방식을 결정할 수에 대 한 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="8a2bd-105">서비스 만들기에 관련 된 기본 클래스는입니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="8a2bd-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>— 메서드를 재정의할이 작업은 <xref:System.ServiceProcess.ServiceBase> 서비스를 만들 때 클래스와이 서비스 함수 클래스를 상속 하는 방법을 결정 하는 코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="8a2bd-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>및 <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> -이러한 클래스를 사용 하 여 설치 하 고 서비스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="8a2bd-108">또한 라는 클래스 <xref:System.ServiceProcess.ServiceController> 는 서비스 자체를 조작 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="8a2bd-109">이 클래스는 서비스 만들기에 관련 된 않으며 시작 하 고 서비스를 중지 하 고에 명령을 전달 하 고 일련의 열거형을 반환 하는 데 사용 될입니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="8a2bd-110">서비스의 동작 정의</span><span class="sxs-lookup"><span data-stu-id="8a2bd-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="8a2bd-111">서비스 클래스에서 서비스의 상태 서비스 제어 관리자에서 변경 될 때 수행 되는 기본 클래스 함수를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="8a2bd-112"><xref:System.ServiceProcess.ServiceBase> 클래스 사용자 지정 동작을 추가 하기 위해 재정의할 수 있는 다음과 같은 메서드를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="8a2bd-113">메서드</span><span class="sxs-lookup"><span data-stu-id="8a2bd-113">Method</span></span>|<span data-ttu-id="8a2bd-114">재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="8a2bd-115">서비스가 실행을 시작할 때 어떤 작업을 수행 해야 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="8a2bd-116">유용한 작업을 수행 하려면 해당 서비스에 대해이 절차의 코드를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="8a2bd-117">서비스 일시 중지 될 때 수행할 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="8a2bd-118">서비스가 중지 된 경우 수행할 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="8a2bd-119">서비스 일시 중지 된 후 일반 기능을 다시 시작 될 때 수행할 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="8a2bd-120">서비스가 해당 시점에 실행 중인 경우 시스템이, 종료 하기 전에 수행할 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="8a2bd-121">서비스 사용자 지정 명령을 수신할 때 수행할 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="8a2bd-122">사용자 지정 명령에 대 한 자세한 내용은 온라인 MSDN 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="8a2bd-123">배터리 부족 또는 일시 중단 된 작업과 같이 전원 관리 이벤트가 수신 되 면 서비스가 해야 응답 하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8a2bd-124">이러한 메서드는 서비스의 수명이;를 통해 이동 하는 상태를 나타내는 다음 한 상태에서 서비스 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="8a2bd-125">예를 들어는 가져올 수 없습니다에 응답 하는 서비스는 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 하기 전에 명령을 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 가 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="8a2bd-126">다른 여러 속성 및 관심 있는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="8a2bd-127">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-127">These include:</span></span>  
  
-   <span data-ttu-id="8a2bd-128"><xref:System.ServiceProcess.ServiceBase.Run%2A> 에서 메서드는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="8a2bd-129">이 서비스에 대 한 주 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-129">This is the main entry point for the service.</span></span> <span data-ttu-id="8a2bd-130">Windows 서비스 템플릿을 사용 하 여 서비스를 만들면 응용 프로그램의 코드가 삽입 됩니다 `Main` 서비스를 실행 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="8a2bd-131">이 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="8a2bd-132">이 예에서는 형식의 배열을 사용 하 여 <xref:System.ServiceProcess.ServiceBase>, 응용 프로그램을 포함 하는 각 서비스를 추가할 수 있습니다 및 된 다음 모든 서비스 수를 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="8a2bd-133">그러나만 단일 서비스를 만드는 경우 선택할 수 있습니다는 배열을 사용를 단순히에서 상속 하는 새 개체를 선언 하는 <xref:System.ServiceProcess.ServiceBase> 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="8a2bd-134">예를 들어 참조 [하는 방법: 프로그래밍 방식으로 서비스 작성](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="8a2bd-135">일련의 속성에는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="8a2bd-136">이러한 서비스에서 어떤 메서드를 호출할 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="8a2bd-137">예를 들어는 <xref:System.ServiceProcess.ServiceBase.CanStop%2A> 속성이로 설정 되어 `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 서비스에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="8a2bd-138">때는 <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> 속성이 `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="8a2bd-139">이러한 속성을 설정 하면 `true`, 그런 다음 재정의 하 고 연결된 된 메서드에 대 한 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a2bd-140">이상 서비스를 재정의 해야 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 유용 하 게 되려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="8a2bd-141">라는 구성 요소를 사용할 수도 있습니다는 <xref:System.ServiceProcess.ServiceController> 와 통신 하 고 기존 서비스의 동작을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2bd-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2bd-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a2bd-142">See Also</span></span>  
 [<span data-ttu-id="8a2bd-143">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="8a2bd-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="8a2bd-144">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="8a2bd-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
