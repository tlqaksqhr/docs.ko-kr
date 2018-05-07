---
title: UI 자동화 트리 개요
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0823a569b19d46f32c1cb780470a935f20429c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-tree-overview"></a>UI 자동화 트리 개요
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 탐색 보조 기술 제품 및 테스트 스크립트는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 대 한 정보를 수집 하는 트리는 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 와 해당 요소입니다.  
  
 내에서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 있습니다 트리는 루트 요소 (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>)는 현재 데스크톱을 나타내고 자식 요소가 응용 프로그램 창을 나타내는입니다. 조각을 나타내는 요소가 포함 될 수 있습니다 이러한 각각의 자식 요소 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 메뉴, 단추, 도구 모음, 목록 상자 등입니다. 따라서 이러한 요소에 목록 항목 등과 같은 요소가 포함될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리는 고정된 구조 아니며 표시 되는 드뭅니다 아니며에서 수많은 요소가 포함 될 수 있기 때문에 있습니다. 트리의 일부는 필요 시에 빌드되며 요소가 추가, 이동 또는 제거될 때 변경될 수 있습니다.  
  
 UI 자동화 공급자는 조각 내에서 항목 간 탐색을 구현하여 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리를 지원하며, 이 트리는 루트(일반적으로 창에서 호스트됨) 및 하위 트리로 구성되어 있습니다. 그러나 공급자에서 컨트롤 간의 탐색은 문제가 되지 않습니다. 에 의해 관리는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 핵심 기본 창 공급자에서 정보를 사용 하 여 합니다.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>자동화 트리 보기  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 항목만 포함 하는 뷰를 트리를 필터링 할 수 <xref:System.Windows.Automation.AutomationElement> 특정 클라이언트와 관련 된 개체입니다. 이 접근 방식을 통해 클라이언트를 통해 표시 되는 구조를 사용자 지정할 수 있습니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 자신의 필요에 있습니다.  
  
 클라이언트는 범위 지정과 필터링 두 가지 방법으로 뷰를 사용자 지정할 수 있습니다. 범위 지정은 기본 요소를 시작으로 뷰의 범위를 정의하는 것입니다. 예를 들어, 응용 프로그램에서 데스크톱의 직계 자식만 검색하거나 응용 프로그램 창의 모든 하위 항목을 검색할 수 있습니다. 필터링은 뷰에 포함되는 요소의 형식을 정의하는 것입니다.  
  
 UI 자동화 공급자는 <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> 및 <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> 속성을 포함하여 요소의 속성을 정의하여 필터링을 지원합니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 3 개의 기본 뷰를 제공합니다. 이러한 뷰는 수행된 필터링의 형식에 따라 정의되며, 뷰의 범위는 응용 프로그램에서 정의됩니다. 또한 응용 프로그램은 속성에 다른 필터를 적용할 수 있습니다(예: 컨트롤 뷰에서 활성화된 컨트롤만 포함되도록 필터링).  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Raw 뷰  
 원시 보기가 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 전체 트리는 <xref:System.Windows.Automation.AutomationElement> 데스크톱은 루트 개체입니다. Raw 뷰는 응용 프로그램의 기본 프로그래밍 방식의 구조를 엄격히 따르기 때문에 가장 자세한 뷰를 사용할 수 있습니다. 트리의 다른 뷰가 빌드되는 기준이기도 합니다. 이 보기는 내부에 따라 달라 지므로 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 프레임 워크의 원시 보기가 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 단추 보다와 다른 raw 뷰가 갖습니다는 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 단추입니다.  
  
 속성을 지정 하지 않고 요소를 검색 하거나 사용 하 여 가져온 raw 뷰는 <xref:System.Windows.Automation.TreeWalker.RawViewWalker> 트리를 탐색 합니다.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>컨트롤 뷰  
 컨트롤 뷰는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 설명 하는 보조 기술 제품의 작업을 간소화 하는 트리는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 최종 사용자와 수 있도록 지 원하는 최종 사용자 응용 프로그램과 상호 작용에 밀접 하 게 매핑되기 때문에 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 구조 최종 사용자가 인식 합니다.  
  
 컨트롤 뷰는 Raw 뷰의 하위 집합입니다. 모든 포함 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 최종 사용자가 대화형으로 이해 하거나 컨트롤의 논리 구조에 기여 하는 raw 뷰의 항목에서 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]합니다. 예 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 의 논리 구조에 기여 하는 항목은 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], 하지만 대화형이 아닌,는 목록 뷰 헤더, 도구 모음, 메뉴 및 상태 표시줄 같은 항목 컨테이너가 있습니다. 레이아웃 또는 장식용으로만 사용되는 비대화형 항목은 컨트롤 뷰에 표시되지 않습니다. 대화 상자에서 컨트롤을 레이아웃하는 데만 사용되고 정보가 포함되어 있지 않은 패널을 예로 들 수 있습니다. 컨트롤 뷰에 표시되는 비대화형 항목으로는 대화 상자에서 정보 및 정적 텍스트가 포함된 그래픽이 있습니다. 컨트롤 뷰에 포함된 비대화형 항목은 키보드 포커스를 받을 수 없습니다.  
  
 요소를 검색 하 여 가져온 컨트롤 뷰는 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> 속성이로 설정 `true`, 또는 사용 하 여는 <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> 트리를 탐색 합니다.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>콘텐츠 뷰  
 콘텐츠 뷰는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 뷰의 하위 집합입니다. 포함 된 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 사용자 인터페이스에서 실제 정보를 전달 하는 항목 포함 하 여 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 받을 수 있는 항목에 키보드 포커스와에 평균 값이 텍스트는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 항목입니다. 예를 들어, 드롭다운 콤보 상자의 값은 최종 사용자가 사용하는 정보를 나타내므로 콘텐츠 뷰에 나타납니다. 콘텐츠 뷰에서, 콤보 상자와 목록 상자 둘 다으로 표시 되며의 컬렉션 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 항목 한 개 또는 여러 개 항목을 선택할 수 있습니다. 상자 하나는 항상 열려 있고 다른 하나를 확장하고 축소할 수 있다는 점은 콘텐츠 뷰와 관련이 없습니다. 이 뷰는 사용자에게 표시되는 데이터 또는 내용을 보여주도록 설계되어 있기 때문입니다.  
  
 콘텐츠 뷰 요소를 검색 하 여 가져온는 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> 속성이로 설정 `true`, 또는 사용 하 여는 <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> 트리를 탐색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Automation.AutomationElement>  
 [UI 자동화 개요](../../../docs/framework/ui-automation/ui-automation-overview.md)
