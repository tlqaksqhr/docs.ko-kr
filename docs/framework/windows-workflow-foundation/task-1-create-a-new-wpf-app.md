---
title: "태스크 1: 새 Windows Presentation Foundation 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 태스크 1: 새 Windows Presentation Foundation 응용 프로그램 만들기
이 태스크에서는 WPF 응용 프로그램 Visual Studio 템플릿을 사용하여 빈 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 응용 프로그램을 만들고 해당 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 어셈블리에 대한 참조를 추가합니다.  
  
### WPF 응용 프로그램 프로젝트를 만들려면  
  
1.  [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]을 열고 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 왼쪽에 있는 **설치된 템플릿** 창에서 **Visual C\#** 또는 **Visual Basic**을 선택합니다.선택한 언어가 표시되지 않으면 **다른 언어**에서 찾아봅니다.  
  
3.  **설치된 템플릿** 창에서 **Windows**를 선택합니다.  
  
4.  위쪽 창의 드롭다운 목록 상자에서 **.NET Framework 4**\(기본값\)이 선택되어 있는지 확인한 다음 **WPF 응용 프로그램**을 선택합니다.  
  
5.  창의 아래쪽에서 프로젝트 이름을 **HostingApplication**으로 설정합니다.  
  
6.  솔루션의 이름을 **RehostingTheDesigner**로 설정합니다.  
  
7.  **확인**을 클릭하여 응용 프로그램 프로젝트를 만듭니다.[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]에서 응용 프로그램에 대한 기본 WPF UI를 만들고 해당 XAML 및 코드 숨김 파일을 포함합니다.  
  
8.  **WorkflowModel** 어셈블리에 대한 참조를 추가합니다.이렇게 하려면 **솔루션 탐색기**에서 **HostingApplication** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.  
  
9. **참조 추가** 대화 상자에서 **.NET** 탭을 클릭하고 Ctrl 키를 누른 상태로 다음 어셈블리를 선택한 다음 **확인**을 클릭합니다.  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. **확인**을 클릭합니다.  
  
11. Workflow Designer 디자인 캔버스를 호스팅하는 방법은 [태스크 2: Workflow Designer 호스팅](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)을 참조하십시오.  
  
## 참고 항목  
 [Workflow Designer 재호스팅](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [태스크 2: Workflow Designer 호스팅](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)