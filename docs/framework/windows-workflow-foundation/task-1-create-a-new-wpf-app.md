---
title: '작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 5576d6f893aa405d454758387334b85a473b0c73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517951"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="ac789-102">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="ac789-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="ac789-103">이 태스크에서는 WPF 응용 프로그램에 대 한 Visual Studio 템플릿을 사용 하 여 빈 Windows Presentation Foundation (WPF) 응용 프로그램을 만들 및 적절 한 참조를 추가 합니다 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="ac789-104">WPF 응용 프로그램 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ac789-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="ac789-105">Visual Studio를 열고 및는 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="ac789-106">에 **새 프로젝트** 대화 상자를 선택 **Visual C#** 또는 **Visual Basic** 에서 **설치 된 템플릿** 의 왼쪽 창 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="ac789-107">선택한 언어가 표시 되지 않으면에서 찾아봅니다 **다른 언어**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="ac789-108">선택 **Windows** 에 **설치 된 템플릿** 창.</span><span class="sxs-lookup"><span data-stu-id="ac789-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="ac789-109">위쪽 창에 있는지를 확인 (기본값) **.NET Framework 4** 선택 하 여 드롭다운 목록 상자에서 선택한 **WPF 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="ac789-110">프로젝트의 이름을 설정 **HostingApplication** 창의 맨 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="ac789-111">솔루션 이름으로 설정 **RehostingTheDesigner**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="ac789-112">클릭 **확인** 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="ac789-113">Visual Studio 응용 프로그램에 대 한 기본 WPF UI를 만들고 해당 XAML 및 코드 숨김 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="ac789-114">에 대 한 참조를 추가 **WorkflowModel** 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="ac789-115">이 수행 하려면 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **HostingApplication** 프로젝트를 마우스 선택 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="ac789-116">에 **참조 추가** 대화 상자를 클릭는 **.NET** 탭에서 CTRL 키를 누른 다음 어셈블리를 선택한 다음를 클릭 **확인**:</span><span class="sxs-lookup"><span data-stu-id="ac789-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="ac789-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="ac789-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="ac789-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="ac789-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="ac789-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="ac789-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="ac789-120">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="ac789-121">참조 [작업 2: 워크플로 디자이너 호스트](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) 워크플로 디자이너 디자인 캔버스를 호스트 하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac789-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac789-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac789-122">See Also</span></span>  
 [<span data-ttu-id="ac789-123">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="ac789-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="ac789-124">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="ac789-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
