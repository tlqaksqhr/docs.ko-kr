---
title: "PrintPreviewDialog 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed071a4d38a0167ac9414ee7d383736dd38a62a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="49460-102">PrintPreviewDialog 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="49460-102">PrintPreviewDialog Control Overview (Windows Forms)</span></span>
<span data-ttu-id="49460-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 표시 하는 데 사용 되는 미리 구성 된 대화 상자가 어떻게는 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 인쇄할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49460-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="49460-104">고유한 대화 상자를 구성 하는 대신 간단한 솔루션으로 Windows 기반 응용 프로그램 내에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49460-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="49460-105">컨트롤에는 인쇄, 확대, 한 페이지 또는 여러 페이지 표시 및 대화 상자 닫기 단추가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49460-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="49460-106">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="49460-106">Key Properties and Methods</span></span>  
 <span data-ttu-id="49460-107">컨트롤의 키 속성은 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>를 미리 볼 수 있도록 문서를 설정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="49460-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="49460-108">해당 문서는 <xref:System.Drawing.Printing.PrintDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="49460-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="49460-109">대화 상자를 표시 하기 위해 호출 해야 해당 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="49460-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="49460-110">앤티앨리어싱 매끄럽게, 표시 텍스트를 만들 수 있지만 느린; 디스플레이 축소할 수 있습니다. 이 기능을 사용 하려면 설정는 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="49460-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="49460-111">특정 속성을 통해 사용할 수는 <xref:System.Windows.Forms.PrintPreviewControl> 하 고 <xref:System.Windows.Forms.PrintPreviewDialog> 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="49460-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="49460-112">(이 추가할 필요가 없습니다 <xref:System.Windows.Forms.PrintPreviewControl> 을 폼은 자동으로 포함 되어는 <xref:System.Windows.Forms.PrintPreviewDialog> 폼에 대화 상자를 추가 합니다.) 통해 사용할 수 있는 속성의 예는 <xref:System.Windows.Forms.PrintPreviewControl> 됩니다는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 가로 및 세로로 컨트롤에 표시 되는 페이지 수를 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="49460-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="49460-113">에 액세스할 수 있습니다는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 속성으로 `PrintPreviewDialog1.PrintPreviewControl.Columns` 에 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` 에 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], 또는 `printPreviewDialog1->PrintPreviewControl->Columns` 에서 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="49460-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49460-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49460-114">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="49460-115">PrintPreviewControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="49460-115">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="49460-116">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49460-116">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="49460-117">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="49460-117">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
