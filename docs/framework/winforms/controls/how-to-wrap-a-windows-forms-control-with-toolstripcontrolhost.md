---
title: '방법: ToolStripControlHost를 사용하여 Windows Forms 컨트롤 래핑'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: 09509705fc8e23b1b5e4fd8c67c12d0be84fc17a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538306"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="ab651-102">방법: ToolStripControlHost를 사용하여 Windows Forms 컨트롤 래핑</span><span class="sxs-lookup"><span data-stu-id="ab651-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<span data-ttu-id="ab651-103"><xref:System.Windows.Forms.ToolStripControlHost>는 <xref:System.Windows.Forms.ToolStripControlHost> 생성자를 사용하거나 <xref:System.Windows.Forms.ToolStripControlHost> 자체를 확장하여 임의 Windows Forms 컨트롤을 호스트할 수 있도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-103"><xref:System.Windows.Forms.ToolStripControlHost> is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="ab651-104"><xref:System.Windows.Forms.ToolStripControlHost>를 확장하고 컨트롤의 자주 사용되는 속성과 메서드를 노출하는 속성 및 메서드를 구현하여 컨트롤을 래핑하는 방법이 더 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="ab651-105"><xref:System.Windows.Forms.ToolStripControlHost> 수준에서 컨트롤에 대한 이벤트를 노출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="ab651-106">파생을 통해 ToolStripControlHost에서 컨트롤을 호스트하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1.  <span data-ttu-id="ab651-107"><xref:System.Windows.Forms.ToolStripControlHost>를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="ab651-108">원하는 컨트롤을 전달하는 기본 클래스 생성자를 호출하는 기본 생성자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-108">Implement a default constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2.  <span data-ttu-id="ab651-109">래핑된 컨트롤과 같은 형식의 속성을 선언하고 `Control`을 속성 접근자의 올바른 컨트롤 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3.  <span data-ttu-id="ab651-110">확장된 클래스의 속성 및 메서드와 함께 래핑된 컨트롤의 자주 사용되는 다른 속성 및 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4.  <span data-ttu-id="ab651-111">선택적으로 <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> 및 <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> 메서드를 재정의하고 노출할 컨트롤 이벤트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5.  <span data-ttu-id="ab651-112">노출할 이벤트에 필요한 래핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="ab651-113">예제</span><span class="sxs-lookup"><span data-stu-id="ab651-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab651-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ab651-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ab651-115">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-115">This example requires:</span></span>  
  
-   <span data-ttu-id="ab651-116">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="ab651-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ab651-117">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-117">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ab651-118">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab651-118">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="ab651-119">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab651-119">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab651-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab651-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripControlHost>  
 [<span data-ttu-id="ab651-121">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ab651-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="ab651-122">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ab651-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="ab651-123">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="ab651-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
