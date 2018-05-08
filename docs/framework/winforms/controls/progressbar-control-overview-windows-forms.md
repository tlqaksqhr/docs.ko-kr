---
title: ProgressBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: bd2b9615b0061a8f2133229edb49357cde69b39e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="progressbar-control-overview-windows-forms"></a>ProgressBar 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.ProgressBar> 컨트롤의 가로 막대에 정렬 된 사각형으로 적절 한 수를 표시 하 여 프로세스의 진행률을 나타냅니다. 프로세스가 완료 되 면 막대가 채워집니다. 진행률 표시줄 방법 이해할 사용자에 게 일반적으로 사용 되는 프로세스를 완료; 기다려야 하 예를 들어 때 큰 파일은 로드 중입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ProgressBar> 컨트롤 수만 수 가로 방향으로 놓여 폼에 있습니다.  
  
## <a name="key-properties-and-methods"></a>키 속성 및 메서드  
 키 속성은 <xref:System.Windows.Forms.ProgressBar> 제어 <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A>합니다. <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성 진행률 표시줄에 표시 최대값과 최소값을 설정 합니다. <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성은 작업 이루어졌을 진행률을 나타냅니다. 컨트롤에 표시 되는 표시줄 블록으로 구성 된 값으로 표시 된 <xref:System.Windows.Forms.ProgressBar> 제어 대략적는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 현재 값입니다. 크기에 따라는 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 다음 블록을 표시 하는 시기를 결정 합니다.  
  
 현재 진행률 값을 업데이트 하는 가장 일반적인 방법은 설정 하는 코드를 작성 하 여 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다. 큰 파일을 로드 하의 예제에서는 최대 (킬로바이트)에서 파일의 크기를 설정할 수 있습니다. 예를 들어 경우는 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성이 100으로 설정 되어는 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 10, 속성 및 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성이 설정 되어 50 5 사각형이 표시 됩니다. 표시 될 수 있는 수의 절반입니다.  
  
 그러나 표시 하는 값을 수정할 수 있는 방법이 있습니다.는 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 설정 하는 것 외의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 직접 합니다. <xref:System.Windows.Forms.ProgressBar.Step%2A> 증가 시킬 값을 지정 하려면 속성을 사용할 수는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다. 그런 다음 호출에서 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 메서드 값이 증가 됩니다. 증분 값을 변경 하는 데는 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 메서드 값을 지정 하 고는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다.  
  
 그래픽으로 현재 작업에 대 한 사용자에 게 알려 주는 또 다른 컨트롤로 <xref:System.Windows.Forms.StatusBar> 제어 합니다.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤 교체 및 기능을 추가 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나는 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 버전과 호환성 및 이후 사용에 대 한 컨트롤이 유지 되는 경우 있습니다 이 옵션을 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ProgressBar>  
 [ProgressBar 컨트롤](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
