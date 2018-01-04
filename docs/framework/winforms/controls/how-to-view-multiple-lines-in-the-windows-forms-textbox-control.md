---
title: "방법: Windows Forms TextBox 컨트롤에 여러 줄 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dca8d0f869702dee50bf851a2099317c45aa842
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>방법: Windows Forms TextBox 컨트롤에 여러 줄 표시
기본적으로 Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤의 텍스트 한 줄을 표시 하 고 스크롤 막대를 표시 하지 않습니다. 텍스트 사용 가능한 공간 보다 긴 경우에 텍스트의 일부만 표시 됩니다. 설정 하 여이 기본 동작을 변경할 수 있습니다는 <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, 및 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절 한 값입니다.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>TextBox 컨트롤에 캐리지 리턴을 표시 하려면  
  
-   여러 줄에 캐리지 리턴을 표시 하려면 <xref:System.Windows.Forms.TextBox>를 사용 하 여는 <xref:System.Environment.NewLine%2A> 속성입니다.  
  
     알아야 하는 이스케이프 문자를 해석 (\\)는 언어에 따라 다릅니다. Visual Basic 사용 하 여 `Chr$(13) & Chr$(10)` 캐리지 리턴 및 줄 바꿈 문자 조합에 대 한 합니다.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>여러 줄 TextBox 컨트롤에서 보려면  
  
1.  <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`으로 설정합니다. 경우 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 은 `true` (기본값), 컨트롤의 텍스트를 하나 이상의 단락 표시 됩니다; 그렇지 않으면 일부 줄 컨트롤의 가장자리에 잘릴 수 있는 목록으로 표시 됩니다.  
  
2.  <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|텍스트를 단락 수 없는 경우이 값을 사용 하는 컨트롤을 거의 대부분 적합 합니다. 사용자는 텍스트 한 번에 표시할 너무 길면 컨트롤 내부 이동할 수 마우스 포인터를 사용할 수 있습니다.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|너비 보다 클 수 있으며 다음과 같은 줄의 목록을 표시 하려면이 값을 사용 하 여는 <xref:System.Windows.Forms.TextBox> 제어 합니다.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|목록 컨트롤의 높이 보다 클 수 있으며이 값을 사용 합니다.|  
  
3.  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-----------|-----------------|  
    |`false`|컨트롤의에서 텍스트를 자동으로 줄 바꿈됩니다, 줄 바꿈에 도달할 때까지 오른쪽으로 스크롤됩니다. 선택한 경우이 값을 사용 하 여 <xref:System.Windows.Forms.ScrollBars.Horizontal> 스크롤 막대 또는 <xref:System.Windows.Forms.ScrollBars.Both>위의 합니다.|  
    |`true`(기본값)|가로 스크롤 막대가 표시 되지 않습니다. 선택한 경우이 값을 사용 하 여 <xref:System.Windows.Forms.ScrollBars.Vertical> 스크롤 막대 또는 <xref:System.Windows.Forms.ScrollBars.None>위의 하나 이상의 단락 표시를 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 컨트롤 개요](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [방법: 읽기 전용 텍스트 상자 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [방법: 문자열에 인용 부호 넣기](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
