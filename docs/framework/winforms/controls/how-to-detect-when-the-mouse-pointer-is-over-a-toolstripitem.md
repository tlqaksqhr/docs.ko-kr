---
title: "방법: 마우스 포인터가 ToolStripItem을 가리키는 시점 감지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 633b92bf6da837b3727001c621548fa58b230102
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>방법: 마우스 포인터가 ToolStripItem을 가리키는 시점 감지
다음 절차를 사용 하 여 마우스 포인터를 위로 가져갈 때 검색 하는 <xref:System.Windows.Forms.ToolStripItem>합니다.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>포인터가 toolstripitem을 가리키는 시점 감지 하려면  
  
-   사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.Selected%2A> 는 항목에 대 한 속성 <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> 은 `true`합니다.  
  
     이렇게 하면 사용자를 동기화 하는 것과 <xref:System.Windows.Forms.ToolStripItem.MouseEnter> 및 <xref:System.Windows.Forms.ToolStripItem.MouseLeave> 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
