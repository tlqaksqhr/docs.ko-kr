---
title: '방법: Win32 호스트 컨테이너를 사용하여 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: 01c6a9dad6fccb38be4f240d0900727f776fd2b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560510"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="28c8d-102">방법: Win32 호스트 컨테이너를 사용하여 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="28c8d-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="28c8d-103">내에서 시각적 개체를 만들 수는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 시각적 개체에 대 한 창 컨테이너 호스트를 제공 하 여이 창을 합니다.</span><span class="sxs-lookup"><span data-stu-id="28c8d-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="28c8d-104">포함된 시각적 개체에 대한 이벤트 처리를 제공하려면 호스트 창 컨테이너의 메시지 필터 루프에 전달된 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="28c8d-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="28c8d-105">참조 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) 에서 시각적 개체를 호스트 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창.</span><span class="sxs-lookup"><span data-stu-id="28c8d-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28c8d-106">예제</span><span class="sxs-lookup"><span data-stu-id="28c8d-106">Example</span></span>  
 <span data-ttu-id="28c8d-107">다음 코드에 대 한 마우스 이벤트 처리기를 설정 하는 방법을 보여 줍니다는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시각적 개체에 대 한 호스트 컨테이너로 사용 되는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="28c8d-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="28c8d-108">다음 예제에 대 한 응답으로 특정 마우스 이벤트 트래핑 적중 횟수 테스트를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28c8d-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="28c8d-109"><xref:System.Windows.Interop.HwndSource> 개체가 나타내는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 내에서 콘텐츠는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 창.</span><span class="sxs-lookup"><span data-stu-id="28c8d-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="28c8d-110">값은 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 의 속성은 <xref:System.Windows.Interop.HwndSource> 개체 시각적 트리 계층의 최상위 노드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28c8d-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="28c8d-111">적중 횟수 테스트에 전체 샘플 Win32 호스트 컨테이너를 사용 하 여 개체에 대 한 참조 [Win32 상호 운용성 샘플을 사용 하 여 적중 테스트](http://go.microsoft.com/fwlink/?LinkID=159995)합니다.</span><span class="sxs-lookup"><span data-stu-id="28c8d-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c8d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28c8d-112">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="28c8d-113">시각적 계층에서 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="28c8d-113">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="28c8d-114">자습서: Win32 응용 프로그램에서 시각적 개체 호스팅</span><span class="sxs-lookup"><span data-stu-id="28c8d-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
