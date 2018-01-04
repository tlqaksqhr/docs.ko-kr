---
title: "GridView 열 머리글 스타일 및 템플릿 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 996d6d5f531a866d4fc80acc3848cdf264901032
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a><span data-ttu-id="d300b-102">GridView 열 머리글 스타일 및 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="d300b-102">GridView Column Header Styles and Templates Overview</span></span>
<span data-ttu-id="d300b-103">이 개요에서는의 열 머리글에 사용자 지정 하는 속성에 대 한 우선 순위는 <xref:System.Windows.Controls.GridView> 의 보기 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-103">This overview discusses the order of precedence for properties that you use to customize a column header in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="customizing-a-column-header-in-a-gridview"></a><span data-ttu-id="d300b-104">GridView에서 열 머리글을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d300b-104">Customizing a Column Header in a GridView</span></span>  
 <span data-ttu-id="d300b-105">내용, 레이아웃 및 열 머리글의 스타일을 정의 하는 속성은 <xref:System.Windows.Controls.GridView> 여러 관련된 클래스에는 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-105">The properties that define the content, layout, and style of a column header in a <xref:System.Windows.Controls.GridView> are found on many related classes.</span></span> <span data-ttu-id="d300b-106">이러한 속성 중 일부는 동일 하거나 유사한 기능을 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-106">Some of these properties have functionality that is similar or the same.</span></span>  
  
 <span data-ttu-id="d300b-107">다음 테이블에 행 그룹은 동일한 기능을 수행 하는 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-107">The rows in the following table show groups of properties that perform the same function.</span></span> <span data-ttu-id="d300b-108">열 머리글을 사용자 지정 하려면 이러한 속성을 사용할 수는 <xref:System.Windows.Controls.GridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-108">You can use these properties to customize the column headers in a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="d300b-109">가장 멀리 오른쪽 열에 속성의 가장 높은 우선 순위에 있는 오른쪽에서 왼쪽으로의 관련된 속성에 대 한 우선 순위는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-109">The order of precedence for related properties is from right to left where the property in the farthest right column has the highest precedence.</span></span> <span data-ttu-id="d300b-110">예를 들어 경우는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 에 설정 되어는 <xref:System.Windows.Controls.GridViewColumnHeader> 개체 및 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> 연결 설정 <xref:System.Windows.Controls.GridViewColumn>, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 우선적으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-110">For example, if a <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> is set on the <xref:System.Windows.Controls.GridViewColumnHeader> object and the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> is set on the associated <xref:System.Windows.Controls.GridViewColumn>, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> takes precedence.</span></span> <span data-ttu-id="d300b-111">이 시나리오는 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-111">In this scenario, the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> has no effect.</span></span>  
  
 <span data-ttu-id="d300b-112">**GridView에서 열 머리글에 대 한 관련된 속성**</span><span class="sxs-lookup"><span data-stu-id="d300b-112">**Related properties for column headers in a GridView**</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="d300b-113">**클래스**</span><span class="sxs-lookup"><span data-stu-id="d300b-113">**Classes**</span></span>|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|<span data-ttu-id="d300b-114">**상황에 맞는 메뉴 속성**</span><span class="sxs-lookup"><span data-stu-id="d300b-114">**Context Menu Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|<span data-ttu-id="d300b-115">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d300b-115">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|<span data-ttu-id="d300b-116">**ToolTip**</span><span class="sxs-lookup"><span data-stu-id="d300b-116">**ToolTip**</span></span><br /><br /> <span data-ttu-id="d300b-117">**속성**</span><span class="sxs-lookup"><span data-stu-id="d300b-117">**Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|<span data-ttu-id="d300b-118">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d300b-118">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|<span data-ttu-id="d300b-119">**헤더 서식 파일**</span><span class="sxs-lookup"><span data-stu-id="d300b-119">**Header Template**</span></span><br /><br /> <span data-ttu-id="d300b-120">**속성**</span><span class="sxs-lookup"><span data-stu-id="d300b-120">**Properties**</span></span>|<span data-ttu-id="d300b-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="d300b-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<span data-ttu-id="d300b-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="d300b-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<span data-ttu-id="d300b-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="d300b-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|<span data-ttu-id="d300b-124">**스타일 속성**</span><span class="sxs-lookup"><span data-stu-id="d300b-124">**Style Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <span data-ttu-id="d300b-125"><sup>1</sup>에 대 한 **헤더 템플릿 속성**템플릿을 템플릿 선택기 속성, 서식 파일 속성은 우선 순위를 설정 하는 경우, 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-125"><sup>1</sup>For **Header Template Properties**, if you set both the template and template selector properties, the template property takes precedence.</span></span> <span data-ttu-id="d300b-126">예를 들어, 모두 설정 하면는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 속성는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-126">For example, if you set both the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d300b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d300b-127">See Also</span></span>  
 [<span data-ttu-id="d300b-128">방법 항목</span><span class="sxs-lookup"><span data-stu-id="d300b-128">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="d300b-129">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="d300b-129">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="d300b-130">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="d300b-130">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
