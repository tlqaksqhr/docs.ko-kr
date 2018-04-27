---
title: '방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정'
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
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 579d63da8a411e47c649695c0a09d4cf519b4410
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8e45f-102">방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8e45f-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8e45f-103"><xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 이벤트를 하나 또는 둘 다 처리하여 <xref:System.Windows.Forms.DataGridView> 행의 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="8e45f-104">이들 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 나머지 부분을 그리게 하는 동안 원하는 부분만 그릴 수 있도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="8e45f-105">예를 들어 사용자 지정 배경을 그리려면 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 이벤트를 처리하고 개별 셀이 자체 전경 콘텐츠를 그리도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="8e45f-106">또는 셀이 자신을 그리고 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 이벤트에 대한 처리기에서 사용자 지정 전경 콘텐츠를 추가하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="8e45f-107">셀 그리기를 사용하지 않도록 설정하고 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 이벤트 처리에서 직접 모든 부분을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="8e45f-108">다음 코드 예제에서는 여러 열에 걸쳐 있는 그라데이션 선택 배경 및 일부 사용자 지정 전경 콘텐츠를 제공하려고 두 이벤트 모두에 대한 처리기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e45f-109">예제</span><span class="sxs-lookup"><span data-stu-id="8e45f-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e45f-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8e45f-110">Compiling the Code</span></span>  
 <span data-ttu-id="8e45f-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="8e45f-112">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8e45f-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8e45f-113">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8e45f-114">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e45f-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="8e45f-115">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e45f-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e45f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e45f-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [<span data-ttu-id="8e45f-117">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8e45f-117">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="8e45f-118">DataGridView 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="8e45f-118">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)
