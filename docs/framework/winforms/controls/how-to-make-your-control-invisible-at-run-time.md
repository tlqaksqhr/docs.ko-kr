---
title: "방법: 런타임에 컨트롤 숨기기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 런타임에 숨기기"
  - "사용자 지정 컨트롤[Windows Forms], 보이지 않는 상태"
  - "보이지 않는 컨트롤"
  - "런타임, 컨트롤 숨기기"
  - "사용자 정의 컨트롤[Windows Forms], 보이지 않는 상태"
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 런타임에 컨트롤 숨기기
런타임에 사용자에게 표시되지 않는 사용자 정의 컨트롤을 만들 수도 있습니다.  예를 들어, 경보 시계 컨트롤은 경보를 울릴 때를 제외하면 사용자에게 표시되지 않습니다.  <xref:System.Windows.Forms.Control.Visible%2A> 속성을 설정하면 손쉽게 이를 수행할 수 있습니다.  <xref:System.Windows.Forms.Control.Visible%2A> 속성이 `true`이면 컨트롤이 정상적으로 표시되고  `false`이면 숨겨집니다.  컨트롤이 숨겨진 동안에도 컨트롤의 코드는 여전히 실행되지만 사용자 인터페이스를 통해 컨트롤과 상호 작용할 수 없습니다.  보이지 않는 동안에도 마우스 클릭과 같은 사용자 입력에 계속 응답하는 컨트롤을 만들려면 투명한 컨트롤을 만들어야 합니다.  자세한 내용은 [컨트롤에 투명한 배경 적용](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)을 참조하십시오.  
  
### 런타임에 컨트롤을 숨기려면  
  
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
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.Visible%2A>   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [방법: 컨트롤에 투명한 배경 적용](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)