---
title: "방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ab87761167c19ee0fe78d33edcfe8662d90e36a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="6be1c-102">방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="6be1c-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="6be1c-103">이 절차에서는 Windows Form에 Windows Presentation Foundation (WPF) 컨트롤을 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6be1c-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6be1c-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6be1c-106">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6be1c-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="6be1c-107">복사 하 여 디자인 타임에 ElementHost 컨트롤을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-107">To copy and paste an ElementHost control at design time</span></span>  
  
1.  <span data-ttu-id="6be1c-108">새 WPF 추가 <xref:System.Windows.Controls.UserControl> Windows Forms 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="6be1c-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="6be1c-109">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="6be1c-110">자세한 내용은 참조 [연습: 새 WPF 콘텐츠 만들기 디자인 타임에 Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="6be1c-111">에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 의 속성 `UserControl1` 를 `200`합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3.  <span data-ttu-id="6be1c-112"><xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4.  <span data-ttu-id="6be1c-113">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-113">Build the project.</span></span>  
  
5.  <span data-ttu-id="6be1c-114">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6.  <span data-ttu-id="6be1c-115">**도구 상자**의 인스턴스를 끌어 `UserControl1` 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="6be1c-116">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7.  <span data-ttu-id="6be1c-117">`elementHost1`을 선택하고 Ctrl+C를 눌러 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8.  <span data-ttu-id="6be1c-118">CTRL + V를 붙여 복사한 컨트롤을 폼으로 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="6be1c-119">새 <xref:System.Windows.Forms.Integration.ElementHost> 라는 컨트롤 `elementHost2` 폼에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6be1c-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be1c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6be1c-120">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="6be1c-121">연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="6be1c-121">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [<span data-ttu-id="6be1c-122">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="6be1c-122">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="6be1c-123">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="6be1c-123">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="6be1c-124">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="6be1c-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
