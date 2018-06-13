---
title: '방법: DockPanel 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], creating
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
ms.openlocfilehash: 4382314b0fe5385c158af9764ccb0067b741a693
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550152"
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="1cc46-102">방법: DockPanel 만들기</span><span class="sxs-lookup"><span data-stu-id="1cc46-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="1cc46-103">예제</span><span class="sxs-lookup"><span data-stu-id="1cc46-103">Example</span></span>  
 <span data-ttu-id="1cc46-104">다음 예제에서는 만들고의 인스턴스를 사용 하 여 <xref:System.Windows.Controls.DockPanel> 코드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc46-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="1cc46-105">이 예제에서는 5 개를 만들어 공간 분할 하는 방법을 보여 줍니다. <xref:System.Windows.Shapes.Rectangle> 요소 (도킹)를 배치 및 해당 부모 내 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc46-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="1cc46-106">기본 설정을 유지 하는 경우 마지막 사각형은 나머지 모든 할당 되지 않은 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="1cc46-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1cc46-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cc46-107">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.Dock>  
 [<span data-ttu-id="1cc46-108">패널 개요</span><span class="sxs-lookup"><span data-stu-id="1cc46-108">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
