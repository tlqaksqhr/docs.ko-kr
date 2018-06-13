---
title: HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: 572ba9f16d1c78e1825d0c9db7530c6c78175d27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538473"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar> 컨트롤 가로로 또는 세로로 응용 프로그램 또는 컨트롤 내에서 쉽게 탐색 긴 목록 항목이 나 많은 양의 정보를 제공 하는 데 사용 됩니다. 스크롤 막대는 Windows 인터페이스의 공통 요소 이므로 <xref:System.Windows.Forms.ScrollBar> 컨트롤에서 파생 되지 않는 컨트롤과 대개는 <xref:System.Windows.Forms.ScrollableControl> 클래스입니다. 대부분의 개발자 통합 하도록 선택 하는 마찬가지로,는 <xref:System.Windows.Forms.ScrollBar> 자신의 사용자 컨트롤 작성 하는 시기를 제어 합니다.  
  
 <xref:System.Windows.Forms.HScrollBar> (가로) 및 <xref:System.Windows.Forms.VScrollBar> (세로) 컨트롤 다른 컨트롤에서 독립적으로 작동 하 고 이벤트, 속성 및 메서드 집합이 자신의 합니다. <xref:System.Windows.Forms.ScrollBar> 컨트롤 텍스트 상자, 목록 상자 및 콤보 상자, MDI 폼에 연결 되어 있는 기본 제공 스크롤 막대와 동일 하지 않은 (의 <xref:System.Windows.Forms.TextBox> 컨트롤에는 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 컨트롤에 연결 되어 있는 스크롤 막대 표시 또는 숨기기).  
  
 <xref:System.Windows.Forms.ScrollBar> 사용을 제어는 <xref:System.Windows.Forms.ScrollBar.Scroll> 스크롤 막대를 따라 (엄지 단추 라고도 함) 스크롤 상자의 움직임을 모니터링 하는 이벤트입니다. 사용 하는 <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 끌 때 스크롤 막대의 값에 대 한 액세스를 제공 합니다.  
  
## <a name="value-property"></a>값 속성  
 <xref:System.Windows.Forms.ScrollBar.Value%2A> (즉, 기본적으로 0) 속성은 한 `integer` , 스크롤 막대의 스크롤 상자 위치에 해당 하는 값입니다. 스크롤 상자 위치가 최소값에, 가로 스크롤 막대 맨 왼쪽 위치 또는 세로 스크롤 막대 위쪽 위치를 이동 합니다. 때 스크롤 상자는 최대값, 스크롤 상자가 이동 맨 오른쪽 또는 아래쪽 위치에 있습니다. 마찬가지로, 하 한 및 상한 범위 사이의 중간 값 스크롤 막대를 중간에 있는 스크롤 상자의 첨단 배치합니다.  
  
 마우스 클릭을 사용 하 여 스크롤 막대 값을 변경 하려면를 사용자 막대를 따라 어떤 위치로 든 스크롤 상자를 끌 수도 있습니다. 결과 값의 스크롤 상자 위치에 따라 달라 지지만 범위 내에서 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 를 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 속성은 사용자가 설정 합니다.  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange 및 SmallChange 속성  
 사용자의 PAGE UP 또는 PAGE DOWN 키를 누르거나 스크롤 상자 옆에 있는 스크롤 막대 트랙에 클릭할 때는 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성에 설정 된 값에 따라이 변경의 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 속성입니다.  
  
 키를 누를 때 화살표 중 하나 또는 스크롤 막대 단추 중 하나를 클릭는 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성에 설정 된 값에 따라이 변경 된 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [.NET Framework 2.0에 대 한 Windows Forms에 대 한 추가](http://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
