---
title: "활동 클래스를 사용하여 워크플로 활동 제작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 활동 클래스를 사용하여 워크플로 활동 제작
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서 [!INCLUDE[wf](../../../includes/wf-md.md)]를 사용하여 활동을 만드는 가장 기본적인 방법은 [기본 제공 활동 라이브러리](../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md)의 활동이나 사용자 지정 활동을 어셈블하여 기능을 만드는 <xref:System.Activities.Activity>에서 상속되는 클래스를 만드는 것입니다.이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.  
  
### 활동 디자이너를 사용하여 사용자 지정 활동을 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 엽니다.  
  
2.  파일, 새로 만들기, 프로젝트를 차례로 선택합니다.**프로젝트 형식** 창의 **Visual C\#** 아래에서 **Workflow 4.0**을 선택하고 **v2010** 노드를 선택합니다.**템플릿** 창에서 **활동 라이브러리**를 선택합니다.새 프로젝트의 이름을 HelloActivity로 지정합니다.  
  
3.  새 활동을 엽니다.도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.  
  
4.  <xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.**텍스트** 필드에 `“Hello World”`\(따옴표 포함\)를 입력합니다.  
  
5.  두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.**텍스트** 필드에 `“Goodbye”`\(따옴표 포함\)를 입력합니다.