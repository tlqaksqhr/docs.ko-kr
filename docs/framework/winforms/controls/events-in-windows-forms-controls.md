---
title: "Windows Forms 컨트롤의 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dba74214fe439e09d1855f7ab248c075bd8257c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="events-in-windows-forms-controls"></a>Windows Forms 컨트롤의 이벤트
Windows Forms 컨트롤의 60 개 이상의 이벤트 상속 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다. 여기에 <xref:System.Windows.Forms.Control.Paint> 이벤트는 컨트롤을 그릴 수 있도록,와 같은 창에 표시와 관련 된 이벤트는 <xref:System.Windows.Forms.Control.Resize> 및 <xref:System.Windows.Forms.Control.Layout> 이벤트 및 하위 수준 마우스 및 키보드 이벤트입니다. 일부 하위 수준 이벤트에서 합성 됩니다 <xref:System.Windows.Forms.Control> 와 같은 의미 이벤트로 <xref:System.Windows.Forms.Control.Click> 및 <xref:System.Windows.Forms.Control.DoubleClick>합니다. 상속 된 이벤트에 대 한 세부 정보를 참조 하십시오. <xref:System.Windows.Forms.Control>합니다.  
  
 사용자 지정 컨트롤이 상속된 이벤트 기능을 재정의해야 하는 경우 대리자를 연결하는 대신 상속된 `On`*EventName* 메서드를 재정의합니다. .NET Framework에서 이벤트 모델에 익숙하지 않다면 [구성 요소에서 이벤트 발생 시키기](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [OnPaint 메서드 재정의](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [사용자 입력 처리](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [이벤트 정의](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [이벤트](../../../../docs/standard/events/index.md)
