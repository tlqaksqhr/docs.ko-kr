---
title: "FlowLayoutPanel 컨트롤 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7eafe31bec86a969a12661c9f5629b2d55e3e3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="flowlayoutpanel-control-overview"></a>FlowLayoutPanel 컨트롤 개요
<xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤은 수평 또는 수직 방향으로 내용을 정렬합니다. 컨트롤의 내용을 한 행에서 다음 행으로 또는 한 열에서 다음 열로 줄 바꿈할 수 있습니다. 또는 해당 내용을 줄 바꿈하는 대신 잘라낼 수 있습니다.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> 속성의 값을 설정하여 흐름 방향을 지정할 수 있습니다. <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤은 RTL(오른쪽에서 왼쪽) 레이아웃에서 흐름 방향을 올바르게 반대로 바꿉니다. <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> 속성의 값을 설정하여 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 내용을 줄 바꿈할지 또는 잘라낼지 지정할 수도 있습니다.  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`로 설정하면 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤이 해당 내용에 맞게 자동으로 크기를 조정합니다. 또한 제공 된 **FlowBreak** 자식 컨트롤에 속성입니다. FlowBreak 속성의 값을 `true` 로 설정하면 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤이 현재 흐름 방향에서 컨트롤 레이아웃을 중지하고 다음 행이나 열로 줄 바꿈합니다.  
  
 Windows Forms 컨트롤은 <xref:System.Windows.Forms.FlowLayoutPanel>의 다른 인스턴스를 포함하여 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 자식일 수 있습니다. 이 기능을 통해 런타임에 폼의 크기에 맞춰 조정되는 정교한 레이아웃을 생성할 수 있습니다.  
  
 또한 참조 [연습: Windows Forms 사용 하 여 FlowLayoutPanel에서 컨트롤 정렬](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [FlowLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
