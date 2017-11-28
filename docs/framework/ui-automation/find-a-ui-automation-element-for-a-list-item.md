---
title: "목록 항목의 UI 자동화 요소 찾기"
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
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 16016f5e5b0ab9633f9f8e4ac662838dd7936b18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>목록 항목의 UI 자동화 요소 찾기
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 검색 하는 방법을 보여 줍니다.는 <xref:System.Windows.Automation.AutomationElement> 항목의 인덱스 알려져 있는 경우 목록 내의 항목에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 사용 하 여 목록에서 지정된 된 항목을 검색 하는 두 가지 방법으로 <xref:System.Windows.Automation.TreeWalker> 및 기타 사용 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>합니다.  
  
 첫 번째 하는 방법에 대 한 더 빠른 경향이 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 는 대 한 컨트롤, 완료 되지만 두 번째 빠릅니다 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] 컨트롤입니다.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 요소 가져오기](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
