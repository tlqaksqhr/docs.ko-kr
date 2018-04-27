---
title: '연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 49d5a998cfa9465bc17a6acd2a459a6ef2c28cff
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="2b7ab-102">연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b7ab-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2b7ab-103">에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="2b7ab-104">그러나, 때때로 경우도 있습니다 사용할 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 사용자 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="2b7ab-105">예를 들어 기존 상당한 투자를 해야 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 또는 있습니다 있을 수는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 고유 기능을 제공 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="2b7ab-106">이 연습에서는 Windows Forms를 호스트 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="2b7ab-107">이 연습에 나와 있는 작업의 전체 코드 목록을 보려면 [wpf XAML 예제를 사용 하 여 Windows Forms 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=160000)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b7ab-108">전제 조건</span><span class="sxs-lookup"><span data-stu-id="2b7ab-108">Prerequisites</span></span>  
 <span data-ttu-id="2b7ab-109">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="2b7ab-110">.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="2b7ab-111">Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b7ab-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="2b7ab-112">MaskedTextBox 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="2b7ab-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="2b7ab-113">이라는 WPF 응용 프로그램 프로젝트 만들기 `HostingWfInWpfWithXaml`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-113">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="2b7ab-114">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="2b7ab-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="2b7ab-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="2b7ab-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="2b7ab-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="2b7ab-117">MainWindow.xaml의 열은 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="2b7ab-118">에 <xref:System.Windows.Window> 요소를 다음 네임 스페이스 매핑을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-118">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="2b7ab-119">`wf` 네임 스페이스 매핑을 Windows Forms 컨트롤을 포함 하는 어셈블리에 대 한 참조를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-119">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="2b7ab-120">에 <xref:System.Windows.Controls.Grid> 다음 XAML을 추가 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-120">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="2b7ab-121"><xref:System.Windows.Forms.MaskedTextBox> 컨트롤의 자식으로 생성 됩니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-121">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="2b7ab-122">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7ab-122">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7ab-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b7ab-123">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="2b7ab-124">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="2b7ab-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="2b7ab-125">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b7ab-125">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="2b7ab-126">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b7ab-126">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="2b7ab-127">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b7ab-127">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="2b7ab-128">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2b7ab-128">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="2b7ab-129">XAML 예제를 사용 하 여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="2b7ab-129">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160000)
