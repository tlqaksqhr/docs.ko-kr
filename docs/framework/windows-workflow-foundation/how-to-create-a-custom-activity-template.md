---
title: "방법: 사용자 지정 활동 템플릿 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ae81b96a348712af58c5e8527f0f04a59689368
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="5dc0f-102">방법: 사용자 지정 활동 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="5dc0f-102">How to: Create a Custom Activity Template</span></span>
<span data-ttu-id="5dc0f-103">사용자 지정 활동 템플릿은 사용자가 각 활동을 개별적으로 만들지 않고 속성 및 기타 설정을 수동으로 구성하지 않아도 되도록 사용자 지정 복합 활동을 비롯한 여러 활동의 구성을 사용자 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="5dc0f-104">이러한 사용자 지정 템플릿을 사용할 수 있도록 설정에 **도구 상자** 에 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 또는 있는 사용자 수에 미리 구성 된 디자인 화면으로 끌 리호스팅된 된 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]<span data-ttu-id="5dc0f-105">이러한 서식 파일의 좋은 예로와 함께 제공:는 [SendAndReceiveReply 템플릿 디자이너](/visualstudio/workflow-designer/sendandreceivereply-template-designer) 및 [ReceiveAndSendReply 템플릿 디자이너](/visualstudio/workflow-designer/receiveandsendreply-template-designer) 에 [메시징 활동 디자이너](/visualstudio/workflow-designer/messaging-activity-designers) 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-105"> ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>  
  
 <span data-ttu-id="5dc0f-106">이 항목의 첫 번째 절차에 대 한 사용자 지정 활동 템플릿을 만드는 방법에 설명는 **지연** 활동 및 두 번째 절차에서 사용할 수 있도록 하는 방법을 설명 간단 하 게 한 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 사용자 지정 서식 파일에 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>  
  
 <span data-ttu-id="5dc0f-107">사용자 지정 활동 템플릿은 <xref:System.Activities.Presentation.IActivityTemplateFactory>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="5dc0f-108">인터페이스에는 템플릿에 사용되는 활동 인스턴스를 만들고 구성할 수 있는 단일 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>  
  
### <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="5dc0f-109">Delay 활동에 대한 템플릿을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5dc0f-109">To create a template for the Delay activity</span></span>  
  
1.  <span data-ttu-id="5dc0f-110">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-110">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="5dc0f-111">에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
     <span data-ttu-id="5dc0f-112">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="5dc0f-113">에 **프로젝트 형식** 창 선택 **워크플로** 중 하 나와 **Visual C#** 프로젝트 또는 **Visual Basic** 그룹화에 따라 프로그램 언어 기본 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>  
  
4.  <span data-ttu-id="5dc0f-114">에 **템플릿** 창 선택 **활동 라이브러리**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-114">In the **Templates** pane, select **Activity Library**.</span></span>  
  
5.  <span data-ttu-id="5dc0f-115">에 **이름** 상자에 입력 `DelayActivityTemplate`합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>  
  
6.  <span data-ttu-id="5dc0f-116">기본값을 **위치** 및 **솔루션 이름** 텍스트 상자 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="5dc0f-117">DelayActivityTemplate 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **참조 추가** 열려는 **참조 추가** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="5dc0f-118">이동 하는 **.NET** 탭을 선택한 **PresentationFramework** 에서 **구성 요소 이름** 열 왼쪽에 클릭 **확인** 참조를 추가 하려면 PresentationFramework.dll 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>  
  
9. <span data-ttu-id="5dc0f-119">이 절차를 반복하여 System.Activities.Presentation.dll 및 WindowsBase.dll 파일에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>  
  
10. <span data-ttu-id="5dc0f-120">DelayActivityTemplate 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **추가** 차례로 **새 항목** 열려는 **새 항목 추가**대화 상자.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>  
  
11. <span data-ttu-id="5dc0f-121">선택 된 **클래스** 템플릿을 mydelaytemplate으로 지정한 이름을 지정 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="5dc0f-122">MyDelayTemplate.cs 파일을 열고 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>  
  
    ```  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
    ```  
  
13. <span data-ttu-id="5dc0f-123">다음 코드를 사용하여 <xref:System.Activities.Presentation.IActivityTemplateFactory> 클래스를 통해 `MyDelayActivity`를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="5dc0f-124">그러면 지연 기간이 10초로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-124">This configures the delay to have a duration of 10 seconds.</span></span>  
  
    ```  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
    ```  
  
14. <span data-ttu-id="5dc0f-125">선택 **솔루션 빌드** 에서 **빌드** 메뉴 DelayActivityTemplate.dll 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>  
  
### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="5dc0f-126">워크플로 디자이너에서 템플릿을 사용할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="5dc0f-126">To make the template available in a Workflow Designer</span></span>  
  
1.  <span data-ttu-id="5dc0f-127">DelayActivityTemplate 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **추가** 차례로 **새 프로젝트** 열려는 **새 프로젝트 추가** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="5dc0f-128">선택 된 **워크플로 콘솔 응용 프로그램** 서식 파일을 이름을 `CustomActivityTemplateApp`, 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5dc0f-129">CustomActivityTemplateApp 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **참조 추가** 열려는 **참조 추가** 대화 상자 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
4.  <span data-ttu-id="5dc0f-130">이동 하는 **프로젝트** 탭을 선택한 **DelayActivityTemplate** 에서 **프로젝트 이름** 열 왼쪽에 클릭 **확인** 추가 하는 첫 번째 절차에서 만든 DelayActivityTemplate.dll 파일에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>  
  
5.  <span data-ttu-id="5dc0f-131">CustomActivityTemplateApp 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **빌드** 는 응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>  
  
6.  <span data-ttu-id="5dc0f-132">CustomActivityTemplateApp 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>  
  
7.  <span data-ttu-id="5dc0f-133">선택 **디버깅 하지 않고 시작** 에서 **디버그** cmd.exe 창에서 메시지가 표시 되 면 계속 하려면 아무 키나 메뉴와 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>  
  
8.  <span data-ttu-id="5dc0f-134">Workflow1.xaml 파일을 열고 엽니다는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="5dc0f-135">찾을 **MyDelayActivity** 에서 서식 파일은 **DelayActivityTemplate** 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="5dc0f-136">디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-136">Drag it onto the design surface.</span></span> <span data-ttu-id="5dc0f-137">확인는 **속성** 창 하는 `Duration` 속성이 10 초로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dc0f-138">예제</span><span class="sxs-lookup"><span data-stu-id="5dc0f-138">Example</span></span>  
 <span data-ttu-id="5dc0f-139">MyDelayActivity.cs 파일에 다음 코드가 들어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc0f-139">The MyDelayActivity.cs file should contain the following code.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
//Namespaces added  
using System.Activities;  
using System.Activities.Statements;  
using System.Activities.Presentation;  
using System.Windows;  
  
namespace DelayActivityTemplate  
{  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dc0f-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5dc0f-140">See Also</span></span>  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
 [<span data-ttu-id="5dc0f-141">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5dc0f-141">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
