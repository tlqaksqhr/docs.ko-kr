---
title: "재호스팅된 워크플로 디자이너에서 새 Workflow Foundation 4.5 기능에 대한 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a4a4038-d8e6-41dd-99ea-93bd76286772
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee8467eaeaef490f4c7a8bfbcb204506d71f5500
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="support-for-new-workflow-foundation-45-features-in-the-rehosted-workflow-designer"></a>재호스팅된 워크플로 디자이너에서 새 Workflow Foundation 4.5 기능에 대한 지원
[!INCLUDE[wf](../../../includes/wf-md.md)]의 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에는 Workflow Designer 환경의 몇 가지 향상된 기능을 포함하여 새로운 여러 기능이 도입되었습니다. 이 항목에서는 이러한 기능 중 재호스트된 디자이너에서 지원되는 기능과 현재 지원되지 않는 기능을 자세히 설명합니다.  
  
> [!NOTE]
>  모든 새 목록에 대 한 [!INCLUDE[wf](../../../includes/wf-md.md)] 에서 도입 된 기능 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 디자이너 재호스팅 관련이 없는 것을 포함 하 여 참조 [.NET 4.5에서 Windows Workflow Foundation의 새로운](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md)합니다.  
  
## <a name="activities"></a>활동  
 기본 제공 활동 라이브러리에는 새로운 활동과 기존 활동의 새로운 기능이 들어 있습니다. 이러한 모든 새 활동은 재호스트된 디자이너에서 지원됩니다. 이러한 새 작업에 대 한 자세한 내용은 참조는 [활동](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md#BKMK_NewActivities) 섹션 [.NET 4.5에서 Windows Workflow Foundation의 새로운](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md)합니다.  
  
## <a name="c-expressions"></a>C# 식  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이전에는 워크플로의 모든 식을 Visual Basic으로만 작성할 수 있었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 Visual Basic 식은 Visual Basic을 사용하여 만든 프로젝트에만 사용됩니다. Visual C# 프로젝트는 이제 식에 C#을 사용합니다. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 워크플로를 작성할 때는 문법 강조 표시 및 IntelliSense와 같은 기능이 포함된 완전한 기능의 C# 식 편집기가 제공됩니다. 이전 버전에서 만들어졌으며 Visual Basic 식을 사용하는 C# 워크플로 프로젝트는 계속 작동합니다.  
  
> [!WARNING]
>  재호스트된 디자이너에서는 C# 식이 지원되지 않습니다.  
  
## <a name="new-designer-capabilities"></a>새로운 디자이너 기능  
  
### <a name="designer-search"></a>디자이너 검색  
 [빠른 찾기](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) 및 [파일에서 찾기](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) 에 도입 된 기능 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재 호스트 된 디자이너에서 지원 되지 않습니다. `Toolbox` 검색은 재호스트된 디자이너에서 지원됩니다. 이러한 기능에 대 한 자세한 내용은 참조 하십시오. [디자이너 검색](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md#BKMK_DesignerSearch)합니다.  
  
> [!WARNING]
>  [빠른 찾기](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) 및 [파일에서 찾기](../../../docs/framework/windows-workflow-foundation/whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) 재 호스트 된 디자이너에서 지원 되지 않습니다.  
  
### <a name="delete-context-menu-item-in-variable-and-argument-designer"></a>변수 및 인수 디자이너에서 상황에 맞는 메뉴에 표시되는 삭제 항목  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서는 디자이너에서 키보드로만 변수 및 인수를 삭제할 수 있었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터는 상황에 맞는 메뉴를 사용하여 변수 및 인수를 삭제할 수 있습니다. 이 기능은 재호스트된 디자이너에서 지원됩니다.  
  
 다음 스크린 샷에서는 변수 및 인수 디자이너의 상황에 맞는 메뉴를 보여 줍니다.  
  
 ![변수 및 인수 디자이너 상황에 맞는 메뉴](../../../docs/framework/windows-workflow-foundation/media/designercontextmenu.png "DesignerContextMenu")  
  
### <a name="auto-surround-with-sequence"></a>시퀀스로 자동 감싸기  
 워크플로 또는 특정 컨테이너 활동(예: <xref:System.Activities.Statements.NoPersistScope>)에는 단일 본문 활동만 포함할 수 있으므로 두 번째 활동을 추가하려면 개발자가 첫 번째 활동을 삭제하고 <xref:System.Activities.Statements.Sequence> 활동을 추가한 후 두 활동을 모두 시퀀스 활동에 추가해야 했습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터는 디자이너 화면에 두 번째 활동을 추가하면 `Sequence` 활동이 자동으로 만들어져 두 활동을 래핑합니다. 이 기능은 재호스트된 디자이너에서 지원됩니다.  
  
 다음 스크린 샷에서는 `WriteLine`의 `Body`에 있는 `NoPersistScope` 활동을 보여 줍니다.  
  
 ![자동 &#45; 저장 위치 서라운드](../../../docs/framework/windows-workflow-foundation/media/autosurround1.png "AutoSurround1")  
  
 다음 스크린 샷에서는 두 번째 `Sequence`이 첫 번째 항목 아래에 놓였을 때 `Body`에 자동으로 만들어진 `WriteLine` 활동을 보여 줍니다.  
  
 ![자동으로 만들어진 sequence 활동](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")  
  
### <a name="pan-mode"></a>이동 모드  
 디자이너에서 큰 워크플로를 더욱 쉽게 이동하기 위해 이동 모드를 사용할 수 있습니다. 이동 모드에서 개발자는 스크롤 바를 사용할 필요 없이 워크플로의 보이는 부분을 클릭하여 끌 수 있습니다. 이동 모드를 활성화하는 단추는 디자이너의 오른쪽 아래 모퉁이에 있습니다. 이 기능은 재호스트된 디자이너에서 지원됩니다.  
  
 다음 스크린 샷에서는 워크플로 디자이너의 오른쪽 아래 모퉁이에 있는 이동 단추를 보여 줍니다.  
  
 ![워크플로 디자이너의 이동 단추](../../../docs/framework/windows-workflow-foundation/media/panbutton.png "PanButton")  
  
 마우스 가운데 단추 또는 스페이스바를 사용하여 워크플로 디자이너를 이동할 수도 있습니다.  
  
### <a name="multi-select"></a>다중 선택  
 이동 모드를 사용하지 않을 경우 활동 주위의 사각형을 끌거나, Ctrl 키를 누른 채 원하는 활동을 하나씩 클릭하여 여러 활동을 한 번에 선택할 수 있습니다. 이 기능은 재호스트된 디자이너에서 지원됩니다.  
  
 디자이너 내에서 선택된 여러 활동을 끌어다 놓을 수도 있으며 상황에 맞는 메뉴를 사용하여 상호 작용할 수도 있습니다.  
  
### <a name="outline-view-of-workflow-items"></a>워크플로 항목 개요 뷰  
 계층적 워크플로를 쉽게 탐색할 수 있도록 워크플로의 구성 요소는 트리 스타일 개요 뷰로 표시됩니다. 개요 보기에 표시 되는 **문서 개요** 보기. 이 뷰를 열려면 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], 맨 위 메뉴에서 선택 **보기**, **다른 창**, **문서 개요**, 하거나 ctrl + W, u입니다. 개요 뷰의 노드를 클릭하면 워크플로 디자이너의 해당 활동으로 이동되고 개요 뷰가 업데이트되어 디자이너에서 선택된 활동이 표시됩니다. 이 기능은 재호스트된 디자이너에서 지원됩니다.  
  
 완료 된 워크플로의 다음 스크린 샷에서 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) 순차 워크플로 개요 보기를 보여 줍니다.  
  
 ![개요 보기 워크플로 디자이너에서](../../../docs/framework/windows-workflow-foundation/media/outlineviewinworkflowdesigner.jpg "OutlineViewinWorkflowDesigner")  
  
### <a name="more-control-of-visibility-of-shell-bar-and-header-items"></a>셸 표시줄 및 헤더 항목의 표시 방식 제어 향상  
 재호스트된 디자이너에서 특정 워크플로에 대해 의미가 없는 일부 표준 UI 컨트롤은 해제할 수 있습니다. [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서는 디자이너의 맨 아래에 있는 셸 표시줄을 통해서만 이를 사용자 지정할 수 있었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A>를 적절한 <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> 값으로 설정하여 디자이너의 맨 위에 있는 셸 헤더 항목의 표시 유형을 조정할 수 있습니다.  
  
### <a name="auto-connect-and-auto-insert-in-flowchart-and-state-machine-workflows"></a>순서도 및 상태 시스템 워크플로의 자동 연결 및 자동 삽입  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서는 순서도 워크플로의 노드 간 연결을 수동으로 추가해야 했습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 도구 상자에서 디자이너 화면으로 활동을 끌어올 때 순서도 및 상태 시스템 노드에는 자동 연결 지점이 표시됩니다. 이러한 지점 중 하나에 활동을 놓으면 필요한 연결과 함께 활동이 자동으로 추가됩니다.  
  
 다음 스크린 샷에서는 도구 상자에서 디자이너 화면으로 활동을 끌어 올 때 표시되는 연결 지점을 보여 줍니다.  
  
 ![자동 연결 지점을 보여 주는 순서도 시작 노드](../../../docs/framework/windows-workflow-foundation/media/autoconnect1.png "Autoconnect1")  
  
 활동을 순서도 노드와 상태 간 연결로 끌어 와 다른 두 노드 사이에 노드를 자동으로 삽입할 수도 있습니다. 다음 스크린 샷에서는 도구 상자의 활동을 끌어다 놓을 수 있는 강조 표시된 연결선을 보여 줍니다.  
  
 ![자동 &#45; insert 처리 활동을 끌기 위한](../../../docs/framework/windows-workflow-foundation/media/autoinsert.png "Autoinsert")  
  
 자동 연결 및 자동 삽입은 재호스트된 디자이너에서 지원됩니다.  
  
### <a name="designer-annotations"></a>디자이너 주석  
 이제 대규모 워크플로를 손쉽게 개발할 수 있도록 디자이너에서 주석을 추가하여 디자인 프로세스를 추적할 수 있습니다. 주석은 활동, 상태, 순서도 노드, 변수 및 인수에 추가할 수 있습니다. 다음 스크린 샷에서는 디자이너에 주석을 추가하는 데 사용되는 상황에 맞는 메뉴를 보여 줍니다.  
  
 ![주석 상황에 맞는 메뉴](../../../docs/framework/windows-workflow-foundation/media/annotationdialog.png "annotationdialog")  
  
 디자이너 주석은 재호스트된 디자이너에서 지원됩니다.  
  
### <a name="define-and-consume-activitydelegate-objects-in-the-designer"></a>디자이너에서 ActivityDelegate 개체 정의 및 사용  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]의 활동은 <xref:System.Activities.ActivityDelegate> 개체를 사용하여 워크플로의 다른 부분이 워크플로의 실행과 상호 작용할 수 있는 실행 지점을 노출했지만, 이러한 실행 지점을 사용하려면 일반적으로 많은 양의 코드가 필요했습니다. 이 릴리스에서는 개발자가 워크플로 디자이너를 사용하여 활동 대리자를 정의하고 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: 워크플로 디자이너에서 활동 대리자 정의 및 사용](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer)합니다.  
  
 활동 대리자는 재호스트된 디자이너에서 지원됩니다.  
  
### <a name="build-time-validation"></a>빌드 타임 유효성 검사  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서는 워크플로 프로젝트를 빌드하는 동안 워크플로 유효성 검사 오류가 빌드 오류로 간주되지 않았습니다. 따라서 워크플로 유효성 검사 오류가 있더라도 워크플로 프로젝트를 성공적으로 빌드할 수 있었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 워크플로 유효성 검사 오류가 있으면 빌드에 실패합니다.  
  
> [!WARNING]
>  빌드 타임 유효성 검사는 재호스트된 디자이너에서 지원되지 않습니다.  
  
### <a name="design-time-background-validation"></a>디자인 타임 백그라운드 유효성 검사  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서는 포그라운드 프로세스로 워크플로의 유효성을 검사하므로 복잡하거나 시간이 많이 걸리는 유효성 검사 프로세스 중에 UI가 중단될 수 있었습니다. 이제는 백그라운드 스레드에서 워크플로 유효성 검사를 수행하므로 UI가 차단되지 않습니다.  
  
 디자인 타임 백그라운드 유효성 검사는 재호스트된 디자이너에서 지원됩니다.  
  
### <a name="view-state-located-in-a-separate-location-in-xaml-files"></a>XAML 파일의 별도 위치에 있는 뷰 상태  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서는 워크플로의 뷰 상태 정보가 XAML 파일을 통해 여러 다른 위치에 저장되었습니다. 따라서 개발자가 XAML을 직접 읽거나 뷰 상태 정보를 제거하는 코드를 작성하기에 불편했습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], XAML 파일에서 뷰 상태 정보가 XAML 파일에서 별도 요소로 serialize 됩니다.  개발자가 쉽게 찾 및 활동의 보기 상태 정보를 편집 하거나 제거할 수 뷰 상태 완전히 합니다.  
  
 이 기능은 재호스트된 워크플로 디자이너에서 지원됩니다.  
  
### <a name="opt-in-for-workflow-45-features-in-rehosted-designer"></a>재호스트된 디자이너에서 Workflow 4.5 기능 사용  
 이전 버전과의 호환성을 유지하기 위해 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 포함된 새로운 기능 중 일부는 재호스트된 디자이너에서 기본적으로 사용되지 않도록 설정됩니다. 따라서 재호스트된 디자이너를 사용하는 기존 응용 프로그램은 최신 버전으로 업데이트해도 차단되지 않습니다. 재호스트된 디자이너에서 새로운 기능을 사용하려면 <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A>을 ".Net Framework 4.5"로 설정하거나 <xref:System.Activities.Presentation.DesignerConfigurationService>의 개별 멤버를 설정하여 개별 기능을 사용하도록 설정합니다.  
  
## <a name="new-workflow-development-models"></a>새로운 워크플로 개발 모델  
 순서도 및 순차 워크플로 개발 모델 외에도 이 릴리스에는 상태 시스템 워크플로 및 계약 중심 워크플로 서비스가 포함되어 있습니다.  
  
### <a name="state-machine-workflows"></a>상태 시스템 워크플로  
 .NET Framework 4.0.1의 일부로 도입 된 상태 시스템 워크플로 [MICROSOFT.NET Framework 4 플랫폼 업데이트 1](http://go.microsoft.com/fwlink/?LinkID=215092)합니다. 이 업데이트에는 여러 가지 새로운 클래스 및 활동이 포함되어 있으므로 개발자가 상태 시스템 워크플로를 만들 수 있었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 이러한 클래스 및 활동이 업데이트되었습니다. 업데이트에는 다음이 포함됩니다.  
  
1.  상태에 중단점을 설정할 수 있는 기능  
  
2.  Workflow Designer에서 전환을 복사하여 붙여 넣을 수 있는 기능  
  
3.  공유 트리거 전환 작성을 위한 디자이너 지원  
  
4.  <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> 및 <xref:System.Activities.Statements.Transition>을 포함하여 상태 시스템 워크플로를 만드는 데 사용되는 활동  
  
 다음 스크린샷은에서 완료 된 상태 시스템 워크플로 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) 단계 [하는 방법: 상태 시스템 워크플로 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)합니다.  
  
 ![완료 된 상태 시스템 워크플로](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
 상태 시스템 워크플로 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [상태 시스템 워크플로](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md)합니다. 상태 시스템 워크플로는 재호스트된 디자이너에서 지원됩니다.  
  
### <a name="contract-first-workflow-development"></a>계약 중심 워크플로 개발  
 계약 중심 워크플로 개발 도구를 사용하면 개발자가 코드에서 계약을 먼저 디자인한 다음 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]에서 몇 번의 클릭으로 도구 상자에서 각 작업을 나타내는 활동 템플릿을 자동으로 생성할 수 있습니다. 그런 다음 이러한 활동은 계약에서 정의한 작업을 구현하는 워크플로를 만드는 데 사용됩니다. Workflow Designer는 워크플로 서비스의 유효성을 검사하여 이러한 작업을 구현하고 워크플로의 서명이 계약 서명과 일치하도록 합니다. 개발자는 워크플로 서비스와 구현된 계약 컬렉션을 연결할 수도 있습니다. 계약 중심 워크플로 서비스 개발에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 기존 서비스 계약을 사용 하는 워크플로 서비스 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)합니다.  
  
> [!WARNING]
>  계약 중심 워크플로 개발은 워크플로 디자이너에서 지원되지 않습니다.
