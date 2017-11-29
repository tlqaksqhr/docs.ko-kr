---
title: "방법: Windows Forms 응용 프로그램에서 글꼴 구성표 변경에 응답"
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
helpviewer_keywords: Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b2e53df114c491e99e13940ae47a4119bd8da46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="9e41f-102">방법: Windows Forms 응용 프로그램에서 글꼴 구성표 변경에 응답</span><span class="sxs-lookup"><span data-stu-id="9e41f-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="9e41f-103">Windows 운영 체제에서 사용자 표시의 기본 글꼴 확대 하거나 축소 하도록 시스템 수준 글꼴 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="9e41f-104">이러한 글꼴 설정을 변경 하는 것은 화면에 텍스트를 읽을 수 있는 더 큰 유형 필요 하 고 시각 장애가 있는 사용자는 사용자에 게 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="9e41f-105">글꼴 구성표 변경 될 때마다는 양식 및 포함 된 모든 텍스트의 크기를 늘리거나 하 여 이러한 변경에 대응 하 여 Windows Forms 응용 프로그램을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="9e41f-106">동적으로 글꼴 크기의 변경 내용을 수용 하기 위해 폼을 하려는 경우를 폼 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="9e41f-107">일반적으로 Windows Forms에서 사용 하는 기본 글꼴은 글꼴에서 반환 되는 <xref:Microsoft.Win32> 네임 스페이스 호출 `GetStockObject(DEFAULT_GUI_FONT)`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="9e41f-108">이 호출에서 반환 되는 글꼴 화면 해상도 변경 하는 경우에 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="9e41f-109">코드에서 기본 글꼴을 변경 해야 다음 절차에 나와 있는 것 처럼 <xref:System.Drawing.SystemFonts.IconTitleFont%2A> 글꼴 크기의 변경 내용에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="9e41f-110">데스크톱 글꼴을 사용 하 고 글꼴 구성표 변경에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="9e41f-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="9e41f-111">폼을 만들고 원하는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="9e41f-112">자세한 내용은 참조 [하는 방법: 명령줄에서 Windows Forms 응용 프로그램을 만들기](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) 및 [Windows Forms에서 사용할 컨트롤](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="9e41f-113">에 대 한 참조 추가 <xref:Microsoft.Win32> 코드에 대 한 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="9e41f-114">필요한 이벤트 처리기를 연결 하 고 폼에 사용 중인 기본 글꼴을 변경 하 여 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="9e41f-115">구현에 대 한 처리기는 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 폼 크기를 자동으로 조정 하는 이벤트는 때는 <xref:Microsoft.Win32.UserPreferenceCategory.Window> 범주 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="9e41f-116">에 대 한 처리기를 구현 하는 마지막으로 <xref:System.Windows.Forms.Form.FormClosing> 분리 하는 이벤트는 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e41f-117">이 코드를 포함 하는 오류를 사용 하면 응용 프로그램에서 메모리 누수를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  <span data-ttu-id="9e41f-118">코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="9e41f-119">수동으로 Windows XP에서 글꼴 구성표를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="9e41f-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="9e41f-120">Windows Forms 응용 프로그램 실행 되는 동안 Windows 바탕 화면을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="9e41f-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="9e41f-121">에 **디스플레이 속성** 대화 상자를 클릭는 **모양** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="9e41f-122">**글꼴 크기** 드롭다운 목록 상자에서 새 글꼴 크기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="9e41f-123">폼에 응답 하 여 바탕 화면 글꼴 구성표에 대 한 런타임 변경 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-123">You will notice that the form now reacts to run time changes in the desktop font scheme.</span></span> <span data-ttu-id="9e41f-124">사용자 간에 변경 될 때 **보통**, **큰 글꼴**, 및 **아주 큰 글꼴**, 폼 글꼴이 변경 되 고 크기가 올바르게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e41f-125">예제</span><span class="sxs-lookup"><span data-stu-id="9e41f-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="9e41f-126">에 대 한 호출을 포함 하는이 코드 예제 constructer `InitializeComponent`, Visual Studio에서 새 Windows Forms 프로젝트를 만들 때 정의 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="9e41f-127">명령줄에서 응용 프로그램을 작성 하는 경우이 줄의 코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e41f-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e41f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e41f-128">See Also</span></span>  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [<span data-ttu-id="9e41f-129">Windows Forms의 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="9e41f-129">Automatic Scaling in Windows Forms</span></span>](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
