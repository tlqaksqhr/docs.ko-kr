---
title: "방법: Windows Forms에서 컨트롤 고정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c6f7cc527c7409ffecab2ac67386d0f819cce3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>방법: Windows Forms에서 컨트롤 고정
런타임 시 사용자 크기를 조정할 수 있는 폼을 디자인 하는 경우 폼에서 컨트롤의 크기를 조정 하 고 제대로 위치를 변경 해야 합니다. 폼을 사용 하 여 동적으로 컨트롤의 크기를 조정 하려면 사용할 수 있습니다는 <xref:System.Windows.Forms.Control.Anchor%2A> Windows Forms 컨트롤의 속성입니다. <xref:System.Windows.Forms.Control.Anchor%2A> 속성은 컨트롤에 대 한 앵커 위치를 정의 합니다. 폼에 컨트롤 고정 폼의 크기를 조정할 때 컨트롤 컨트롤 앵커 위치 사이의 거리를 유지 합니다. 예를 들어 한 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼의 크기가 조정 왼쪽, 오른쪽 및 폼의 아래쪽 가장자리에 고정 되는 <xref:System.Windows.Forms.TextBox> 컨트롤의 크기가 조정 가로로 폼의 오른쪽 및 왼쪽 면에서 동일 하 게 유지 되도록 합니다. 또한 컨트롤 배치 자체 세로로 위치는 항상 폼의 아래쪽 가장자리 로부터 같은 거리 되도록 합니다. 컨트롤 고정 하지 않으면 폼의 크기를 조정 하는 경우 폼의 가장자리를 기준으로 컨트롤의 위치 변경 됩니다.  
  
 <xref:System.Windows.Forms.Control.Anchor%2A> 속성와 상호 작용 하는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다. 자세한 내용은 참조 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-anchor-a-control-on-a-form"></a>폼에 컨트롤을 고정 하려면  
  
1.  고정 하려는 컨트롤을 선택 합니다.  
  
    > [!NOTE]
    >  CTRL 키를 선택 하는 각 컨트롤을 누른 다음이 절차의 나머지 여 동시에 여러 컨트롤을 고정할 수 있습니다.  
  
2.  에 **속성** 창 오른쪽의 화살표를 클릭는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성입니다.  
  
     편집기는 십자형 표시가 표시 됩니다.  
  
3.  앵커를 설정 하려면 위쪽, 왼쪽, 오른쪽 또는 맨 아래 섹션의 교차를 클릭 합니다.  
  
     컨트롤 위쪽에 고정 되며 기본적으로 유지 됩니다.  
  
4.  고정 된 컨트롤의 측면을 지우려면 십자형에서 해당 막대를 클릭 합니다.  
  
5.  닫습니다는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 편집기 클릭는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 이름을 다시 합니다.  
  
 런타임에 폼에 표시 되 면 폼의 가장자리 로부터 같은 거리에 위치를 유지 하도록 컨트롤 크기가 조정 됩니다. 고정된 된 가장자리에서의 거리는 항상 동일 하 게 유지 거리 Windows Forms 디자이너에 컨트롤을 배치 하는 경우 정의 된 대로 합니다.  
  
> [!NOTE]
>  와 같은 특정 컨트롤에서 <xref:System.Windows.Forms.ComboBox> 는 높이에 제한이 있습니다. 맨 아래 폼 이나 컨테이너 컨트롤을 고정 컨트롤의 높이 제한이을 강제할 수 없습니다.  
  
 상속 된 컨트롤 이어야 합니다 `Protected` 고정 되어야 할 수 있습니다. 컨트롤의 액세스 수준을 변경 하려면 해당 `Modifiers` 속성에는 **속성** 창.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
