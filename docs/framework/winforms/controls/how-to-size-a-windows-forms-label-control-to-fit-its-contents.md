---
title: "방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정 | Microsoft Docs"
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
  - "캡션, 크기 조정"
  - "Label 컨트롤[Windows Forms], 내용에 맞게 크기 조정"
  - "레이블, 내용에 맞게 크기 조정"
  - "크기, 컨트롤"
  - "컨트롤 크기 조정"
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정
Windows Forms <xref:System.Windows.Forms.Label> 컨트롤은 한 줄이나 여러 줄이 될 수 있고 크기를 고정시키거나 해당 컨트롤을 캡션에 맞게 크기가 자동으로 조정되도록 만들 수 있습니다.  <xref:System.Windows.Forms.Label.AutoSize%2A> 속성은 컨트롤의 크기를 캡션에 맞게 조정하므로 런타임에 캡션이 변경되는 경우에 특히 유용합니다.  
  
### 내용에 따라 label 컨트롤의 크기를 동적으로 조정하려면  
  
1.  <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 `true`로 설정합니다.  
  
 <xref:System.Windows.Forms.Label.AutoSize%2A>가 `false`로 설정된 경우 <xref:System.Windows.Forms.Label.Text%2A> 속성에 지정된 단어가 가능한 경우 줄 바꿈 되지만 이로 인해 컨트롤이 커지지는 않습니다.  
  
## 참고 항목  
 [방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)   
 [Label 컨트롤 개요](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Label 컨트롤](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)