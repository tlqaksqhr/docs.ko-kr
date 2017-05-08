---
title: "Get UI Automation Element Properties | Microsoft Docs"
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
  - "properties, retrieving"
  - "UI Automation, retrieving properties of elements"
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Get UI Automation Element Properties
> [!NOTE]
>  이 문서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위해 작성되었습니다.  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746)을 참조하십시오.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소의 속성을 검색하는 방법을 보여 줍니다.  
  
### 현재 속성 값 가져오기  
  
1.  가져올 속성 값의 <xref:System.Windows.Automation.AutomationElement>를 가져옵니다.  
  
2.  <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>를 호출하거나 <xref:System.Windows.Automation.AutomationElement.Current%2A> 속성 구조체를 검색하여 해당 멤버 중 하나에서 값을 가져옵니다.  
  
### 캐시된 속성 값 가져오기  
  
1.  가져올 속성 값의 <xref:System.Windows.Automation.AutomationElement>를 가져옵니다.  이 속성은 <xref:System.Windows.Automation.CacheRequest>에 지정되어 있어야 합니다.  
  
2.  <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>를 호출하거나 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 속성 구조체를 검색하여 해당 멤버 중 하나에서 값을 가져옵니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Automation.AutomationElement>의 현재 속성을 검색하는 여러 방법을 보여 줍니다.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## 참고 항목  
 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [Caching in UI Automation Clients](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)