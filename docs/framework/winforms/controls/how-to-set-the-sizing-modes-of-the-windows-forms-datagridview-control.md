---
title: '방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
ms.openlocfilehash: 3d2ebb2b42a3e6558d5aedb207bdc4e2607d5270
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536317"
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="945dc-102">방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정</span><span class="sxs-lookup"><span data-stu-id="945dc-102">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="945dc-103">다음 절차에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 컨트롤의 특정 열에 사용할 수 있는 크기를 사용자 지정하거나 결합하는 몇 가지 일반적인 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-103">The following procedures demonstrate some common scenarios that customize or combine the sizing options available for the <xref:System.Windows.Forms.DataGridView> control and for specific columns in a control.</span></span>  
  
### <a name="to-create-a-fixed-width-column"></a><span data-ttu-id="945dc-104">고정 너비 열을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-104">To create a fixed-width column</span></span>  
  
-   <span data-ttu-id="945dc-105"><xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>으로 설정하고, <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> 속성을 <xref:System.Windows.Forms.DataGridViewTriState.False>로 설정하고, <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성을 `true`로 설정하고, <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-105">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, the <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> property to <xref:System.Windows.Forms.DataGridViewTriState.False>, the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`, and the <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> property to an appropriate value.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a><span data-ttu-id="945dc-106">콘텐츠에 맞게 크기를 조정하는 열을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-106">To create a column that adjusts its size to fit its content</span></span>  
  
-   <span data-ttu-id="945dc-107"><xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 콘텐츠 기반 크기 조정 모드로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-107">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to a content-based sizing mode.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a><span data-ttu-id="945dc-108">다양한 크기 및 중요도 값에 대한 채우기 모드 열을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-108">To create fill-mode columns for values of varying size and importance</span></span>  
  
-   <span data-ttu-id="945dc-109"><xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>로 설정하여 이 값을 재정의하지 않는 모든 열에 대한 크기 조정 코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-109">Set the <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> to set the sizing mode for all columns that do not override this value.</span></span> <span data-ttu-id="945dc-110">열의 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성을 평균 콘텐츠 너비에 비례하는 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-110">Set the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> properties of the columns to values that are proportional to their average content widths.</span></span> <span data-ttu-id="945dc-111">중요도 열의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 속성을 설정하여 부분 콘텐츠 표시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> properties of important columns to ensure partial content display.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="945dc-112">예제</span><span class="sxs-lookup"><span data-stu-id="945dc-112">Example</span></span>  
 <span data-ttu-id="945dc-113">다음 전체 코드 예제에서는 이 항목에 설명된 크기 조정 옵션을 이해하는 데 도움이 될 수 있는 데모 응용 프로그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-113">The following complete code example provides a demonstration application that can help you understand the sizing options described in this topic.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 <span data-ttu-id="945dc-114">이 데모 응용 프로그램을 사용하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-114">To use this demonstration application:</span></span>  
  
-   <span data-ttu-id="945dc-115">폼 크기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-115">Change the size of the form.</span></span> <span data-ttu-id="945dc-116"><xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 값으로 지정된 비율을 유지하면서 채우기 모드 열에서 어떻게 너비가 변경되는지 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-116">Observe how the fill-mode columns change their widths while retaining the proportions indicated by the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> property values.</span></span> <span data-ttu-id="945dc-117">폼이 너무 작을 때 열의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>가 어떻게 너비가 변경되지 않도록 방지하는지 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-117">Observe how a column's <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> prevents it from changing when the form is too small.</span></span>  
  
-   <span data-ttu-id="945dc-118">마우스로 열 구분선을 끌어서 열 크기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-118">Change the column sizes by dragging the column dividers with the mouse.</span></span> <span data-ttu-id="945dc-119">일부 열을 어떻게 크기 조정할 수 없는지, 크기 조정 가능한 열을 어떻게 최소 너비보다 더 작게 설정할 수 있는지 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-119">Observe how some columns cannot be resized, and how resizable columns cannot be made narrower than their minimum widths.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="945dc-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="945dc-120">Compiling the Code</span></span>  
 <span data-ttu-id="945dc-121">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-121">This example requires:</span></span>  
  
-   <span data-ttu-id="945dc-122">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="945dc-122">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="945dc-123">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="945dc-124">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="945dc-124">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="945dc-125">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="945dc-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945dc-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="945dc-126">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
