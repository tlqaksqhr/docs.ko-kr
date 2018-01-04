---
title: "방법: 런타임에 컨트롤 숨기기"
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
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e28a682c6f3bfc52a293daebeade960c1875bb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>방법: 런타임에 컨트롤 숨기기
런타임 시 표시 되지 않는 사용자 정의 컨트롤 만들기 하려는 경우 경우가 있습니다. 예를 들어 알람 시계에 있는 컨트롤은 경보를 울릴 제외 하 고 볼 수 있습니다. 설정 하 여 쉽게 이렇게는 <xref:System.Windows.Forms.Control.Visible%2A> 속성입니다. 경우는 <xref:System.Windows.Forms.Control.Visible%2A> 속성은 `true`, 컨트롤을 정상적으로 표시 됩니다. 경우 `false`, 컨트롤에 표시 되지 것입니다. 컨트롤의 코드 숨겨진 동안 계속 실행 될 수 있습니다 하지만 사용자 인터페이스를 통해 컨트롤과 상호 작용할 수 없습니다. 사용자 입력 (예: 마우스 클릭)에 계속 응답 보이지 않는 컨트롤을 만들려는 경우에 투명 한 컨트롤을 만들어야 합니다. 자세한 내용은 참조 [컨트롤에 투명 한 배경을 지정](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)합니다.  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>런타임 시 컨트롤을 보이지 않도록 하려면  
  
1.  <xref:System.Windows.Forms.Control.Visible%2A> 속성을 `false`으로 설정합니다.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [방법: 컨트롤에 투명한 배경 적용](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
