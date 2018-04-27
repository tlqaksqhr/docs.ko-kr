---
title: UI 자동화 공급자의 컨트롤 패턴 지원
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
caps.latest.revision: 13
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: c66df9103b1edb43490a7e1a6a9d1a3cc87bfc28
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a>UI 자동화 공급자의 컨트롤 패턴 지원
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 클라이언트 응용 프로그램에서 데이터를 가져올 수 있도록 UI 자동화 공급자에 하나 이상의 컨트롤 패턴을 구현하는 방법을 보여 줍니다.  
  
### <a name="support-control-patterns"></a>컨트롤 패턴 지원  
  
1.  <xref:System.Windows.Automation.Provider.IInvokeProvider> 용 <xref:System.Windows.Automation.InvokePattern>와 같이 요소가 지원해야 하는 컨트롤 패턴에 사용되는 적절한 인터페이스를 구현합니다.  
  
2.  각 컨트롤 인터페이스의 구현에서의 사용자 구현을 포함 하는 개체를 반환 합니다. <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType>  
  
## <a name="example"></a>예제  
 다음 예제에서는 단일 선택 사용자 지정 목록 상자에 대한 <xref:System.Windows.Automation.Provider.ISelectionProvider> 의 구현을 보여 줍니다. 3개의 속성을 반환하고 현재 선택된 항목을 가져옵니다.  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> 를 구현하는 클래스를 반환하는 <xref:System.Windows.Automation.Provider.ISelectionProvider>의 구현을 보여 줍니다. 대부분의 목록 상자 컨트롤은 다른 패턴도 지원 하지만,이 예제는 null 참조 (`Nothing` Microsoft Visual Basic.net에서) 다른 모든 패턴 식별자에 대해 반환 됩니다.  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 공급자 개요](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [서버 쪽 UI 자동화 공급자 구현](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
