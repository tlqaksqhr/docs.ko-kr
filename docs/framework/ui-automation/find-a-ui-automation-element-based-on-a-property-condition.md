---
title: "Find a UI Automation Element Based on a Property Condition | Microsoft Docs"
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
  - "elements, finding by property conditions"
  - "UI Automation, finding elements by property conditions"
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Find a UI Automation Element Based on a Property Condition
> [!NOTE]
>  이 문서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위해 작성되었습니다.  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746)을 참조하십시오.  
  
 이 항목에는 특정 속성을 기반으로 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 내에서 요소를 찾는 방법을 보여 주는 예제 코드가 나와 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Automation.AutomationElement> 트리에서 원하는 특정 요소를 식별하는 속성 조건 집합을 지정합니다.  그런 다음 일치하는 요소 수를 줄이기 위해 일련의 <xref:System.Windows.Automation.AndCondition> 부울 연산을 결합하는 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 메서드를 사용하여 일치하는 모든 요소를 검색하는 작업을 수행합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.AutomationElement.RootElement%2A>에서 검색하는 경우 바로 아래 자식 요소만 검색해야 합니다.  모든 하위 항목을 검색하면 수백 또는 수천 개의 요소에서 검색 작업이 반복되어 스택 오버플로가 발생할 수 있습니다.  하위 수준에 있는 특정 요소를 찾으려는 경우 하위 수준에 있는 컨테이너나 응용 프로그램 창에서 검색을 시작해야 합니다.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## 참고 항목  
 [InvokePattern and ExpandCollapsePattern Menu Item Sample](http://msdn.microsoft.com/ko-kr/b7fa141c-e2d1-4da2-a27f-81a7d1172210)   
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)   
 [Use the AutomationID Property](../../../docs/framework/ui-automation/use-the-automationid-property.md)