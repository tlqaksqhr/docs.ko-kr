---
title: "속성 변경 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 지정 컨트롤[Windows Forms], 속성 변경(코드 사용)"
  - "속성[Windows Forms], 변경 내용"
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 속성 변경 이벤트
*PropertyName*이라는 속성이 변경되는 경우 컨트롤에서 알림을 보내게 하려면 *PropertyName*`Changed` 이벤트를 정의하고 해당 이벤트를 발생시키는 `On`*PropertyName*`Changed` 메서드를 정의합니다.  속성 이름에 *Changed*라는 단어를 추가하는 것이 Windows Forms의 명명 규칙입니다.  속성 변경 이벤트에 대한 관련 이벤트 대리자 형식은 <xref:System.EventHandler>이며 이벤트 데이터 형식은 <xref:System.EventArgs>입니다.  기본 클래스 <xref:System.Windows.Forms.Control>은 <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>와 같은 많은 속성 변경 이벤트를 정의합니다.  이벤트에 대한 배경 정보는 [이벤트](../../../../docs/standard/events/index.md) 및 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)를 참조하십시오.  
  
 속성 변경 이벤트는 변경에 응답하는 이벤트 처리기를 컨트롤의 소비자가 연결할 수 있도록 해주기 때문에 유용합니다.  컨트롤에서 발생시킨 속성 변경 이벤트에 응답해야 할 경우 이벤트에 대리자를 연결하는 대신 해당 `On`*PropertyName*`Changed` 메서드를 재정의합니다.  대개 컨트롤은 다른 속성을 업데이트하거나 그리기 화면의 일부 또는 전체를 다시 그려서 속성 변경 이벤트에 응답합니다.  
  
 다음 예제에서는 `FlashTrackBar` 사용자 지정 컨트롤이 <xref:System.Windows.Forms.Control>에서 상속한 속성 변경 이벤트에 응답하는 방법을 보여 줍니다.  전체 샘플을 보려면 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하십시오.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## 참고 항목  
 [이벤트](../../../../docs/standard/events/index.md)   
 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)