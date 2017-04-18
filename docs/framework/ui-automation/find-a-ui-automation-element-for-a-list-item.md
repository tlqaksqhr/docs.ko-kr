---
title: "Find a UI Automation Element for a List Item | Microsoft Docs"
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
  - "list items, finding elements for"
  - "elements, finding for list items"
  - "UI Automation, finding elements for List items"
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Find a UI Automation Element for a List Item
> [!NOTE]
>  이 문서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위해 작성되었습니다.  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746)을 참조하십시오.  
  
 이 항목에서는 항목의 인덱스를 알고 있을 때 목록 내 항목에서 <xref:System.Windows.Automation.AutomationElement>를 검색하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 목록에서 지정된 항목을 검색하는 두 가지 방법, 즉 <xref:System.Windows.Automation.TreeWalker>를 사용하는 방법과 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>을 사용하는 방법을 보여 줍니다.  
  
 첫 번째 기술은 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 컨트롤에 대해 더 빠른 경향이 있고 두 번째는 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] 컨트롤에 대해 더 빠릅니다.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## 참고 항목  
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)