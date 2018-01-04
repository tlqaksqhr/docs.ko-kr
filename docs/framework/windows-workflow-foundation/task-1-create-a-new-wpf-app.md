---
title: "작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a207b09ff7124bb161678627f365a6fa4021a38d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="2eeb8-102">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="2eeb8-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="2eeb8-103">이 태스크에서는 WPF 응용 프로그램 Visual Studio 템플릿을 사용하여 빈 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 응용 프로그램을 만들고 해당 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-103">In this task, you will create an empty [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="2eeb8-104">WPF 응용 프로그램 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2eeb8-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="2eeb8-105">열기 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] 및는 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-105">Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="2eeb8-106">에 **새 프로젝트** 대화 상자를 선택 **Visual C#** 또는 **Visual Basic** 에서 **설치 된 템플릿** 의 왼쪽 창 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="2eeb8-107">선택한 언어가 표시 되지 않으면에서 찾아봅니다 **다른 언어**합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="2eeb8-108">선택 **Windows** 에 **설치 된 템플릿** 창.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="2eeb8-109">위쪽 창에 있는지를 확인 (기본값) **.NET Framework 4** 선택 하 여 드롭다운 목록 상자에서 선택한 **WPF 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="2eeb8-110">프로젝트의 이름을 설정 **HostingApplication** 창의 맨 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="2eeb8-111">솔루션 이름으로 설정 **RehostingTheDesigner**합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="2eeb8-112">클릭 **확인** 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-112">Click **OK** to create the application project.</span></span> [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]<span data-ttu-id="2eeb8-113">에서 응용 프로그램에 대한 기본 WPF UI를 만들고 해당 XAML 및 코드 숨김 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-113"> creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="2eeb8-114">에 대 한 참조를 추가 **WorkflowModel** 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="2eeb8-115">이 수행 하려면 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **HostingApplication** 프로젝트를 마우스 선택 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="2eeb8-116">에 **참조 추가** 대화 상자를 클릭는 **.NET** 탭에서 CTRL 키를 누른 다음 어셈블리를 선택한 다음를 클릭 **확인**:</span><span class="sxs-lookup"><span data-stu-id="2eeb8-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="2eeb8-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="2eeb8-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="2eeb8-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="2eeb8-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="2eeb8-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="2eeb8-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="2eeb8-120">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="2eeb8-121">참조 [작업 2: 워크플로 디자이너 호스트](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) 워크플로 디자이너 디자인 캔버스를 호스트 하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeb8-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eeb8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2eeb8-122">See Also</span></span>  
 [<span data-ttu-id="2eeb8-123">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="2eeb8-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="2eeb8-124">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="2eeb8-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
