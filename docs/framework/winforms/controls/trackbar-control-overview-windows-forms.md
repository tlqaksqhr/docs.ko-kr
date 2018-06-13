---
title: TrackBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: d0a0cbbcc618e2fa52b3719bcc8f0135a1e0752e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535999"
---
# <a name="trackbar-control-overview-windows-forms"></a>TrackBar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.TrackBar> 많은 양의 정보를 통해 탐색 또는 시각적으로 숫자 설정을 조정 하는 것에 대 한 제어도 ("slider" 컨트롤) 사용 됩니다. <xref:System.Windows.Forms.TrackBar> 컨트롤에는 두 부분이:는 엄지 단추 라고도 슬라이더의 눈금 표시 합니다. 엄지 단추는 조정할 수 있는 일부입니다. 엄지 단추의 위치는 <xref:System.Windows.Forms.TrackBar.Value%2A> 속성입니다. 눈금 표시 되는 일정 한 간격을 두고 배치 되어 시각적 표시기입니다. Trackbar에서 가로 또는 세로로 정렬 될을 지정 하는 이동 합니다. 예를 들어 시스템에 대 한 커서 깜박임 마우스 속도 제어 하려면 트랙 표시줄을 사용할 수 있습니다.  
  
## <a name="key-properties"></a>키 속성  
 키 속성은 <xref:System.Windows.Forms.TrackBar> 제어 <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, 및 <xref:System.Windows.Forms.TrackBar.Maximum%2A>합니다. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> 눈금 사이의 간격이입니다. <xref:System.Windows.Forms.TrackBar.Minimum%2A> 및 <xref:System.Windows.Forms.TrackBar.Maximum%2A> 트랙 표시줄에 나타낼 수 있는 최소 및 최대 값입니다.  
  
 다른 두 개의 중요 한 속성은 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 및 <xref:System.Windows.Forms.TrackBar.LargeChange%2A>합니다. 값은 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 속성은 위치가 엄지 단추를 왼쪽 또는 오른쪽 화살표 키를 누르면 지정 하는 응답 이동의 수입니다. 값은 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 속성은 엄지 단추를 지정 하는 PAGE UP 또는 PAGE DOWN 키를 누른 상태에 대 한 응답에서으로 이동 또는 조정 컨트롤의 어느 쪽에 트랙 표시줄 위에 클릭 마우스에 대 한 응답에서 위치의 수입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TrackBar>  
 [TrackBar 컨트롤](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
