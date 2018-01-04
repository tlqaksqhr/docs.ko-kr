---
title: "활동 클래스를 사용하여 워크플로 활동 제작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52d29f9cbed65932b3f9e97f0e9275861953b5d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>활동 클래스를 사용하여 워크플로 활동 제작
사용 하 여 활동을 만드는 가장 기본적인 방법은 [!INCLUDE[wf](../../../includes/wf-md.md)] 에 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 에서 상속 되는 클래스를 만드는 <xref:System.Activities.Activity> 만들어지는 기능 어셈블하는 방법으로 사용자 지정 활동 또는 활동에서는 [기본 제공 활동 라이브러리 ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). 이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>활동 디자이너를 사용하여 사용자 지정 활동을 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]를 엽니다.  
  
2.  파일, 새로 만들기, 프로젝트를 차례로 선택합니다. 선택 **Workflow 4.0** 아래 **Visual C#** 에 **프로젝트 형식** 창과 선택은 **v2010** 노드. 선택 **활동 라이브러리** 에 **템플릿** 창. 새 프로젝트의 이름을 HelloActivity로 지정합니다.  
  
3.  새 활동을 엽니다.  도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.  
  
4.  <xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다. 입력 `"Hello World"` (따옴표 포함)와는 **텍스트** 필드입니다.  
  
5.  두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다. 입력 `"Goodbye"` (따옴표 포함)와는 **텍스트** 필드입니다.
