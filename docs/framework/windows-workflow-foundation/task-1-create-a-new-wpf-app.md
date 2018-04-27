---
title: '작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd21013331e19fa9e18ad7cbee0a7bb07abaf3d2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기
이 태스크에서는 WPF 응용 프로그램에 대 한 Visual Studio 템플릿을 사용 하 여 빈 Windows Presentation Foundation (WPF) 응용 프로그램을 만들 및 적절 한 참조를 추가 합니다 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 어셈블리입니다.  
  
### <a name="to-create-the-wpf-application-project"></a>WPF 응용 프로그램 프로젝트를 만들려면  
  
1.  Visual Studio를 열고 및는 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자를 선택 **Visual C#** 또는 **Visual Basic** 에서 **설치 된 템플릿** 의 왼쪽 창 상자입니다. 선택한 언어가 표시 되지 않으면에서 찾아봅니다 **다른 언어**합니다.  
  
3.  선택 **Windows** 에 **설치 된 템플릿** 창.  
  
4.  위쪽 창에 있는지를 확인 (기본값) **.NET Framework 4** 선택 하 여 드롭다운 목록 상자에서 선택한 **WPF 응용 프로그램**합니다.  
  
5.  프로젝트의 이름을 설정 **HostingApplication** 창의 맨 아래에 있습니다.  
  
6.  솔루션 이름으로 설정 **RehostingTheDesigner**합니다.  
  
7.  클릭 **확인** 응용 프로그램 프로젝트를 만듭니다. Visual Studio 응용 프로그램에 대 한 기본 WPF UI를 만들고 해당 XAML 및 코드 숨김 파일을 포함 합니다.  
  
8.  에 대 한 참조를 추가 **WorkflowModel** 어셈블리입니다. 이 수행 하려면 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **HostingApplication** 프로젝트를 마우스 선택 **참조 추가**합니다.  
  
9. 에 **참조 추가** 대화 상자를 클릭는 **.NET** 탭에서 CTRL 키를 누른 다음 어셈블리를 선택한 다음를 클릭 **확인**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. **확인**을 클릭합니다.  
  
11. 참조 [작업 2: 워크플로 디자이너 호스트](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) 워크플로 디자이너 디자인 캔버스를 호스트 하는 방법을 배울 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 디자이너 재호스트](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [작업 2: 워크플로 디자이너 호스트](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
