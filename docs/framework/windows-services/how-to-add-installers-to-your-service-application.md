---
title: "방법: 서비스 응용 프로그램에 설치 관리자 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 15487d4311f896aa09c1c7712292058086a49b50
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="5e0ee-102">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="5e0ee-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="5e0ee-103">Visual Studio 리소스에 연결 된 서비스 응용 프로그램을 설치할 수 있는 설치 구성 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="5e0ee-104">설치 구성 요소는 시스템을 설치 하는 것와를 서비스가 존재 하는지 확인 하 여 서비스 제어 관리자에서 개별 서비스를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="5e0ee-105">서비스 응용 프로그램을 사용할 때 자동으로 프로젝트에 적절 한 설치 관리자를 추가 하려면 속성 창에서 링크를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e0ee-106">서비스에 대 한 속성 값은 설치 관리자 클래스에는 서비스 클래스에서 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="5e0ee-107">서비스 클래스에서 속성 값을 업데이트 하는 경우 설치 관리자에서 자동으로 업데이트 되는 것은 되지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="5e0ee-108">프로젝트는 새 클래스에는 설치 관리자를 추가 하면 (, 기본적으로 라는 `ProjectInstaller`) 프로젝트 및 구성 요소에 만들어집니다. 해당 설치의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="5e0ee-109">프로젝트에 필요한이 클래스 역할의 모든 설치 구성 요소에 대 한 중심점.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="5e0ee-110">예를 들어 두 번째 서비스 응용 프로그램에 추가 하 고 설치 관리자 추가 링크를 클릭 하는 경우 두 번째 설치 관리자 클래스 만들어지지 않습니다. 대신, 두 번째 서비스에 대 한 필요한 추가 설치 구성 요소는 기존 클래스에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="5e0ee-111">서비스를 제대로 설치 되도록 설치 관리자 내에서 특별 한 코딩이 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="5e0ee-112">그러나 설치 프로세스에 특별 한 기능을 추가 해야 할 경우 설치 관리자의 내용을 수정 해야 경우에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e0ee-113">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5e0ee-114">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5e0ee-115">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="5e0ee-116">서비스 응용 프로그램에 설치 관리자를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="5e0ee-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="5e0ee-117">**솔루션 탐색기**, 액세스 **디자인** 설치 구성 요소를 추가 하려는 서비스에 대 한 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="5e0ee-118">자체 보다는 내용이 서비스를 선택 하려면 디자이너의 배경을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="5e0ee-119">포커스 마우스 오른쪽 단추로 클릭 한 다음 디자이너와 **설치 관리자 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="5e0ee-120">새 클래스를 `ProjectInstaller`, 두 가지 설치 구성 요소 및 <xref:System.ServiceProcess.ServiceProcessInstaller> 및 <xref:System.ServiceProcess.ServiceInstaller>, 구성 요소에 복사 되는 서비스에 대 한 프로젝트 및 속성 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="5e0ee-121">클릭는 <xref:System.ServiceProcess.ServiceInstaller> 구성 요소 확인 값은 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성이 동일한 값으로 설정 되어는 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 서비스 자체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="5e0ee-122">서비스는 시작 하는 방법을 확인 하려면는 <xref:System.ServiceProcess.ServiceInstaller> 설정 및 구성 요소는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="5e0ee-123">값</span><span class="sxs-lookup"><span data-stu-id="5e0ee-123">Value</span></span>|<span data-ttu-id="5e0ee-124">결과</span><span class="sxs-lookup"><span data-stu-id="5e0ee-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="5e0ee-125">설치 후 서비스를 수동으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-125">The service must be manually started after installation.</span></span> <span data-ttu-id="5e0ee-126">자세한 내용은 참조 [하는 방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="5e0ee-127">서비스는 컴퓨터가 재부팅 될 때마다 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="5e0ee-128">서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="5e0ee-129">프로그램 서비스가 실행 되는 보안 컨텍스트를 확인 하려면 클릭는 <xref:System.ServiceProcess.ServiceProcessInstaller> 구성 요소 및 해당 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="5e0ee-130">자세한 내용은 참조 [하는 방법: 서비스에 대 한 보안 컨텍스트 지정](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="5e0ee-131">사용자 지정 처리를 수행 해야 하는 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="5e0ee-132">프로젝트의 각 추가 서비스에 대해 1-7 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e0ee-133">프로젝트의 각 추가 서비스를 추가 해야 추가 <xref:System.ServiceProcess.ServiceInstaller> 프로젝트의 구성 요소 `ProjectInstaller` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="5e0ee-134"><xref:System.ServiceProcess.ServiceProcessInstaller> 모든 프로젝트에 있는 개별 서비스 설치 관리자와 3 단계에서 추가 하는 구성 요소의 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0ee-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0ee-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e0ee-135">See Also</span></span>  
 [<span data-ttu-id="5e0ee-136">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="5e0ee-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="5e0ee-137">방법: 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="5e0ee-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="5e0ee-138">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="5e0ee-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="5e0ee-139">방법: 서비스에 대한 보안 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="5e0ee-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
