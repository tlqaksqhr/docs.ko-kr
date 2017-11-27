---
title: "속성 조건을 기반으로 UI 자동화 요소 찾기"
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
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: cafd84ce3acea80905d686f33f23338e3581a9c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>속성 조건을 기반으로 UI 자동화 요소 찾기
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 내에서 요소를 찾는 방법을 보여 주는 예제 코드는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 특정 속성 또는 속성에 기반 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 속성 조건 집합이 관심 있는 특정 요소 (또는 요소)를 식별 하는에 지정 된 <xref:System.Windows.Automation.AutomationElement> 트리 합니다. 일치 하는 모든 요소에 대 한 검색 된 다음 수행는 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 일련의 통합 하는 메서드 <xref:System.Windows.Automation.AndCondition> 부울 연산 일치 하는 요소 수를 제한 합니다.  
  
> [!NOTE]
>  검색 하는 경우는 <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, 직계 자식 항목만 가져와야 하는 것이 좋습니다. 하위 항목 검색 수백 또는 수천 개의 요소를 스택 오버플로가 발생할 수 있으므로 반복 될 수 있습니다. 낮은 수준의 특정 요소를 가져오려고 시도하는 경우, 낮은 수준의 컨테이너 또는 응용 프로그램 창에서 검색을 시작해야 합니다.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>참고 항목  
 [InvokePattern 및 ExpandCollapsePattern 메뉴 항목 샘플](http://msdn.microsoft.com/en-us/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [UI 자동화 요소 가져오기](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [AutomationID 속성 사용](../../../docs/framework/ui-automation/use-the-automationid-property.md)
