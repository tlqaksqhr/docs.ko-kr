---
title: '방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: e067966b606d77ceb9d11d2784c0d5f73ad332a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정
Windows Forms <xref:System.Windows.Forms.Label> 또는 여러 줄 컨트롤이 될 수 있으며 자동으로 크기를 조정할 수의 캡션을 맞게 자동 하거나 크기에서 고정 될 수 있습니다. <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 사용 하면를 캡션에 맞게 컨트롤 크기 조정 되는 런타임 시 캡션이 변경 하는 경우에 특히 유용 합니다.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>내용에 맞게 동적으로 조정 레이블 컨트롤 만들기  
  
1.  설정의 <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 `true`합니다.  
  
 경우 <xref:System.Windows.Forms.Label.AutoSize%2A> 로 설정 된 `false`, 지정 된 단어는 <xref:System.Windows.Forms.Label.Text%2A> 속성은 가능한 경우 다음 줄으로 줄 바꿈이 되지만 컨트롤 증가 하지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Label 컨트롤 개요](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [레이블 컨트롤](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
