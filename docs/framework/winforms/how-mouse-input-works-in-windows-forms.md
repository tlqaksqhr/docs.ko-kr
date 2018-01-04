---
title: "Windows Forms에서 마우스 입력이 작동하는 방식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 388fd8d3e7f23dc55d46c5a097be99e9f1c34ab0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Windows Forms에서 마우스 입력이 작동하는 방식
수신 및 마우스 입력을 처리에 모든 Windows 응용 프로그램의 중요 한 부분입니다. 응용 프로그램에서 작업을 수행 하려면 마우스 이벤트를 처리 하거나 적중 테스트를 수행 하려면 마우스 위치 정보 또는 기타 작업을 사용할 수 있습니다. 또한 응용 프로그램의 컨트롤 마우스 입력을 처리 하는 방식을 변경할 수 있습니다. 이 항목에서는 detail 및 마우스에 대 한 시스템 설정을 변경 하는 방법에서 이러한 마우스 이벤트를 설명 합니다. 마우스로 제공 되는 데이터에 대 한 자세한 내용은 이벤트와 마우스 클릭 이벤트가 순서는 발생 한 자세한 내용은 [Windows Forms의 마우스 이벤트](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)합니다.  
  
## <a name="mouse-location-and-hit-testing"></a>마우스 위치 및 적중 테스트  
 마우스 포인터를 이동 하는 사용자가 마우스를 이동 하는 경우 운영 체제 마우스 포인터에는 단일 운영 체제를 추적 및 포인터의 위치를 인식 하는 핫 스폿 픽셀 포함 되어 있습니다. 사용자가 마우스를 이동 하거나 마우스 단추를 누를 때는 <xref:System.Windows.Forms.Control> 를 포함 하는 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 적합 한 마우스 이벤트를 발생 시킵니다. 와 현재 마우스 위치를 가져올 수 있습니다는 <xref:System.Windows.Forms.MouseEventArgs.Location%2A> 속성의는 <xref:System.Windows.Forms.MouseEventArgs> 마우스 이벤트를 처리 하는 경우 또는 사용 하 여는 <xref:System.Windows.Forms.Cursor.Position%2A> 의 속성은 <xref:System.Windows.Forms.Cursor> 클래스입니다. 이후에 마우스 위치 정보를 사용 하 여 적중 테스트를 수행 하 고 마우스 위치에 따라 작업을 수행할 수 있습니다. 적중 테스트 기능에 기본 제공 Windows Forms에서 여러 컨트롤 같은 <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> 및 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 적합 한 마우스 이벤트와 함께 사용 되는 <xref:System.Windows.Forms.Control.MouseHover> 예를 들어, 적중 테스트에 매우 유용 응용 프로그램은 특정 작업을 수행 하는 시기를 결정 합니다.  
  
## <a name="mouse-events"></a>마우스 이벤트  
 마우스 입력에 응답 하는 기본적인 방법은 마우스 이벤트를 처리 하기 위한 것입니다. 다음 표에서 마우스 이벤트를 표시 하 고 발생 하는 경우를 설명 합니다.  
  
|마우스 이벤트|설명|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|이 이벤트는 마우스 단추를 놓을 때 발생, 전에 일반적으로 <xref:System.Windows.Forms.Control.MouseUp> 이벤트입니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다. 클릭 되었을 때 결정 해야 하는 경우이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.MouseClick>|이 이벤트는 사용자가 컨트롤을 마우스로 클릭할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다. 한 번의 클릭 발생할 때 마우스에 대 한 정보를 보려고 할 때이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|이 이벤트는 컨트롤을 두 번 클릭할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다. 두 번 클릭할 때 결정 해야 하는 경우이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|이 이벤트는 컨트롤을 마우스로 클릭할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다. 두 번 클릭할 때 마우스에 대 한 정보를 보려고 할 때이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.MouseDown>|이 이벤트는 마우스 포인터가 컨트롤 위에 있는 사용자가 마우스 단추를 누를 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|이 이벤트는 마우스 포인터가 컨트롤의 종류에 따라 컨트롤의 테두리 또는 클라이언트 영역에 들어갈 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseHover>|이 이벤트는 마우스 포인터를 중지 하 고 컨트롤 위에 있을 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|이 이벤트는 마우스 포인터가 컨트롤의 종류에 따라 컨트롤의 테두리 또는 클라이언트 영역을 벗어날 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseMove>|이 이벤트는 컨트롤 위에 있는 동안 마우스 포인터를 움직이면 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseUp>|이 이벤트는 마우스 포인터가 컨트롤 위에 있는 사용자가 마우스 단추를 놓을 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|이 이벤트는 컨트롤에 포커스가 있을 때 마우스 휠을 회전할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다. 사용할 수는 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> 속성 <xref:System.Windows.Forms.MouseEventArgs> 마우스 스크롤 떨어져 있는 정도 결정 하 합니다.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>마우스 입력을 변경 하 고 시스템 설정 검색  
 검색 하 고는 컨트롤이 컨트롤에서 파생 되 고 사용 하 여 마우스 입력을 처리 하는 방식을 변경할 수는 <xref:System.Windows.Forms.Control.GetStyle%2A> 및 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드. <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 사용 하며의 비트 조합 <xref:System.Windows.Forms.ControlStyles> 컨트롤 표준 클릭 또는 두 번 클릭 동작이 있는지 또는 컨트롤에서 마우스 처리를 처리 하는 경우를 결정 하는 값입니다. 또한는 <xref:System.Windows.Forms.SystemInformation> 클래스는 마우스의 기능을 설명 하 고 운영 체제와 마우스 상호 작용 하는 방법을 지정 하는 속성을 포함 합니다. 다음 표에서 이러한 속성을 요약 합니다.  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|크기를 픽셀 단위로 가져옵니다, 그리고 두 번 클릭이 있는 사용자를 두 고려해 야 할 운영 체제에 대해 두 번 클릭 해야 하는 영역의 합니다.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|첫 번째 클릭 및 마우스 동작을 두 번 클릭 고려해 야 할 운영 체제에 대 한 두 번째 클릭 간에 경과 된 시간 (밀리초)의 최대 수를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|마우스의 단추 수를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|마우스 왼쪽 단추와 오른쪽 단추의 기능이 바뀌었는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|마우스 호버 메시지가 생성되기 전에 마우스 포인터가 마우스 호버 시간 동안 머물러야 하는 사각형의 크기를 픽셀 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|마우스 호버 메시지가 생성되기 전에 마우스 포인터가 호버 사각형에 머물러야 하는 시간을 밀리초 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|마우스가 설치 되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|1 ~ 20 현재 마우스 속도 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|휠 마우스가 설치되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|단일 마우스 휠 회전 증분에 대 한 델타 값 크기를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|마우스 휠을 돌릴 때 스크롤되는 줄 수를 가져옵니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Windows Forms의 마우스 캡처](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)  
 [Windows Forms의 마우스 포인터](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)
