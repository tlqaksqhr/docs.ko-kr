---
title: "지원되는 UI 자동화 컨트롤 패턴 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "컨트롤 패턴 가져오기"
  - "UI 자동화 컨트롤 패턴 가져오기"
  - "컨트롤 패턴 가져오기"
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: 10
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 10
---
# 지원되는 UI 자동화 컨트롤 패턴 가져오기
> [!NOTE]
>  이 설명서는 관리 되는 사용 하려는.NET Framework 개발자를 위한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 정의 된 클래스는 <xref:System.Windows.Automation> 네임 스페이스입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 참조 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에서는에서 컨트롤 패턴 개체를 검색 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소입니다.  
  
### <a name="obtain-all-control-patterns"></a>모든 컨트롤 패턴 가져오기  
  
1.  가져오기는 <xref:System.Windows.Automation.AutomationElement> 관심 있는 컨트롤이 포함 된 패턴이 있습니다.  
  
2.  호출 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> 요소에서 모든 컨트롤 패턴을 얻을 수 있습니다.  
  
> [!CAUTION]
>  클라이언트를 사용 하지 않도록 것이 좋습니다 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>합니다. 이 메서드를 호출 하는 대로 성능이 심각 하 게 저하 될 수 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 각 기존 컨트롤 패턴에 대해 내부적으로 합니다. 가능한 경우 클라이언트를 호출 해야 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 관심의 핵심 패턴에 있습니다.  
  
### <a name="obtain-a-specific-control-pattern"></a>특정 컨트롤 패턴 가져오기  
  
1.  가져오기는 <xref:System.Windows.Automation.AutomationElement> 관심 있는 컨트롤이 포함 된 패턴이 있습니다.  
  
2.  호출 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 또는 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 특정 패턴에 대 한 쿼리입니다. 이러한 방법은 서로 비슷하지만 패턴이 없으면 하지만 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 에서 예외가 발생 하 고 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 반환 `false`.  
  
## <a name="example"></a>예제  
 다음 예제에서는 검색 된 <xref:System.Windows.Automation.AutomationElement> 목록 항목에 대 한 가져옵니다는 <xref:System.Windows.Automation.SelectionItemPattern> 해당 요소에서.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>참고 항목  
 [클라이언트에 대 한 UI 자동화 컨트롤 패턴](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)