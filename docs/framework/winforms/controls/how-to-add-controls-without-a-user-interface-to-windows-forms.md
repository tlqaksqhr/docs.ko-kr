---
title: '방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e900c1c34f69531a14cfa11803ef5a6afb4783c6
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="2ed5b-102">방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2ed5b-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="2ed5b-103">비시각적 컨트롤 (또는 구성 요소) 응용 프로그램에 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="2ed5b-104">다른 컨트롤과 달리 구성 요소 사용자에 게 사용자 인터페이스를 제공 하지 않는 및 따라서 Windows Forms 디자이너 화면에 표시 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="2ed5b-105">구성 요소는 폼에 추가 되 면 Windows Forms 디자이너 구성 요소를 모두 표시 되는 폼의 아래쪽에 크기를 조정할 수 트레이 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="2ed5b-106">컨트롤에 구성 요소 트레이에 추가 되 면 구성 요소를 선택한 폼에서 다른 컨트롤 처럼 해당 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ed5b-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2ed5b-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2ed5b-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="2ed5b-110">Windows Form에 구성 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="2ed5b-110">To add a component to a Windows Form</span></span>  
  
1.  <span data-ttu-id="2ed5b-111">폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-111">Open the form.</span></span> <span data-ttu-id="2ed5b-112">자세한 내용은 참조 [하는 방법: Windows Forms 디자이너에 표시](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-112">For details, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="2ed5b-113">에 **도구 상자**구성 요소를 클릭 하 고 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="2ed5b-114">구성 요소가 구성 요소 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="2ed5b-115">또한 런타임 시 구성 요소는 폼에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="2ed5b-116">이것이 일반적인 시나리오에서 특히 않기 때문에 구성 요소 사용자 인터페이스가 있는 컨트롤과 달리 visual 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="2ed5b-117">다음 예제에는 <xref:System.Windows.Forms.Timer> 런타임 시 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="2ed5b-118">(Visual Studio에는 다른 타이머의 수;이 경우 Windows Forms를 사용 하 여 <xref:System.Windows.Forms.Timer> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="2ed5b-119">Visual Studio에서 다양 한 타이머에 대 한 자세한 내용은 참조 [서버 기반 타이머 소개](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span><span class="sxs-lookup"><span data-stu-id="2ed5b-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2ed5b-120">구성 요소는 종종 효과적으로 기능 구성 요소에 대해 설정 해야 하는 컨트롤 관련 속성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="2ed5b-121">경우에 <xref:System.Windows.Forms.Timer> 설정 아래 구성 요소는 `Interval` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="2ed5b-122">때는 반드시 프로젝트에 속성을 설정 하 고 해당 구성 요소에 필요한 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="2ed5b-123">프로그래밍 방식으로 Windows Form에 구성 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="2ed5b-123">To add a component to a Windows Form programmatically</span></span>  
  
1.  <span data-ttu-id="2ed5b-124">인스턴스를 만들고는 <xref:System.Windows.Forms.Timer> 코드의 클래스.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2.  <span data-ttu-id="2ed5b-125">설정의 `Interval` 속성 타이머 틱 간에 시간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3.  <span data-ttu-id="2ed5b-126">구성 요소에 필요한 기타 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="2ed5b-127">다음 코드와 생성 한 <xref:System.Windows.Forms.Timer> 와 해당 `Interval` 속성 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2ed5b-128">악의적인 UserControl을 참조 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="2ed5b-129">악의적인 사용자가 실수로 프로젝트에 추가 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 것만.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed5b-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ed5b-130">See Also</span></span>  
 [<span data-ttu-id="2ed5b-131">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2ed5b-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="2ed5b-132">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2ed5b-132">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="2ed5b-133">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2ed5b-133">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="2ed5b-134">방법: Windows Forms 간에 컨트롤 복사</span><span class="sxs-lookup"><span data-stu-id="2ed5b-134">How to: Copy Controls Between Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [<span data-ttu-id="2ed5b-135">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="2ed5b-135">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="2ed5b-136">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="2ed5b-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="2ed5b-137">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2ed5b-137">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="2ed5b-138">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2ed5b-138">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
