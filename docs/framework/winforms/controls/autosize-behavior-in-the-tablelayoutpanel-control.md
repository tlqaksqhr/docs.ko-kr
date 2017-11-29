---
title: "TableLayoutPanel 컨트롤의 AutoSize 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d4813b7bd37c0c5bd9b04b37cb825067b35ce3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="6cbde-102">TableLayoutPanel 컨트롤의 AutoSize 동작</span><span class="sxs-lookup"><span data-stu-id="6cbde-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="6cbde-103">고유 AutoSize 동작</span><span class="sxs-lookup"><span data-stu-id="6cbde-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="6cbde-104"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 다음과 같은 방법으로 자동 크기 조정 동작을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
-   <span data-ttu-id="6cbde-105">통해는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="6cbde-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
-   <span data-ttu-id="6cbde-106">통해는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="6cbde-107">행과 열 스타일을 사용 하 여 AutoSize 속성</span><span class="sxs-lookup"><span data-stu-id="6cbde-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="6cbde-108">다음 표에서 설명 간의 상호 작용은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="6cbde-109">자동 크기 조정 설정</span><span class="sxs-lookup"><span data-stu-id="6cbde-109">AutoSize setting</span></span>|<span data-ttu-id="6cbde-110">스타일 상호 작용</span><span class="sxs-lookup"><span data-stu-id="6cbde-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="6cbde-111"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 왼쪽에서 오른쪽으로 진행 하 고 다음과 같은 순서로 또는 열 이나 행에 대 한 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="6cbde-112">1.  경우는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성이 <xref:System.Windows.Forms.SizeType.Absolute>, 하 여 지정 된 픽셀 수 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="6cbde-113">2.  경우는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성이 <xref:System.Windows.Forms.SizeType.AutoSize>, 자식 컨트롤에 의해 반환 되는 픽셀 수가 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="6cbde-114">3.  모든 공간 후 <xref:System.Windows.Forms.SizeType.Absolute> 및 <xref:System.Windows.Forms.SizeType.AutoSize> 열 이나 행은 할당 된 모든 열 이나 행으로 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 로 설정 <xref:System.Windows.Forms.SizeType.Percent> 비례적으로 남은 공간을 할당 하는 데 사용 됩니다</span><span class="sxs-lookup"><span data-stu-id="6cbde-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="6cbde-115">위의 상호 예외와 유사한는 <xref:System.Windows.Forms.SizeType.Percent> 열 이나 행 획득 한 자동 크기 조정 끝점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="6cbde-116"><xref:System.Windows.Forms.TableLayoutPanel> 열 이나 행 충분 한 여유 공간을 확보할 컨트롤이 확장 되어 있도록 없는 열 이나 행으로 <xref:System.Windows.Forms.SizeType.Percent> 스타일 지정에는 해당 내용이 잘리지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="6cbde-117"><xref:System.Windows.Forms.TableLayoutPanel> 비율에 따라 새 공간을 할당 하는 컨트롤의 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbde-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cbde-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cbde-118">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="6cbde-119">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6cbde-119">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
