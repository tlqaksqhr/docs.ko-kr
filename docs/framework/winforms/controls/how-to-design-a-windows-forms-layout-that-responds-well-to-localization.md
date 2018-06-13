---
title: '방법: 지역화에 적합한 Windows Forms 레이아웃 디자인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: aa141319e902ff96ecfb9e9a70ca66528705418d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533880"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="fd3c7-102">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="fd3c7-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="fd3c7-103">지역화할 준비가 된 폼을 만들면 국제 시장에서 개발 속도를 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="fd3c7-104"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 <xref:System.Windows.Forms.Control.Text%2A> 속성 값 변경 때문에 컨트롤 크기가 조정될 때 정상적으로 응답하는 레이아웃을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd3c7-105">예제</span><span class="sxs-lookup"><span data-stu-id="fd3c7-105">Example</span></span>  
 <span data-ttu-id="fd3c7-106">이 폼에서는 표시된 문자열 값을 다른 언어로 번역할 때 비례하여 조정되는 레이아웃을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="fd3c7-107">이 번역 프로세스를 *지역화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="fd3c7-108">자세한 내용은 [지역화](../../../../docs/standard/globalization-localization/localization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-108">For more information, see [Localization](../../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="fd3c7-109">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="fd3c7-110">또한 [연습: 지역화를 위해 비율을 조정하는 레이아웃 만들기](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  <span data-ttu-id="fd3c7-111">[방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-111">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="fd3c7-112">[연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-112">[Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="fd3c7-113">[방법: TableLayoutPanel 컨트롤에서 행과 열 확장](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-113">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="fd3c7-114">[방법: TableLayoutPanel 컨트롤에서 열과 행 편집](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-114">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
5.  <span data-ttu-id="fd3c7-115">[연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-115">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span></span>  
  
6.  <span data-ttu-id="fd3c7-116">[연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-116">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
7.  <span data-ttu-id="fd3c7-117">[연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-117">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span></span>  
  
8.  <span data-ttu-id="fd3c7-118">[방법: AutoSize 속성과 TableLayoutPanel 컨트롤을 사용하여 Windows Forms 지역화 지원](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-118">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span></span>  
  
9. <span data-ttu-id="fd3c7-119">[연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="fd3c7-119">[Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd3c7-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fd3c7-120">Compiling the Code</span></span>  
 <span data-ttu-id="fd3c7-121">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-121">This example requires:</span></span>  
  
-   <span data-ttu-id="fd3c7-122">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="fd3c7-122">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fd3c7-123">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fd3c7-124">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-124">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="fd3c7-125">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd3c7-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3c7-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd3c7-126">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [<span data-ttu-id="fd3c7-127">지역화</span><span class="sxs-lookup"><span data-stu-id="fd3c7-127">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)
