---
title: "방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기"
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
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc782ba262527a319cbb05cc6d36ca568afc55c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="be106-102">방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기</span><span class="sxs-lookup"><span data-stu-id="be106-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="be106-103">이중 버퍼링은 메모리 버퍼를 사용하여 여러 그리기 작업과 관련된 깜박임 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="be106-104">이중 버퍼링을 사용하면 모든 그리기 작업이 그리기 화면 대신 메모리 버퍼에 먼저 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="be106-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="be106-105">모든 그리기 작업이 완료되면 메모리 버퍼가 연결된 그리기 화면에 직접 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="be106-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="be106-106">화면에 하나의 그래픽 작업을 수행 하기 때문에 복잡 한 그리기 작업과 관련 된 이미지 깜박임이 제거 되었습니다. 대부분의 응용 프로그램에서 제공 하는 기본 이중 버퍼링는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 최상의 결과 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="be106-107">표준 Windows Forms 컨트롤을 두 번 기본적으로 버퍼링 합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="be106-108">두 가지 방법으로 컨트롤을 작성 한 폼에서 기본 이중 버퍼링을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be106-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="be106-109">설정 하거나는 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`, 하거나 호출할 수 있습니다는 <xref:System.Windows.Forms.Control.SetStyle%2A> 설정 하는 메서드는 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 플래그를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="be106-110">두 방법 모두 폼 이나 컨트롤에 대 한 기본 이중 버퍼링을 설정 하 고 그래픽 깜빡임 렌더링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="be106-111">호출 된 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 모든 렌더링 코드를 작성 한 사용자 지정 컨트롤에만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be106-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="be106-112">애니메이션 또는 고급 메모리 관리와 같은 보다 고급 이중 버퍼링 시나리오에 대 한 고유한 이중 버퍼링 논리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be106-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="be106-113">자세한 내용은 참조 [하는 방법: 버퍼링 된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-113">For more information, see [How to: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="be106-114">깜빡임 줄이기 위해</span><span class="sxs-lookup"><span data-stu-id="be106-114">To reduce flicker</span></span>  
  
-   <span data-ttu-id="be106-115"><xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="be106-116">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="be106-116">\- or -</span></span>  
  
-   <span data-ttu-id="be106-117">호출의 <xref:System.Windows.Forms.Control.SetStyle%2A> 설정 하는 메서드는 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 플래그를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="be106-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="be106-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be106-118">See Also</span></span>  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [<span data-ttu-id="be106-119">이중 버퍼링 그래픽</span><span class="sxs-lookup"><span data-stu-id="be106-119">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="be106-120">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="be106-120">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
