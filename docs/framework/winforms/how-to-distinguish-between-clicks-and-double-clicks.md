---
title: "방법: 클릭과 두 번 클릭 간 구별"
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
- cpp
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4da472b4a2cb2001953758acb0f28da77f08ac70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a><span data-ttu-id="5c33d-102">방법: 클릭과 두 번 클릭 간 구별</span><span class="sxs-lookup"><span data-stu-id="5c33d-102">How to: Distinguish Between Clicks and Double-Clicks</span></span>
<span data-ttu-id="5c33d-103">일반적으로 단일 *클릭*은 UI(사용자 인터페이스) 동작을 시작하고 *두 번 클릭*은 동작을 확장합니다</span><span class="sxs-lookup"><span data-stu-id="5c33d-103">Typically, a single *click* initiates a user interface (UI) action and a *double-click* extends the action.</span></span> <span data-ttu-id="5c33d-104">예를 들어 한 번 클릭은 대개 항목을 선택하고 두 번 클릭은 선택된 항목을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-104">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="5c33d-105">그러나 Windows Forms 클릭 이벤트는 한 번 클릭과 두 번 클릭이 호환되지 않는 동작을 수행하는 시나리오에는 쉽게 적용되지 않습니다. <xref:System.Windows.Forms.Control.Click> 또는 <xref:System.Windows.Forms.Control.MouseClick> 이벤트에 연결된 동작이 <xref:System.Windows.Forms.Control.DoubleClick> 또는 <xref:System.Windows.Forms.Control.MouseDoubleClick> 이벤트에 연결된 동작 앞에 수행되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-105">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="5c33d-106">이 항목에서는 이 문제에 대한 두 가지 솔루션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-106">This topic demonstrates two solutions to this problem.</span></span> <span data-ttu-id="5c33d-107">한 솔루션은 두 번 클릭 이벤트를 처리하고 클릭 이벤트 처리 시 작업을 롤백하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-107">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="5c33d-108">드물지만 <xref:System.Windows.Forms.Control.MouseDown> 이벤트를 처리하고 <xref:System.Windows.Forms.SystemInformation> 클래스의 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 및 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 속성을 사용하여 클릭 및 두 번 클릭 동작을 시뮬레이션해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-108">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="5c33d-109">클릭 사이의 시간을 측정하고, <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 값에 도달하기 전에 두 번째 클릭이 발생하고 클릭이 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>에서 정의된 사각형 내에 있으면 두 번 클릭 동작을 수행하고, 그러지 않으면 클릭 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-109">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>  
  
### <a name="to-roll-back-a-click-action"></a><span data-ttu-id="5c33d-110">클릭 동작을 롤백하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-110">To roll back a click action</span></span>  
  
-   <span data-ttu-id="5c33d-111">작업하고 있는 컨트롤에 표준 두 번 클릭 동작이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-111">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="5c33d-112">그러지 않으면 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드로 컨트롤을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-112">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="5c33d-113">두 번 클릭 이벤트를 처리하고 두 번 클릭 동작과 클릭 동작을 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-113">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="5c33d-114">다음 코드 예제에서는 두 번 클릭이 사용되는 사용자 지정 단추를 만드는 방법과 두 번 클릭 이벤트 처리 코드에서 클릭 동작을 롤백하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-114">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a><span data-ttu-id="5c33d-115">MouseDown 이벤트에서 클릭을 구분하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-115">To distinguish between clicks in the MouseDown event</span></span>  
  
-   <span data-ttu-id="5c33d-116"><xref:System.Windows.Forms.Control.MouseDown> 이벤트를 처리하고 적절한 <xref:System.Windows.Forms.SystemInformation> 속성 및 <xref:System.Windows.Forms.Timer> 구성 요소를 사용하여 클릭 사이의 위치 및 시간 차이를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-116">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the appropriate <xref:System.Windows.Forms.SystemInformation> properties and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="5c33d-117">클릭 또는 두 번 클릭이 수행되는지에 따라 적절한 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-117">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="5c33d-118">다음 코드 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-118">The following code example demonstrates how this can be done.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c33d-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5c33d-119">Compiling the Code</span></span>  
 <span data-ttu-id="5c33d-120">이러한 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-120">These examples require:</span></span>  
  
-   <span data-ttu-id="5c33d-121">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5c33d-121">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5c33d-122">명령줄에서 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]용으로 이들 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c33d-122">For information about building these examples from the command line for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5c33d-123">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이들 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c33d-123">You can also build these examples in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] by pasting the code into new projects.</span></span>  <span data-ttu-id="5c33d-124">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c33d-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c33d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c33d-125">See Also</span></span>  
 [<span data-ttu-id="5c33d-126">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="5c33d-126">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
