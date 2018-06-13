---
title: UI 자동화 공급자의 컨트롤 패턴 지원
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0c7ca4507ce5e7d2f6f295caace23134a8a6d492
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398995"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="bc99d-102">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="bc99d-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="bc99d-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bc99d-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc99d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="bc99d-105">이 항목에서는 클라이언트 응용 프로그램에서 데이터를 가져올 수 있도록 UI 자동화 공급자에 하나 이상의 컨트롤 패턴을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="bc99d-106">컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="bc99d-106">Support Control Patterns</span></span>  
  
1.  <span data-ttu-id="bc99d-107"><xref:System.Windows.Automation.Provider.IInvokeProvider> 용 <xref:System.Windows.Automation.InvokePattern>와 같이 요소가 지원해야 하는 컨트롤 패턴에 사용되는 적절한 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2.  <span data-ttu-id="bc99d-108">각 컨트롤 인터페이스의 구현에서의 사용자 구현을 포함 하는 개체를 반환 합니다. <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bc99d-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="bc99d-109">예제</span><span class="sxs-lookup"><span data-stu-id="bc99d-109">Example</span></span>  
 <span data-ttu-id="bc99d-110">다음 예제에서는 단일 선택 사용자 지정 목록 상자에 대한 <xref:System.Windows.Automation.Provider.ISelectionProvider> 의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="bc99d-111">3개의 속성을 반환하고 현재 선택된 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="bc99d-112">예제</span><span class="sxs-lookup"><span data-stu-id="bc99d-112">Example</span></span>  
 <span data-ttu-id="bc99d-113">다음 예제에서는 <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> 를 구현하는 클래스를 반환하는 <xref:System.Windows.Automation.Provider.ISelectionProvider>의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="bc99d-114">대부분의 목록 상자 컨트롤은 다른 패턴도 지원 하지만,이 예제는 null 참조 (`Nothing` Microsoft Visual Basic.net에서) 다른 모든 패턴 식별자에 대해 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc99d-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="bc99d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc99d-115">See Also</span></span>  
 [<span data-ttu-id="bc99d-116">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="bc99d-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="bc99d-117">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="bc99d-117">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
