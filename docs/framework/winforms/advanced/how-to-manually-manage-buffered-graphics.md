---
title: '방법: 버퍼링된 그래픽 수동 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: f8675582fe6bafefd94d6a740c3263e407dfd4e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523957"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="7f7ac-102">방법: 버퍼링된 그래픽 수동 관리</span><span class="sxs-lookup"><span data-stu-id="7f7ac-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="7f7ac-103">더 많은 고급 이중 버퍼링 시나리오를 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이중 버퍼링 논리를 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="7f7ac-104">할당 및 개별 그래픽 버퍼를 관리 하는 일을 담당 하는 클래스는 <xref:System.Drawing.BufferedGraphicsContext> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="7f7ac-105">모든 응용 프로그램에는 자체 기본 <xref:System.Drawing.BufferedGraphicsContext> 기본 이중 버퍼링 해당 응용 프로그램의 모든 관리입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="7f7ac-106">호출 하 여이 인스턴스에 대 한 참조를 검색할 수 있습니다는 <xref:System.Drawing.BufferedGraphicsManager.Current%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="7f7ac-107">BufferedGraphicsContext 기본에 대 한 참조를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="7f7ac-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="7f7ac-108">설정의 <xref:System.Drawing.BufferedGraphicsManager.Current%2A> 속성을 다음 코드 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="7f7ac-109">호출할 필요가 없습니다는 `Dispose` 에서 메서드는 <xref:System.Drawing.BufferedGraphicsContext> 에서 수신 하는 참조는 <xref:System.Drawing.BufferedGraphicsManager> 클래스.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="7f7ac-110"><xref:System.Drawing.BufferedGraphicsManager> 메모리 할당 및 기본에 대 한 배포의 모든 처리 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="7f7ac-111">애니메이션 같은 그래픽 위주의 응용 프로그램에 대 한 경우에 따라 성능을 개선할 수 있습니다 전용을 사용 하 여 <xref:System.Drawing.BufferedGraphicsContext> 대신는 <xref:System.Drawing.BufferedGraphicsContext> 에서 제공 되는 <xref:System.Drawing.BufferedGraphicsManager>합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="7f7ac-112">따라서 만들고 모든는 다른 버퍼링 된 그래픽 관리 응용 프로그램과 연결 된 경우에 응용 프로그램에서 사용 되는 메모리 뛰어날 것의 성능 오버 헤드를 발생 시 키 지 않고 그래픽 버퍼를 개별적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="7f7ac-113">전용된 BufferedGraphicsContext를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7f7ac-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="7f7ac-114">선언 하 고의 새 인스턴스를 만듭니다는 <xref:System.Drawing.BufferedGraphicsContext> 다음 코드 예제와 같이 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="7f7ac-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f7ac-115">See Also</span></span>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [<span data-ttu-id="7f7ac-116">이중 버퍼링 그래픽</span><span class="sxs-lookup"><span data-stu-id="7f7ac-116">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="7f7ac-117">방법: 버퍼링된 그래픽 수동 렌더링</span><span class="sxs-lookup"><span data-stu-id="7f7ac-117">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
