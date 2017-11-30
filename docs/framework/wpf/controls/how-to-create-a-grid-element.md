---
title: "방법: Grid 요소 만들기"
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
helpviewer_keywords: Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd9614aee6e2bf7085b2fbee77993217439320a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="a7139-102">방법: Grid 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="a7139-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="a7139-103">예제</span><span class="sxs-lookup"><span data-stu-id="a7139-103">Example</span></span>  
 <span data-ttu-id="a7139-104">만들고의 인스턴스를 사용 하는 방법을 보여 주는 다음 예제 <xref:System.Windows.Controls.Grid> 중 하나를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a7139-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="a7139-105">이 예에서는 세 개의 <xref:System.Windows.Controls.ColumnDefinition> 개체 및 3 <xref:System.Windows.Controls.RowDefinition> 를 9 개까지 포함 하는 표의 만드는 셀, 워크시트와 같이 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a7139-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="a7139-106">각 셀을 포함 한 <xref:System.Windows.Controls.TextBlock> 데이터 및 맨 위 행을 나타내는 요소에 포함 되어는 <xref:System.Windows.Controls.TextBlock> 와 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 적용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a7139-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="a7139-107">각 셀의 경계를 표시 하는 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7139-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a7139-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7139-108">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="a7139-109">패널 개요</span><span class="sxs-lookup"><span data-stu-id="a7139-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
