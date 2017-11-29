---
title: "방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 985aa58056f4c4ec8f3042c682291508f1434ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="4445e-102">방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="4445e-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="4445e-103">하지만 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 기능을 추가 하 고는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하는 경우 이전 버전과 호환성 및 이후 사용을 모두 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="4445e-104"><xref:System.Windows.Forms.NotifyIcon> 구성 요소 작업 표시줄의 상태 알림 영역에 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="4445e-105">일반적으로 응용 프로그램 명령을 나타내는 응용 프로그램으로 보낼이 아이콘을 마우스 오른쪽 단추로 클릭 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="4445e-106">연결 하 여 한 <xref:System.Windows.Forms.ContextMenu> 구성 요소는 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 응용 프로그램에이 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4445e-107">응용 프로그램의 인스턴스를 표시 하는 동안 시작 시 최소화 하려는 경우는 <xref:System.Windows.Forms.NotifyIcon> 의 작업 표시줄에서 구성 요소에는 기본 폼의 설정 <xref:System.Windows.Forms.Form.WindowState%2A> 속성을 <xref:System.Windows.Forms.FormWindowState.Minimized> 하십시오는 <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성 로 설정 된 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="4445e-108">NotifyIcon 구성 요소와 디자인 타임에 바로 가기 메뉴를 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="4445e-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1.  <span data-ttu-id="4445e-109">추가 <xref:System.Windows.Forms.NotifyIcon> 폼에 구성 요소와 같은 중요 한 속성을 설정 하 고는 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="4445e-110">자세한 내용은 참조 [하는 방법: Windows Forms NotifyIcon 구성 요소와 작업 표시줄에 응용 프로그램 아이콘 추가](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2.  <span data-ttu-id="4445e-111">추가 <xref:System.Windows.Forms.ContextMenu> Windows Form에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="4445e-112">런타임 시 사용할 수 있도록 설정할 명령을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="4445e-113">액세스 키 등 이러한 새 메뉴 항목에 메뉴 향상을 추가 하는 데 좋은 시간이 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3.  <span data-ttu-id="4445e-114">설정의 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 속성의는 <xref:System.Windows.Forms.NotifyIcon> 추가한 바로 가기 메뉴에는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="4445e-115">이 속성이 설정 된 작업 표시줄에서 아이콘을 클릭 하면 바로 가기 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="4445e-116">NotifyIcon 구성 요소와 바로 가기 메뉴를 프로그래밍 방식으로 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="4445e-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1.  <span data-ttu-id="4445e-117">인스턴스를 만들는 <xref:System.Windows.Forms.NotifyIcon> 클래스 및 <xref:System.Windows.Forms.ContextMenu> 속성 설정은 응용 프로그램에 필요한 모든 클래스 (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 에 대 한 속성의 <xref:System.Windows.Forms.NotifyIcon> 에 대 한 메뉴 항목, 구성는 <xref:System.Windows.Forms.ContextMenu> 구성 요소)입니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2.  <span data-ttu-id="4445e-118">설정의 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 속성의는 <xref:System.Windows.Forms.NotifyIcon> 추가한 바로 가기 메뉴에는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="4445e-119">이 속성이 설정 된 작업 표시줄에서 아이콘을 클릭 하면 바로 가기 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4445e-120">다음 코드 예제에서는 기본 메뉴 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="4445e-121">메뉴 선택 개발 하는 응용 프로그램에 맞게 사용자 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="4445e-122">또한 처리 하는 코드를 작성 하려면 됩니다는 <xref:System.Windows.Forms.MenuItem.Click> 이러한 새 메뉴 항목에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
>  <span data-ttu-id="4445e-123">초기화 해야 `notifyIcon1` 및 `contextMenu1,` 폼의 생성자에 다음 문을 포함 하 여 어떤 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4445e-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="4445e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4445e-124">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="4445e-125">방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 응용 프로그램 아이콘 추가</span><span class="sxs-lookup"><span data-stu-id="4445e-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [<span data-ttu-id="4445e-126">NotifyIcon 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4445e-126">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="4445e-127">NotifyIcon 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="4445e-127">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
