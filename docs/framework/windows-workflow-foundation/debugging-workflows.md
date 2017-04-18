---
title: "워크플로 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 워크플로 디버깅
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]는 개발 환경에서 실행 중인 워크플로를 디버깅하기 위한 여러 옵션을 제공합니다.  디자이너, XAML 및 코드에서 워크플로를 디버깅할 수 있습니다.  
  
## Workflow Designer에서 디버깅  
 Workflow Designer에서 활동을 강조 표시하고 **F9** 키를 누르거나 해당 활동의 상황에 맞는 메뉴를 사용하여 활동에 중단점을 설정할 수 있습니다.  그러면 워크플로 호스트가 디버그 모드에서 실행될 때 워크플로 실행이 중단됩니다.  다음 스크린샷에서는 워크플로 실행이 중단점에서 일시 중지됩니다.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Workflow Designer로 워크플로 디버깅](../Topic/Debugging%20Workflows%20with%20the%20Workflow%20Designer.md).  
  
## XAML에서 디버깅  
 워크플로가 디자이너의 중단점에서 일시 중지된 경우 XAML에서 워크플로를 디버깅할 수도 있습니다.  XAML에서 실행 지점을 보려면 워크플로 실행이 일시 중지될 때 Workflow Designer에서 **XAML 뷰**를 선택합니다.  솔루션 탐색기에서 디자이너에 워크플로를 다시 열어 디버깅을 다시 디자이너로 전환할 수 있습니다.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][방법: Workflow Designer로 XAML 디버그](../Topic/How%20to:%20Debug%20XAML%20with%20the%20Workflow%20Designer.md).  
  
## 코드에서 디버깅  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서는 다른 명령형 응용 프로그램과 동일한 방법으로 코드 중단점을 사용할 수 있습니다.  코드 창의 왼쪽 여백을 클릭하여 코드 중단점을 만들거나 **F9** 키를 눌러 커서 위치에 중단점을 배치합니다.  
  
## 워크플로 프로세스에 연결  
 워크플로 디버깅은 Visual Studio 인프라를 사용하여 프로세스에 연결하는 방식도 지원합니다.  이렇게 하면 워크플로 작성자가 Internet Information Services\(IIS\) 7.0 등 다른 호스트 환경에서 실행되는 워크플로를 디버깅할 수 있습니다.  
  
## 원격 디버깅  
 [!INCLUDE[wf](../../../includes/wf-md.md)] 원격 디버깅은 다른 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] 구성 요소의 원격 디버깅과 동일하게 작동합니다.  원격 디버깅 사용에 대한 자세한 내용은 [방법: 원격 디버깅 사용](http://go.microsoft.com/fwlink/?LinkId=196257)을 참조하세요.  
  
> [!NOTE]
>  워크플로 응용 프로그램에서 x86 아키텍처를 대상으로 하고 64비트 운영 체제를 실행 중인 컴퓨터에서 호스트될 경우 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]가 원격 컴퓨터에 설치되지 않고 워크플로 응용 프로그램의 대상이 **모든 CPU**로 변경되지 않으면 원격 디버깅은 작동되지 않습니다.  
  
## 워크플로 디버깅 서비스 확장  
 워크플로 디버거 서비스는 현재 공용이며 다시 호스트된 디자이너에서 모니터링, 시뮬레이션 및 디버깅과 같은 사용자 지정 응용 프로그램을 만드는 데 사용될 수 있습니다.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] <xref:System.Activities.Presentation.Debug.DebuggerService> 항목을 참조하세요.