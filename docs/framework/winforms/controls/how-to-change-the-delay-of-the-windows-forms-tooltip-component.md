---
title: "방법: Windows Forms ToolTip 구성 요소의 지연 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48bb8c08fa02a54f9bfd3febbe99f683fd68d7f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>방법: Windows Forms ToolTip 구성 요소의 지연 변경
Windows Forms에 대해 설정할 수 있는 지연 값이 여러 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다. 이러한 모든 속성에 대 한 측정 단위는 밀리초입니다. <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 속성 표시할 도구 설명 문자열에 대 한 연결된 된 컨트롤에 가리키고 있어야 기간을 결정 합니다. <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 속성 후속 도구 설명 문자열이 다른 한 도구 설명과 연관 된 컨트롤에서 마우스를 이동할 때 나타나는 데 걸리는 시간 (밀리초)의 수를 설정 합니다. <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 속성 도구 설명 문자열이 표시 되는 시간의 길이 결정 합니다. 값을 설정 하 여 개별적으로 또는 이러한 값을 설정할 수는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성, 속성에 할당 된 값에 따라 설정 됩니다는 지연 된 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성. 예를 들어, <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> N 값으로 설정 되어 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> N로 설정 되어 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 의 값으로 설정 되어 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 5로 나눈 (또는 N/5) 및 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 다섯 번의 값에 해당 값으로 설정 됩니다는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성 (또는 5N).  
  
### <a name="to-set-the-delay"></a>지연 시간을 설정 하려면  
  
1.  이 예제에 나와 있는 것 처럼 다음 속성을 설정 합니다.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [ToolTip 구성 요소](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
