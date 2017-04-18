---
title: "Windows Forms의 마우스 포인터 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "커서, 설정[Windows Forms]"
  - "마우스 커서"
  - "마우스 포인터"
  - "마우스 포인터, 설정[Windows Forms]"
  - "마우스, 커서"
  - "포인터, 설정[Windows Forms]"
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms의 마우스 포인터
커서라고도 하는 마우스 *포인터*는 사용자가 화면에서 마우스로 입력할 때 포커스 점을 지정하는 비트맵입니다.  이 항목에서는 Windows Forms의 마우스 포인터에 대한 개요와 마우스 포인터를 수정 및 제어하는 몇 가지 방법에 대해 설명합니다.  
  
## 마우스 포인터에 액세스  
 마우스 포인터는 <xref:System.Windows.Forms.Cursor> 클래스로 나타내며 각 <xref:System.Windows.Forms.Control>에는 해당 컨트롤에 대한 포인터를 지정하는 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName> 속성이 있습니다.  <xref:System.Windows.Forms.Cursor> 클래스에는 <xref:System.Windows.Forms.Cursor.Position%2A> 및 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 속성과 같이 포인터를 설명하는 속성과 <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A> 및 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 메서드와 같이 포인터의 모양을 수정할 수 있는 메서드가 들어 있습니다.  
  
## 마우스 포인터 제어  
 마우스 포인터를 사용할 수 있는 영역을 제한하거나 마우스의 위치를 변경해야 하는 경우가 있습니다.  <xref:System.Windows.Forms.Cursor>의 <xref:System.Windows.Forms.Cursor.Position%2A> 속성을 사용하여 마우스의 현재 위치를 가져오거나 설정할 수 있습니다.  또한 <xref:System.Windows.Forms.Cursor.Clip%2A> 속성을 설정하여 마우스 포인터를 사용할 수 있는 영역을 제한할 수 있습니다.  기본적으로 전체 화면이 클리핑 영역입니다.  
  
## 마우스 포인터 변경  
 사용자에게 피드백을 줄 수 있는 가장 좋은 방법은 마우스 포인터를 변경하는 것입니다.  예를 들어, <xref:System.Windows.Forms.Control.MouseEnter> 및 <xref:System.Windows.Forms.Control.MouseLeave> 이벤트의 처리기에서 마우스 포인터를 수정하여 계산이 수행되고 있음을 사용자에게 알리고 컨트롤에서 사용자 상호 작용을 제한할 수 있습니다.  응용 프로그램에서 끌어서 놓기 작업이 수행되고 있을 때와 같이 시스템 이벤트 때문에 마우스 포인터가 변경되는 경우도 있습니다.  
  
 마우스 포인터를 변경하는 기본적인 방법은 컨트롤의 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName> 또는 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 속성을 새 <xref:System.Windows.Forms.Cursor>로 설정하는 것입니다.  마우스 포인터를 변경하는 예제를 보려면 <xref:System.Windows.Forms.Cursor> 클래스의 코드 예제를 참조하십시오.  또한 <xref:System.Windows.Forms.Cursors> 클래스는 손 모양의 포인터와 같은 여러 형식의 포인터에 대한 <xref:System.Windows.Forms.Cursor> 개체 집합을 노출합니다.  마우스 포인터가 컨트롤에 있을 때 항상 모래 시계 모양의 대기 포인터를 표시하려면 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 속성을 사용합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Cursor>   
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Windows Forms에서의 끌어서 놓기 기능](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)