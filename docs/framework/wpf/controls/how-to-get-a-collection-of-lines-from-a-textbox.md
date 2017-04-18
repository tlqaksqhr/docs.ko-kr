---
title: "방법: TextBox에서 줄 컬렉션 가져오기 | Microsoft Docs"
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
  - "선, 컬렉션 가져오기"
  - "TextBox 컨트롤, 선 컬렉션 가져오기"
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: TextBox에서 줄 컬렉션 가져오기
이 예제에서는 <xref:System.Windows.Controls.TextBox>에서 텍스트 줄 컬렉션을 가져오는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.TextBox>를 인수로 받아서 **TextBox**에서 텍스트 줄이 포함된 <xref:System.Collections.Specialized.StringCollection>을 반환하는 간단한 메서드를 보여 줍니다.  <xref:System.Windows.Controls.TextBox.LineCount%2A> 속성은 **TextBox**에 현재 있는 줄 수를 확인하는 데 사용되며 <xref:System.Windows.Controls.TextBox.GetLineText%2A> 메서드는 각 줄을 추출하여 줄 컬렉션에 추가하는 데 사용됩니다.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)