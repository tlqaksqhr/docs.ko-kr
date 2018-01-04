---
title: "방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 415ffebbcf196a163932b1b83e32a6128f0bf1a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="311ee-102">방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="311ee-102">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>
<span data-ttu-id="311ee-103"><xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 메서드를 사용하여 만드는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프에 Windows Form에 표시하여 COM(구성 요소 개체 모델) 상호 운용성 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-103">You can resolve Component Object Model (COM) interoperability problems by displaying your Windows Form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop, which is created by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="311ee-104">폼이 COM 클라이언트 응용 프로그램에서 제대로 작동하게 하려면 Windows Forms 메시지 루프에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-104">To make a form work correctly from a COM client application, you must run it on a Windows Forms message loop.</span></span> <span data-ttu-id="311ee-105">이렇게 하려면 다음 접근 방식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-105">To do this, use one of the following approaches:</span></span>  
  
-   <span data-ttu-id="311ee-106"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하여 Windows Form을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form;</span></span>  
  
-   <span data-ttu-id="311ee-107">각 Windows Form을 별도 스레드에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-107">Display each Windows Form on a separate thread.</span></span> <span data-ttu-id="311ee-108">자세한 내용은 [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="311ee-108">For more information, see [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="311ee-109">프로시저</span><span class="sxs-lookup"><span data-stu-id="311ee-109">Procedure</span></span>  
 <span data-ttu-id="311ee-110"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하는 것이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프에 폼을 표시하는 가장 쉬운 방법일 수 있습니다. 모든 방법 중에서 이 방법이 코드 구현을 가장 적게 요구하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-110">Using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method can be the easiest way to display a form on a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop because, of all the approaches, it requires the least code to implement.</span></span>  
  
 <span data-ttu-id="311ee-111"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드는 관리되지 않는 응용 프로그램의 메시지 루프를 일시 중단하고 폼을 대화 상자로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-111">The <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method suspends the unmanaged application's message loop and displays the form as a dialog box.</span></span> <span data-ttu-id="311ee-112">호스트 응용 프로그램의 메시지 루프가 일시 중단되었기 때문에 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드는 새 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프를 만들어 폼의 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-112">Because the host application's message loop has been suspended, the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method creates a new [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop to process the form's messages.</span></span>  
  
 <span data-ttu-id="311ee-113"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드 사용의 단점은 폼이 모달 대화 상자로 열린다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-113">The disadvantage of using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method is that the form will be opened as a modal dialog box.</span></span> <span data-ttu-id="311ee-114">즉, Windows Form이 열려 있는 동안에는 호출하는 응용 프로그램에서 UI(사용자 인터페이스)가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-114">This behavior blocks any user interface (UI) in the calling application while the Windows Form is open.</span></span> <span data-ttu-id="311ee-115">사용자가 폼을 종료하면 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 메시지 루프가 닫히고 이전 응용 프로그램의 메시지 루프가 다시 실행되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-115">When the user exits the form, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] message loop closes and the earlier application's message loop starts running again.</span></span>  
  
 <span data-ttu-id="311ee-116">폼을 표시할 메서드를 가지고 있는 클래스 라이브러리를 Windows Forms에서 만든 다음 COM interop에 대한 클래스 라이브러리를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-116">You can create a class library in Windows Forms which has a method to show the form, and then build the class library for COM interop.</span></span> <span data-ttu-id="311ee-117">Visual Basic 6.0 또는 MFC(Microsoft Foundation Classes)에서 이 DLL 파일을 사용할 수 있으며, 이러한 환경 중 하나에서 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 호출하여 폼을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-117">You can use this DLL file from Visual Basic 6.0 or Microsoft Foundation Classes (MFC), and from either of these environments you can call the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the form.</span></span>  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="311ee-118">ShowDialog 메서드로 Windows Form을 표시하여 COM Interop를 지원하려면</span><span class="sxs-lookup"><span data-stu-id="311ee-118">To support COM interop by displaying a windows form with the ShowDialog method</span></span>  
  
-   <span data-ttu-id="311ee-119"><xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> 메서드에 대한 모든 호출을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 구성 요소의 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드에 대한 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="311ee-119">Replace all calls to the <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> method with calls to the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method in your [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311ee-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="311ee-120">See Also</span></span>  
 [<span data-ttu-id="311ee-121">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="311ee-121">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="311ee-122">방법: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="311ee-122">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 [<span data-ttu-id="311ee-123">Windows Forms 및 관리되지 않는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="311ee-123">Windows Forms and Unmanaged Applications</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
