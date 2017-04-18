---
title: "방법: Windows Forms ToolTip 구성 요소의 지연 변경 | Microsoft Docs"
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
  - "예제[Windows Forms], 도구 설명"
  - "ToolTip 구성 요소[Windows Forms], 지연 값"
  - "도구 설명[Windows Forms], 지연 값"
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms ToolTip 구성 요소의 지연 변경
Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소에 여러 개의 지연 값을 설정할 수 있습니다.  이러한 속성의 측정 단위는 모두 밀리초입니다.  <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 속성은 사용자가 도구 설명 문자열이 나타날 때까지 연결된 컨트롤을 가리켜야 하는 시간을 결정하고  <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 속성은 도구 설명이 연결된 한 컨트롤에서 다른 컨트롤로 마우스를 움직일 때 다음 도구 설명 문자열이 나타나는 데 소요되는 시간을 결정합니다\(밀리초\).  또한 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 속성은 도구 설명 문자열이 표시되는 시간을 결정합니다.  이러한 값은 개별적으로 또는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성의 값을 설정하여 지정할 수 있습니다. 다른 지연 속성은 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성에 할당된 값을 기초로 설정됩니다.  예를 들어 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>의 값이 N으로 설정되면 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>는 N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>를 5로 나눈 값\(N\/5\), <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성 값에 5를 곱한 값\(5N\)으로 설정됩니다.  
  
### 지연을 설정하려면  
  
1.  이 예제를 참조하여 다음 속성을 설정합니다.  
  
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
  
## 참고 항목  
 [ToolTip 구성 요소 개요](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [ToolTip 구성 요소](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)