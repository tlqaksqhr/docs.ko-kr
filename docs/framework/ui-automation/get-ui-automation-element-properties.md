---
title: UI 자동화 요소 속성 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 73678433692f5532f712f0d2c7a3c5bf138a87b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="get-ui-automation-element-properties"></a>UI 자동화 요소 속성 가져오기
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는의 속성을 검색 하는 방법을 보여 줍니다.는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소입니다.  
  
### <a name="get-a-current-property-value"></a>현재 속성 값 가져오기  
  
1.  가져올는 <xref:System.Windows.Automation.AutomationElement> 가져오려면 속성이 있습니다.  
  
2.  호출 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, 검색 또는 <xref:System.Windows.Automation.AutomationElement.Current%2A> 속성 구조 및 해당 멤버 중 하나에서 값 가져오기.  
  
### <a name="get-a-cached-property-value"></a>캐시 된 속성 값 가져오기  
  
1.  가져올는 <xref:System.Windows.Automation.AutomationElement> 가져오려면 속성이 있습니다. 속성에 지정 되어 있어야는 <xref:System.Windows.Automation.CacheRequest>합니다.  
  
2.  호출 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, 검색 또는 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 속성 구조 및 해당 멤버 중 하나에서 값 가져오기.  
  
## <a name="example"></a>예제  
 다음 예에서는 현재 속성을 검색 하는 방법을 보여 주는 <xref:System.Windows.Automation.AutomationElement>합니다.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>참고 항목  
 [클라이언트의 UI 자동화 속성](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [UI 자동화의 캐싱 사용](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [UI 자동화 클라이언트의 캐싱](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
