---
title: "방법: TextBox 컨트롤에서 탭 문자 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "탭 문자, 사용"
  - "TextBox 컨트롤, 탭 문자 사용"
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: TextBox 컨트롤에서 탭 문자 사용
이 예제에서는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 탭 문자를 일반 입력으로 허용하도록 설정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.TextBox> 컨트롤에서 탭 문자를 입력으로 허용하도록 하려면 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> 특성을 **true**로 설정합니다.  
  
 [!code-xml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)