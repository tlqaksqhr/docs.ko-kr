---
title: "Windows Forms에서 마우스 입력이 작동하는 방식 | Microsoft Docs"
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
  - "마우스, 입력"
  - "Windows Forms, 마우스 입력"
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Windows Forms에서 마우스 입력이 작동하는 방식
마우스 입력을 받아 처리하는 것은 모든 Windows 응용 프로그램에서 중요한 부분 중 하나입니다.  마우스 이벤트를 처리하여 응용 프로그램의 작업을 수행하거나 마우스 위치 정보를 사용하여 적중 테스트 또는 기타 작업을 수행할 수 있습니다.  또한 응용 프로그램의 컨트롤에서 마우스 입력이 처리되는 방식을 변경할 수도 있습니다.  이 항목에서는 이러한 마우스 이벤트에 대한 자세한 내용과 마우스의 시스템 설정을 가져오고 변경하는 방법에 대해 설명합니다.  마우스 이벤트에 제공되는 데이터 및 마우스 클릭 이벤트가 발생하는 순서에 대한 자세한 내용은 [Windows Forms의 마우스 이벤트](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)를 참조하십시오.  
  
## 마우스 위치 및 적중 테스트  
 사용자가 마우스를 움직임에 따라 운영 체제에서 마우스 포인터를 이동합니다.  마우스 포인터에는 핫 스폿이라는 하나의 픽셀이 있으며, 운영 체제에서는 이 픽셀을 추적하여 포인터 위치를 인식합니다.  사용자가 마우스를 움직이거나 마우스 단추를 누르면 <xref:System.Windows.Forms.Cursor.HotSpot%2A>이 들어 있는 <xref:System.Windows.Forms.Control>이 해당 마우스 이벤트를 발생시킵니다.  마우스 이벤트를 처리할 때 <xref:System.Windows.Forms.MouseEventArgs>의 <xref:System.Windows.Forms.MouseEventArgs.Location%2A> 속성을 사용하거나 <xref:System.Windows.Forms.Cursor> 클래스의 <xref:System.Windows.Forms.Cursor.Position%2A> 속성을 사용하여 현재 마우스 위치를 가져올 수 있습니다.  이후에 마우스 위치 정보를 사용하여 적중 테스트를 수행한 다음, 마우스 위치를 기반으로 작업을 수행할 수 있습니다.  적중 테스트 기능은 Windows Forms에서 <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> 및 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 몇 가지 컨트롤에 기본적으로 제공되어 있습니다.  적중 테스트를 <xref:System.Windows.Forms.Control.MouseHover>와 같은 적절한 마우스 이벤트와 함께 사용하면 응용 프로그램에서 특정 작업을 수행해야 할 시점을 파악할 때 아주 유용합니다.  
  
## 마우스 이벤트  
 마우스 입력에 응답하는 기본적인 방법은 마우스 이벤트를 처리하는 것입니다.  다음 표에서는 마우스 이벤트를 보여 주고 각 이벤트가 발생하는 시점에 대해 설명합니다.  
  
|마우스 이벤트|설명|  
|-------------|--------|  
|<xref:System.Windows.Forms.Control.Click>|이 이벤트는 마우스 단추를 놓을 때 발생하며, 일반적으로 <xref:System.Windows.Forms.Control.MouseUp> 이벤트보다 먼저 발생합니다.  이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.  단추가 클릭되는 시점만 파악할 경우에 이 이벤트를 처리하십시오.|  
|<xref:System.Windows.Forms.Control.MouseClick>|이 이벤트는 사용자가 마우스로 컨트롤을 클릭할 때 발생합니다.  이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.  단추가 클릭되었을 때 마우스에 대한 정보를 가져와야 하는 경우에 이 이벤트를 처리하십시오.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|이 이벤트는 컨트롤을 두 번 클릭할 때 발생합니다.  이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.  단추가 두 번 클릭되는 시점만 파악할 경우에 이 이벤트를 처리하십시오.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|이 이벤트는 사용자가 마우스로 컨트롤을 두 번 클릭할 때 발생합니다.  이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.  단추가 두 번 클릭되었을 때 마우스에 대한 정보를 가져와야 하는 경우에 이 이벤트를 처리하십시오.|  
|<xref:System.Windows.Forms.Control.MouseDown>|이 이벤트는 마우스 포인터가 컨트롤 위에 있을 때 사용자가 마우스 단추를 누르면 발생합니다.  이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|이 이벤트는 컨트롤 형식에 따라 마우스 포인터가 컨트롤의 테두리나 클라이언트 영역에 들어갈 때 발생합니다.  이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseHover>|이 이벤트는 컨트롤 위에서 마우스 포인터를 멈추고 잠시 기다릴 때 발생합니다.  이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|이 이벤트는 컨트롤 형식에 따라 마우스 포인터가 컨트롤의 테두리나 클라이언트 영역을 벗어날 때 발생합니다.  이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseMove>|이 이벤트는 컨트롤 위에서 마우스 포인터를 움직일 때 발생합니다.  이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseUp>|이 이벤트는 마우스 포인터가 컨트롤 위에 있을 때 사용자가 마우스 단추를 놓으면 발생합니다.  이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|이 이벤트는 컨트롤에 포커스가 있는 상태에서 사용자가 마우스 휠을 돌릴 때 발생합니다.  이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.  <xref:System.Windows.Forms.MouseEventArgs>의 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> 속성을 사용하여 마우스가 스크롤된 거리를 확인할 수 있습니다.|  
  
## 마우스 입력 변경 및 시스템 설정 검색  
 컨트롤을 파생시키고 <xref:System.Windows.Forms.Control.GetStyle%2A> 및 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 사용하여 컨트롤에서 마우스 입력이 처리되는 방식을 확인하고 변경할 수 있습니다.  <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드에서는 <xref:System.Windows.Forms.ControlStyles> 값을 비트 단위로 조합한 값을 사용하여 컨트롤에 표준 클릭 또는 두 번 클릭 동작이 있는지 여부 및 컨트롤에서 마우스 프로세스가 자체적으로 처리되는지 여부를 확인합니다.  또한 <xref:System.Windows.Forms.SystemInformation> 클래스에는 마우스 기능을 설명하고 마우스가 운영 체제와 상호 작용하는 방법을 지정하는 속성이 포함되어 있습니다.  다음 표에서는 이러한 속성을 요약 설명합니다.  
  
|Property|설명|  
|--------------|--------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|운영 체제에서 두 번의 클릭이 두 번 클릭으로 간주되도록 사용자가 두 번 클릭해야 하는 영역의 크기를 픽셀 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|운영 체제에서 마우스 동작이 두 번 클릭으로 간주되도록 첫 번째 클릭과 두 번째 클릭 사이 간격의 최대 시간을 밀리초 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|마우스의 단추 수를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|마우스 왼쪽 단추와 오른쪽 단추의 기능이 바뀌었는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|마우스 호버 메시지가 생성되기 전에 마우스 포인터가 마우스 호버 시간 동안 머물러야 하는 사각형의 크기를 픽셀 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|마우스 호버 메시지가 생성되기 전에 마우스 포인터가 호버 사각형에 머물러야 하는 시간을 밀리초 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|마우스가 설치되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|현재 마우스 속도를 나타내는 값\(1 \- 20\)을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|휠 마우스가 설치되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|마우스 휠을 한 번 돌릴 때의 델타 증분 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|마우스 휠을 돌릴 때 스크롤되는 줄 수를 가져옵니다.|  
  
## 참고 항목  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Windows Forms의 마우스 캡처](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)   
 [Windows Forms의 마우스 포인터](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)