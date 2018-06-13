---
title: '방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: 5abe233a240e74e41d4defad060383aec155ea71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529278"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기
맞추고에서 컨트롤을 늘일 수는 <xref:System.Windows.Forms.TableLayoutPanel> 와 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-align-and-stretch-a-control"></a>맞춤 및 늘이기 컨트롤을  
  
1.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 의 왼쪽 위 셀으로는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. <xref:System.Windows.Forms.Button> 컨트롤의 셀에 가운데 맞춤 됩니다.  
  
3.  값으로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Left,Right`합니다. <xref:System.Windows.Forms.Button> 컨트롤이 있는 셀의 너비에 맞게 늘어납니다.  
  
4.  값으로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top,Bottom`합니다. <xref:System.Windows.Forms.Button> 컨트롤이 있는 셀의 높이 맞게 늘어납니다.  
  
5.  값으로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다. <xref:System.Windows.Forms.Button> 컨트롤이 확장 되어 셀을 채웁니다.  
  
6.  값으로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.None>합니다. <xref:System.Windows.Forms.Button> 컨트롤 원래 크기를 반환 하 고 셀의 왼쪽 위 모퉁이로 이동 합니다. **Windows Forms 디자이너** 가 설정 된 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top, Left`합니다.  
  
7.  값으로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Bottom,Right`합니다. <xref:System.Windows.Forms.Button> 컨트롤이 있는 셀의 오른쪽 아래 모서리에 이동 합니다.  
  
8.  값으로 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.None>합니다. <xref:System.Windows.Forms.Button> 컨트롤이 셀의 중앙으로 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
