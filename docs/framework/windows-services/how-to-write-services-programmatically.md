---
title: "방법: 프로그래밍 방식으로 서비스 작성"
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
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: cdb9c7bba564b71bfba86076218e48610cf73076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="bc6ca-102">방법: 프로그래밍 방식으로 서비스 작성</span><span class="sxs-lookup"><span data-stu-id="bc6ca-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="bc6ca-103">Windows 서비스 프로젝트 템플릿을 사용 하지 않도록 선택 상속 및 기타 인프라 요소를 설정 하 여 사용자 고유의 서비스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="bc6ca-104">서비스를 프로그래밍 방식으로 만드는 경우 서식 파일을 처리할 수 있는 몇 가지 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="bc6ca-105">서비스 클래스에서 상속 하도록 설정 해야는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="bc6ca-106">만들어야는 `Main` 실행 되도록 서비스를 정의 하는 서비스 프로젝트 및 호출에 대 한 메서드는 <xref:System.ServiceProcess.ServiceBase.Run%2A> 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="bc6ca-107">재정의 해야 합니다는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 실행 되도록 할 절차와 모든 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="bc6ca-108">서비스를 프로그래밍 방식으로 작성 하려면</span><span class="sxs-lookup"><span data-stu-id="bc6ca-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="bc6ca-109">빈 프로젝트를 만들고이 단계에 따라 필요한 네임 스페이스에 대 한 참조를 만들 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="bc6ca-110">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **참조** 노드와 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="bc6ca-111">에 **.NET Framework** 탭으로 스크롤한 **System.dll** 클릭 **선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="bc6ca-112">스크롤하여 **System.ServiceProcess.dll** 클릭 **선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="bc6ca-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="bc6ca-114">클래스를 추가 하 고 구성에서 상속 하도록 <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="bc6ca-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="bc6ca-115">서비스 클래스를 구성 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="bc6ca-116">만들기는 `Main` 메서드 클래스에 대 한 클래스가 포함 됩니다; 서비스를 정의 하는 데 사용 `userService1` 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="bc6ca-117">재정의 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 다음 서비스를 시작할 때 발생 하는 모든 처리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="bc6ca-118">정의 하려는 사용자 지정 처리, 다른 메서드를 재정의 하 고 각각의 경우에는 서비스가 수행할 동작을 확인 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="bc6ca-119">서비스 응용 프로그램에 필요한 설치 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="bc6ca-120">자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="bc6ca-121">선택 하 여 프로젝트를 빌드해야 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc6ca-122">F5 키를 눌러 프로젝트를 실행하지 마세요. 서비스 프로젝트는 이러한 방식으로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="bc6ca-123">설치 프로젝트 및 서비스를 설치 하려면 사용자 지정 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="bc6ca-124">예를 들어 참조 [연습: Windows 서비스 응용 프로그램 구성 요소 디자이너에서 만드는](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="bc6ca-125">서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-125">Install the service.</span></span> <span data-ttu-id="bc6ca-126">자세한 내용은 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc6ca-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc6ca-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc6ca-127">See Also</span></span>  
 [<span data-ttu-id="bc6ca-128">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="bc6ca-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="bc6ca-129">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="bc6ca-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="bc6ca-130">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="bc6ca-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="bc6ca-131">방법: 서비스에 대한 정보 로깅</span><span class="sxs-lookup"><span data-stu-id="bc6ca-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="bc6ca-132">연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="bc6ca-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
