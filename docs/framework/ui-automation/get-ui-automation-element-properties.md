---
title: "UI 자동화 요소 속성 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f3fcbb25fab616b60a1f60d9443af13b60f2d27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="7c774-102">UI 자동화 요소 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="7c774-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="7c774-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c774-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7c774-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c774-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7c774-105">이 항목에서는의 속성을 검색 하는 방법을 보여 줍니다.는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7c774-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="7c774-106">현재 속성 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="7c774-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="7c774-107">가져올는 <xref:System.Windows.Automation.AutomationElement> 가져오려면 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c774-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="7c774-108">호출 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, 검색 또는 <xref:System.Windows.Automation.AutomationElement.Current%2A> 속성 구조 및 해당 멤버 중 하나에서 값 가져오기.</span><span class="sxs-lookup"><span data-stu-id="7c774-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="7c774-109">캐시 된 속성 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="7c774-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="7c774-110">가져올는 <xref:System.Windows.Automation.AutomationElement> 가져오려면 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c774-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="7c774-111">속성에 지정 되어 있어야는 <xref:System.Windows.Automation.CacheRequest>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c774-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="7c774-112">호출 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, 검색 또는 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 속성 구조 및 해당 멤버 중 하나에서 값 가져오기.</span><span class="sxs-lookup"><span data-stu-id="7c774-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c774-113">예</span><span class="sxs-lookup"><span data-stu-id="7c774-113">Example</span></span>  
 <span data-ttu-id="7c774-114">다음 예에서는 현재 속성을 검색 하는 방법을 보여 주는 <xref:System.Windows.Automation.AutomationElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c774-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="7c774-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c774-115">See Also</span></span>  
 [<span data-ttu-id="7c774-116">클라이언트의 UI 자동화 속성</span><span class="sxs-lookup"><span data-stu-id="7c774-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="7c774-117">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="7c774-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="7c774-118">UI 자동화 클라이언트의 캐싱</span><span class="sxs-lookup"><span data-stu-id="7c774-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
