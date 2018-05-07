---
title: TableLayoutPanel 컨트롤의 AutoSize 동작
ms.date: 03/30/2017
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: 497991106d151cfe1f3944977828e9c77c27e526
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>TableLayoutPanel 컨트롤의 AutoSize 동작
## <a name="distinct-autosize-behaviors"></a>고유 AutoSize 동작  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 다음과 같은 방법으로 자동 크기 조정 동작을 지원 합니다.  
  
-   통해는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성  
  
-   통해는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일입니다.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>행과 열 스타일을 사용 하 여 AutoSize 속성  
 다음 표에서 설명 간의 상호 작용은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일입니다.  
  
|자동 크기 조정 설정|스타일 상호 작용|  
|----------------------|-----------------------|  
|`false`|<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 왼쪽에서 오른쪽으로 진행 하 고 다음과 같은 순서로 또는 열 이나 행에 대 한 공간을 할당 합니다.<br /><br /> 1.  경우는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성이 <xref:System.Windows.Forms.SizeType.Absolute>, 하 여 지정 된 픽셀 수 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 할당 됩니다.<br />2.  경우는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성이 <xref:System.Windows.Forms.SizeType.AutoSize>, 자식 컨트롤에 의해 반환 되는 픽셀 수가 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드를 할당 합니다.<br />3.  모든 공간 후 <xref:System.Windows.Forms.SizeType.Absolute> 및 <xref:System.Windows.Forms.SizeType.AutoSize> 열 이나 행은 할당 된 모든 열 이나 행으로 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 로 설정 <xref:System.Windows.Forms.SizeType.Percent> 비례적으로 남은 공간을 할당 하는 데 사용 됩니다|  
|`true`|위의 상호 예외와 유사한는 <xref:System.Windows.Forms.SizeType.Percent> 열 이나 행 획득 한 자동 크기 조정 끝점이 있습니다.<br /><br /> <xref:System.Windows.Forms.TableLayoutPanel> 열 이나 행 충분 한 여유 공간을 확보할 컨트롤이 확장 되어 있도록 없는 열 이나 행으로 <xref:System.Windows.Forms.SizeType.Percent> 스타일 지정에는 해당 내용이 잘리지 합니다. <xref:System.Windows.Forms.TableLayoutPanel> 비율에 따라 새 공간을 할당 하는 컨트롤의 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 속성입니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [TableLayoutPanel 컨트롤 개요](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
