---
title: '방법: 버퍼링된 그래픽 수동 렌더링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: ab0868e31ac8b010c662c04a7670e1ead19cebe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524198"
---
# <a name="how-to-manually-render-buffered-graphics"></a><span data-ttu-id="63945-102">방법: 버퍼링된 그래픽 수동 렌더링</span><span class="sxs-lookup"><span data-stu-id="63945-102">How to: Manually Render Buffered Graphics</span></span>
<span data-ttu-id="63945-103">버퍼링된 고유한 그래픽을 관리하는 경우 그래픽 버퍼를 만들고 렌더링할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63945-103">If you are managing your own buffered graphics, you will need to be able to create and render graphics buffers.</span></span> <span data-ttu-id="63945-104"><xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> 메서드를 호출하여 화면의 그리기 화면과 연결된 <xref:System.Drawing.BufferedGraphics> 클래스의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63945-104">You can create instances of the <xref:System.Drawing.BufferedGraphics> class that is associated with drawing surfaces on your screen by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method.</span></span> <span data-ttu-id="63945-105">이 메서드는 폼 또는 컨트롤과 같은 특정 렌더링 화면과 연결된 <xref:System.Drawing.BufferedGraphics> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63945-105">This method creates a <xref:System.Drawing.BufferedGraphics> instance that is associated with a particular rendering surface, such as a form or control.</span></span> <span data-ttu-id="63945-106"><xref:System.Drawing.BufferedGraphics> 인스턴스를 만든 후 <xref:System.Drawing.BufferedGraphics.Graphics%2A> 속성을 통해 나타내는 버퍼에 통해 나타내는 버퍼에 그래픽을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63945-106">After you have created a <xref:System.Drawing.BufferedGraphics> instance, you can draw graphics to the buffer it represents through the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="63945-107">모든 그래픽 작업을 수행한 후 <xref:System.Drawing.BufferedGraphics.Render%2A> 메서드를 호출하여 버퍼 내용을 화면에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63945-107">After you have performed all graphics operations, you can copy the contents of the buffer to the screen by calling the <xref:System.Drawing.BufferedGraphics.Render%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63945-108">고유한 렌더링을 수행하는 경우 약간의 증가이긴 하지만 메모리 사용이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="63945-108">If you perform your own rendering, memory consumption will increase, though the increase may only be slight.</span></span>  
  
### <a name="to-manually-display-buffered-graphics"></a><span data-ttu-id="63945-109">버퍼링된 그래픽을 수동으로 표시하려면</span><span class="sxs-lookup"><span data-stu-id="63945-109">To manually display buffered graphics</span></span>  
  
1.  <span data-ttu-id="63945-110"><xref:System.Drawing.BufferedGraphicsContext> 클래스의 인스턴스에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63945-110">Obtain a reference to an instance of the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="63945-111">자세한 내용은 참조 [하는 방법: 버퍼링 된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63945-111">For more information, see [How to: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span></span>  
  
2.  <span data-ttu-id="63945-112">다음 코드 예제와 같이 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> 메서드를 호출하여 <xref:System.Drawing.BufferedGraphics> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63945-112">Create an instance of the <xref:System.Drawing.BufferedGraphics> class by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3.  <span data-ttu-id="63945-113"><xref:System.Drawing.BufferedGraphics.Graphics%2A> 속성을 설정하여 그래픽 버퍼에 그래픽을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="63945-113">Draw graphics to the graphics buffer by setting the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="63945-114">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="63945-114">For example:</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4.  <span data-ttu-id="63945-115">그래픽 버퍼에 그리기 작업을 모두 완료했으면, 다음 코드 예제와 같이 <xref:System.Drawing.BufferedGraphics.Render%2A> 메서드를 호출하여 해당 버퍼와 연결된 그리기 화면이나 지정된 그리기 화면에 버퍼를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="63945-115">When you have completed all of your drawing operations to the graphics buffer, call the <xref:System.Drawing.BufferedGraphics.Render%2A> method to render the buffer, either to the drawing surface associated with that buffer, or to a specified drawing surface, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5.  <span data-ttu-id="63945-116">그래픽 렌더링을 마친 후 <xref:System.Drawing.BufferedGraphics> 인스턴스에 대해 `Dispose` 메서드를 호출하여 시스템 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="63945-116">After you are finished rendering graphics, call the `Dispose` method on the <xref:System.Drawing.BufferedGraphics> instance to free system resources.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="63945-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63945-117">See Also</span></span>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphics>  
 [<span data-ttu-id="63945-118">이중 버퍼링 그래픽</span><span class="sxs-lookup"><span data-stu-id="63945-118">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="63945-119">방법: 버퍼링된 그래픽 수동 관리</span><span class="sxs-lookup"><span data-stu-id="63945-119">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)
