---
title: "방법: 컨트롤에 투명한 배경 적용 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 투명한 배경"
  - "투명성, Windows Forms 사용자 지정 컨트롤"
  - "투명한 배경, 사용자 지정 컨트롤"
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 방법: 컨트롤에 투명한 배경 적용
.NET Framework의 이전 버전에서는 양식 생성자에 먼저 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 설정하지 않으면 컨트롤이 투명 배경색 설정을 지원하지 않았습니다. 현재 프레임워크 버전에서는 대부분의 컨트롤에 대한 배경색을 디자인 타임에 **속성** 창 또는 양식 생성자의 코드에서 <xref:System.Drawing.Color.Transparent%2A>으로 설정할 수 있습니다.  
  
> [!NOTE]
>  Windows Forms 컨트롤은 진정한 투명성을 지원하지 않습니다. 투명한 Windows Forms 컨트롤의 배경은 해당 부모가 색칠합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 속성이 <xref:System.Drawing.Color.Transparent%2A>으로 설정된 경우에도 <xref:System.Windows.Controls.Button> 컨트롤은 투명한 배경색을 지원하지 않습니다.  
  
### 컨트롤에 투명한 배경색을 적용하려면  
  
-   속성 창에서 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 속성을 선택하고 <xref:System.Drawing.Color.Transparent%2A>으로 설정합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [관리되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)   
 [방법: 불투명 및 반투명 선 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)