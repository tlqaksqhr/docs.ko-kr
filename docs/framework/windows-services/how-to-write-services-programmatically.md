---
title: '방법: 프로그래밍 방식으로 서비스 작성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
manager: douge
ms.openlocfilehash: 99fd44723bba21127e2a5e0ba3e9bfc4b90b52d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513288"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="70042-102">방법: 프로그래밍 방식으로 서비스 작성</span><span class="sxs-lookup"><span data-stu-id="70042-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="70042-103">Windows 서비스 프로젝트 템플릿을 사용하지 않으려는 경우 상속 및 기타 인프라 요소를 직접 설정하여 고유한 서비스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70042-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="70042-104">서비스를 프로그래밍 방식으로 만드는 경우 템플릿을 사용할 경우 자동으로 처리되는 다음과 같은 여러 단계를 직접 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="70042-105"><xref:System.ServiceProcess.ServiceBase> 클래스에서 상속하도록 서비스 클래스를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="70042-106">서비스 프로젝트에 대한 `Main` 메서드를 만들어야 합니다. 이 메서드는 실행할 서비스를 정의하고 해당 서비스에 대해 <xref:System.ServiceProcess.ServiceBase.Run%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="70042-107"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 프로시저를 재정의하고 이들 프로시저에서 실행할 코드를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="70042-108">서비스를 프로그래밍 방식으로 작성하려면</span><span class="sxs-lookup"><span data-stu-id="70042-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="70042-109">빈 프로젝트를 만들고 다음 단계에 따라 필요한 네임스페이스에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70042-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="70042-110">**솔루션 탐색기**에서 **참조** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="70042-111">**.NET Framework** 탭에서 **System.dll**로 스크롤하고 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="70042-112">**System.ServiceProcess.dll**로 스크롤하고 **선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="70042-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="70042-114">클래스를 추가하고 <xref:System.ServiceProcess.ServiceBase>에서 상속하도록 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="70042-115">다음 코드를 추가하여 서비스 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="70042-116">클래스에 대한 `Main` 메서드를 만들고 이 메서드를 사용하여 클래스에 포함할 서비스를 정의합니다. 여기서 `userService1`은 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70042-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="70042-117"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 재정의하고 서비스가 시작될 때 수행할 처리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="70042-118">사용자 지정 처리를 정의할 다른 메서드를 재정의하고 각 경우에 서비스가 수행할 작업을 결정하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="70042-119">서비스 응용 프로그램에 필요한 설치 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="70042-120">자세한 내용은 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)(방법: 서비스 응용 프로그램에 설치 관리자 추가)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70042-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="70042-121">**빌드** 메뉴에서 **솔루션 빌드**를 선택하여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70042-122">F5 키를 눌러 프로젝트를 실행하지 마세요. 서비스 프로젝트는 이러한 방식으로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70042-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="70042-123">설치 프로젝트와 서비스를 설치하는 사용자 지정 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70042-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="70042-124">예제는 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)(연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70042-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="70042-125">서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70042-125">Install the service.</span></span> <span data-ttu-id="70042-126">자세한 내용은 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70042-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70042-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70042-127">See Also</span></span>  
 [<span data-ttu-id="70042-128">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="70042-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="70042-129">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="70042-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="70042-130">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="70042-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="70042-131">방법: 서비스에 대한 정보 로깅</span><span class="sxs-lookup"><span data-stu-id="70042-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="70042-132">연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="70042-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
