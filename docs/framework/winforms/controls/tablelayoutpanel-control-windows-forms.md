---
title: "TableLayoutPanel 컨트롤(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f8f949edcf637f4b56ab0bcfdd121c5cb29e543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="40ca1-102">TableLayoutPanel 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="40ca1-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="40ca1-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 해당 내용을 표에 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="40ca1-104">레이아웃이 디자인 타임과 런타임에 모두 수행되므로 응용 프로그램 환경이 변경되면 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="40ca1-105">따라서 패널의 컨트롤이 비례적으로 크기를 조정할 수 있으므로 지역화로 인한 부모 컨트롤 크기 조정이나 텍스트 길이 변경과 같은 변경 내용에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40ca1-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="40ca1-106">In This Section</span></span>  
 [<span data-ttu-id="40ca1-107">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="40ca1-107">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="40ca1-108">행과 열이 있는 레이아웃을 만들 수 있게 해주는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 일반적인 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="40ca1-109">TableLayoutPanel 컨트롤에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="40ca1-109">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="40ca1-110"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 레이아웃 기능을 최대한 활용할 수 있게 해주는 권장 사항을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="40ca1-111">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="40ca1-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="40ca1-112"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤이 자동 크기 조정 동작을 지원하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="40ca1-113">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="40ca1-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="40ca1-114"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 자식 컨트롤을 고정 및 도킹하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="40ca1-115">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="40ca1-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="40ca1-116"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 지역화에 효과적으로 대응하는 폼을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="40ca1-117">방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="40ca1-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="40ca1-118"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 크기 조정에 효과적으로 대응하는 폼을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1.  <span data-ttu-id="40ca1-119">[방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="40ca1-119">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="40ca1-120">[방법: TableLayoutPanel 컨트롤에서 행과 열 확장](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="40ca1-120">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="40ca1-121">[방법: TableLayoutPanel 컨트롤에서 열과 행 편집](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="40ca1-121">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="40ca1-122">[연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="40ca1-122">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="40ca1-123">참조</span><span class="sxs-lookup"><span data-stu-id="40ca1-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="40ca1-124"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="40ca1-125"><xref:System.Windows.Forms.TableLayoutSettings> 형식에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="40ca1-126"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="40ca1-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="40ca1-127">Related Sections</span></span>  
 [<span data-ttu-id="40ca1-128">지역화</span><span class="sxs-lookup"><span data-stu-id="40ca1-128">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="40ca1-129">지역화와 관련된 항목의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="40ca1-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="40ca1-130">또한 참조 [응용 프로그램 지역화](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) 또는 [응용 프로그램 지역화](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="40ca1-130">Also see [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) or [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span></span>
