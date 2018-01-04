---
title: "TableLayoutPanel 컨트롤 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 614887524a49e1163b3049111895166995fdace4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="20ffd-102">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="20ffd-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="20ffd-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 해당 내용을 표에 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="20ffd-104">레이아웃이 디자인 타임과 런타임에 모두 수행되므로 응용 프로그램 환경이 변경되면 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="20ffd-105">따라서 패널의 컨트롤이 비례적으로 크기를 조정할 수 있으므로 지역화로 인한 부모 컨트롤 크기 조정이나 텍스트 길이 변경과 같은 변경 내용에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="20ffd-106">Windows Forms 컨트롤은 <xref:System.Windows.Forms.TableLayoutPanel>의 다른 인스턴스를 포함하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 자식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="20ffd-107">따라서 런타임에 변경 내용에 맞게 조정되는 정교한 레이아웃을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="20ffd-108"><xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 속성의 값에 따라 새 컨트롤을 추가할 때 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 이를 수용하기 위해 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="20ffd-109"><xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 또는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 속성의 값을 0으로 설정하면 <xref:System.Windows.Forms.TableLayoutPanel>이 해당 방향으로 바인딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="20ffd-110"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 자식 컨트롤로 가득 찬 후에 확장 방향(가로 또는 세로)을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="20ffd-111">기본적으로 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 행을 추가하여 아래로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="20ffd-112">기본 동작과 다르게 동작하는 행과 열을 원하는 경우 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 속성을 사용하여 행과 열의 속성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="20ffd-113">행 또는 열의 속성을 개별적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="20ffd-114"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 자식 컨트롤에 `Cell`, `Column`, `Row`, `ColumnSpan` 및 `RowSpan` 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="20ffd-115">자식 컨트롤의 `ColumnSpan` 또는 `RowSpan` 속성을 설정하여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 셀을 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ffd-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  <span data-ttu-id="20ffd-116">[방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="20ffd-116">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="20ffd-117">[방법: TableLayoutPanel 컨트롤에서 행과 열 확장](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="20ffd-117">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="20ffd-118">[방법: TableLayoutPanel 컨트롤에서 열과 행 편집](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="20ffd-118">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="20ffd-119">[연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="20ffd-119">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ffd-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20ffd-120">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [<span data-ttu-id="20ffd-121">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="20ffd-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="20ffd-122">방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="20ffd-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [<span data-ttu-id="20ffd-123">TableLayoutPanel 컨트롤에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="20ffd-123">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
