---
title: '방법: TableLayoutPanel 컨트롤에서 행과 열 확장'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a78286be8ef64212d945b3cb11a2963d5a1b2e79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535349"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="f9e97-102">방법: TableLayoutPanel 컨트롤에서 행과 열 확장</span><span class="sxs-lookup"><span data-stu-id="f9e97-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="f9e97-103">컨트롤에 <xref:System.Windows.Forms.TableLayoutPanel> 인접 한 행과 열을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9e97-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f9e97-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f9e97-106">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9e97-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="f9e97-107">열과 행을 확장 하려면</span><span class="sxs-lookup"><span data-stu-id="f9e97-107">To span columns and rows</span></span>  
  
1.  <span data-ttu-id="f9e97-108">끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="f9e97-109">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 의 왼쪽 위 셀으로는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="f9e97-110">설정의 <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 **2**합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="f9e97-111"><xref:System.Windows.Forms.Button> 컨트롤 첫 번째와 두 번째 열으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4.  <span data-ttu-id="f9e97-112">설정의 <xref:System.Windows.Forms.Button> 컨트롤의 **RowSpan** 속성을 **2**합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="f9e97-113"><xref:System.Windows.Forms.Button> 삽입할 첫 번째와 두 번째 행에 걸쳐 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5.  <span data-ttu-id="f9e97-114">설정의 <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 **1**합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="f9e97-115"><xref:System.Windows.Forms.Button> 컨트롤 첫 번째 열으로 이동 하 고 첫 번째 및 두 번째 행을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e97-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e97-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9e97-116">See Also</span></span>  
 [<span data-ttu-id="f9e97-117">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f9e97-117">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
