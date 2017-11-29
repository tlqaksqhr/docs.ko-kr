---
title: "방법: Grid를 사용하여 표준 UI 대화 상자 빌드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 641e74d8c9f8db1afde19c008de08f0029b0bf90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="00c04-102">방법: Grid를 사용하여 표준 UI 대화 상자 빌드</span><span class="sxs-lookup"><span data-stu-id="00c04-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="00c04-103">이 예제에서는 한 표준을 만들 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 대화 상자를 사용 하 여는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="00c04-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c04-104">예제</span><span class="sxs-lookup"><span data-stu-id="00c04-104">Example</span></span>  
 <span data-ttu-id="00c04-105">다음 예제에서는 같은 대화 상자가 **실행** 대화 상자에는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="00c04-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="00c04-106">이 예에서는 만듭니다는 <xref:System.Windows.Controls.Grid> 사용 하 여는 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 5 개의 열과 4 개의 행을 정의 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="00c04-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="00c04-107">이 예제에서는 다음 추가 하 고 배치는 <xref:System.Windows.Controls.Image>, `RunIcon.png`대화 상자에서 발견 되는 이미지를 나타내기 위해.</span><span class="sxs-lookup"><span data-stu-id="00c04-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="00c04-108">이미지가 첫 번째 열과 행에 배치 되는 <xref:System.Windows.Controls.Grid> (왼쪽 위 모퉁이).</span><span class="sxs-lookup"><span data-stu-id="00c04-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="00c04-109">이 예제에서는 추가 하는 다음으로 <xref:System.Windows.Controls.TextBlock> 첫 번째 행의 나머지 열을 포함 하는 첫 번째 열에는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="00c04-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="00c04-110">다른 추가 <xref:System.Windows.Controls.TextBlock> 두 번째 행을 나타내는 첫 번째 열에는 요소는 **열려** 입력란.</span><span class="sxs-lookup"><span data-stu-id="00c04-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="00c04-111">A <xref:System.Windows.Controls.TextBlock> 다음과 데이터 입력 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00c04-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="00c04-112">이 예에서는 세 개의 추가 마지막으로, <xref:System.Windows.Controls.Button> 은 마지막 행을 나타내는 요소는 **확인**, **취소**, 및 **찾아보기** 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="00c04-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="00c04-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00c04-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [<span data-ttu-id="00c04-114">패널 개요</span><span class="sxs-lookup"><span data-stu-id="00c04-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="00c04-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="00c04-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
