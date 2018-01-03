---
title: "UI 자동화의 캐싱 사용"
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
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 808ba16cbacfad2cc255ae40e2cbad3178350afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="use-caching-in-ui-automation"></a>UI 자동화의 캐싱 사용
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 섹션에서는 <xref:System.Windows.Automation.AutomationElement> 속성 및 컨트롤 패턴의 캐싱을 구현하는 방법을 보여줍니다.  
  
### <a name="activate-a-cache-request"></a>캐시 요청 활성화  
  
1.  <xref:System.Windows.Automation.CacheRequest>를 만듭니다.  
  
2.  <xref:System.Windows.Automation.CacheRequest.Add%2A>를 사용하여 속성 및 패턴을 캐시에 지정합니다.  
  
3.  <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> 속성을 설정하여 캐시 범위를 지정합니다.  
  
4.  <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> 속성을 설정하여 하위 트리의 뷰를 지정합니다.  
  
5.  개체에 대한 전체 참조를 검색하지 않음으로써 효율성을 높이려는 경우 <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> 속성을 <xref:System.Windows.Automation.AutomationElementMode.None> 으로 설정합니다. (이렇게 하면 해당 개체에서 현재 값을 검색할 수 없습니다.)  
  
6.  <xref:System.Windows.Automation.CacheRequest.Activate%2A> 블록의 `using` 를 사용하여(`Using` 의 [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]) 요청을 활성화합니다.  
  
 <xref:System.Windows.Automation.AutomationElement> 개체를 가져오거나 이벤트를 구독한 후, <xref:System.Windows.Automation.CacheRequest.Pop%2A> ( <xref:System.Windows.Automation.CacheRequest.Push%2A> 가 사용된 경우)를 사용하거나 <xref:System.Windows.Automation.CacheRequest.Activate%2A>에서 생성된 개체를 삭제하여 요청을 비활성화합니다. ( <xref:System.Windows.Automation.CacheRequest.Activate%2A> 블록의 `using` 를 사용합니다(`Using` 의 [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)])).  
  
### <a name="cache-automationelement-properties"></a>AutomationElement 속성 캐시  
  
1.  <xref:System.Windows.Automation.CacheRequest> 가 활성 상태인 동안 <xref:System.Windows.Automation.AutomationElement> 또는 <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 을 사용하여 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>개체를 가져옵니다. 또는 <xref:System.Windows.Automation.AutomationElement> 가 활성 상태였을 때 등록한 이벤트의 소스로 <xref:System.Windows.Automation.CacheRequest> 를 가져옵니다. ( <xref:System.Windows.Automation.CacheRequest> 를 GetUpdatedCache 또는 <xref:System.Windows.Automation.TreeWalker> 메서드 중 하나에 전달하여 캐시를 만들 수도 있습니다.)  
  
2.  <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> 를 사용하거나 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 의 <xref:System.Windows.Automation.AutomationElement>속성에서 속성을 검색합니다.  
  
### <a name="obtain-cached-patterns-and-their-properties"></a>캐시된 패턴 및 해당 속성 가져오기  
  
1.  <xref:System.Windows.Automation.CacheRequest> 가 활성 상태인 동안 <xref:System.Windows.Automation.AutomationElement> 또는 <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 을 사용하여 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>개체를 가져옵니다. 또는 <xref:System.Windows.Automation.AutomationElement> 가 활성 상태였을 때 등록한 이벤트의 소스로 <xref:System.Windows.Automation.CacheRequest> 를 가져옵니다. ( <xref:System.Windows.Automation.CacheRequest> 를 GetUpdatedCache 또는 <xref:System.Windows.Automation.TreeWalker> 메서드 중 하나에 전달하여 캐시를 만들 수도 있습니다.)  
  
2.  <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> 또는 <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> 을 사용하여 캐시된 패턴을 검색합니다.  
  
3.  컨트롤 패턴의 `Cached` 속성에서 속성 값을 검색합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제는 <xref:System.Windows.Automation.CacheRequest.Activate%2A> 를 사용하여 <xref:System.Windows.Automation.CacheRequest>를 활성화하는 캐싱의 다양한 측면을 보여줍니다.  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a>예  
 다음 코드 예제는 <xref:System.Windows.Automation.CacheRequest.Push%2A> 를 사용하여 <xref:System.Windows.Automation.CacheRequest>를 활성화하는 캐싱의 다양한 측면을 보여줍니다. 캐시 요청을 중첩하려는 경우를 제외하고, <xref:System.Windows.Automation.CacheRequest.Activate%2A>를 사용하는 것이 좋습니다.  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 클라이언트의 캐싱](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
