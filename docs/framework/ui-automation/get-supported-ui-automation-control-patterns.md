---
title: 지원되는 UI 자동화 컨트롤 패턴 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: fe492aa322f005e3bd118031e97e3837e3314093
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410194"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="257c8-102">지원되는 UI 자동화 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="257c8-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="257c8-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="257c8-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="257c8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="257c8-105">이 항목에서는에서 컨트롤 패턴 개체를 검색 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="257c8-106">모든 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="257c8-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="257c8-107">가져오기는 <xref:System.Windows.Automation.AutomationElement> 컨트롤이 포함 된 패턴이 있는에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="257c8-108">호출 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> 요소에서 모든 컨트롤 패턴을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="257c8-109">클라이언트를 사용 하지 않음을 것이 좋습니다 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="257c8-110">이 메서드를 호출 하는 대로 성능이 심각 하 게 저하 될 수 있습니다 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 기존의 각 컨트롤 패턴에 대해 내부적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="257c8-111">가능 하면 클라이언트를 호출 해야 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 키 패턴에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="257c8-112">특정 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="257c8-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="257c8-113">가져오기는 <xref:System.Windows.Automation.AutomationElement> 컨트롤이 포함 된 패턴이 있는에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="257c8-114">호출 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 또는 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 특정 패턴에 대 한 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="257c8-115">이러한 메서드는 비슷하지만, 경우에 패턴이 없는 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 예외를 발생 시키고 및 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="257c8-116">예제</span><span class="sxs-lookup"><span data-stu-id="257c8-116">Example</span></span>  
 <span data-ttu-id="257c8-117">다음 예제에서는 검색 된 <xref:System.Windows.Automation.AutomationElement> 목록 항목에 대 한 가져옵니다는 <xref:System.Windows.Automation.SelectionItemPattern> 해당 요소에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="257c8-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="257c8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="257c8-118">See Also</span></span>  
 [<span data-ttu-id="257c8-119">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="257c8-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
