---
title: '방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e62091addfb64c287154b190f02caf1600533b3b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="8c9e5-102">방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의</span><span class="sxs-lookup"><span data-stu-id="8c9e5-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="8c9e5-103">패널의는 <xref:System.Windows.Forms.SplitContainer> 컨트롤에 중점을 두 잘 되 고 크기를 조정 하 고 사용자가 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="8c9e5-104">그러나 프로그래밍 방식으로 제어 하는 분할 하려는 됩니다 때 됩니다-여기서 배치 하 고 이동할 수 정도를 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="8c9e5-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성 및 속성에는 <xref:System.Windows.Forms.SplitContainer> 제어 요구에 맞게 사용자 인터페이스의 동작을 보다 정밀 하 게 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="8c9e5-106">이러한 속성은 다음 표에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="8c9e5-107">이름</span><span class="sxs-lookup"><span data-stu-id="8c9e5-107">Name</span></span>|<span data-ttu-id="8c9e5-108">설명</span><span class="sxs-lookup"><span data-stu-id="8c9e5-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8c9e5-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="8c9e5-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="8c9e5-110">키보드 또는 마우스를 사용 하 여 이동 가능한 분할자 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="8c9e5-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="8c9e5-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="8c9e5-112">이동할 수 있는 분할 막대를 왼쪽 또는 위쪽 가장자리에서 픽셀 거리를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="8c9e5-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="8c9e5-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="8c9e5-114">최소 거리 (픽셀)를 사용자가 분할자를 이동할 수 있는지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="8c9e5-115">아래 예에서는 수정는 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> ; "분할자 맞춤" 효과 만드는 속성 분할자를 끌 때 기본값 1이 아닌 10 픽셀의 단위로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="8c9e5-116">SplitContainer 크기 조정 동작을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="8c9e5-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="8c9e5-117">프로시저에서 설정에서 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성을 원하는 크기로 '맞추기' 결과가 분할자의 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="8c9e5-118">폼의 다음 코드 예제에서 <xref:System.Windows.Forms.Form.Load> 이벤트, 내에서 분할자는 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 끌 때 10 픽셀을 이동 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="8c9e5-119">(Visual C#) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="8c9e5-120">분할자를 왼쪽 이나 오른쪽으로 약간 이동 효과가 없습니다. 때는 뚜렷한; 그러나 마우스 포인터 되 면 두 방향에서 모두 10 픽셀, 분할자 새 위치에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="8c9e5-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9e5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c9e5-121">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
