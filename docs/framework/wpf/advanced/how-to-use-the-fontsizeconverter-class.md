---
title: "방법: FontSizeConverter 클래스 사용 | Microsoft Docs"
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
  - "FontSizeConverter 개체"
  - "입력 체계, FontSizeConverter 개체"
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: FontSizeConverter 클래스 사용
## 예제  
 이 예제에서는<xref:System.Windows.FontSizeConverter> 인스턴스를 만들어 이를 통해 글꼴 크기를 변경하는 방법을 보여 줍니다.  
  
 이 예제에서는 별도의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일에 정의되어 있는 대로 <xref:System.Windows.Controls.ListBoxItem>의 콘텐츠를 <xref:System.Double> 인스턴스로 변환하고 나중에 다시 <xref:System.String>으로 변환하는 `changeSize`라는 사용자 지정 메서드를 정의합니다.  이 메서드는 <xref:System.Windows.FontSizeConverter> 개체에 <xref:System.Windows.Controls.ListBoxItem>을 전달하고 이는 <xref:System.Windows.Controls.ListBoxItem>의 <xref:System.Windows.Controls.ContentControl.Content%2A>를 <xref:System.Double> 인스턴스로 변환합니다.  그런 다음 이 값을 <xref:System.Windows.Controls.TextBlock> 요소의 <xref:System.Windows.Controls.TextBlock.FontSize%2A> 속성 값으로 다시 전달합니다.  
  
 이 예제에서는 `changeFamily`라는 두 번째 사용자 지정 메서드도 정의합니다.  이 메서드는 <xref:System.Windows.Controls.ListBoxItem>의 <xref:System.Windows.Controls.ContentControl.Content%2A>를 <xref:System.String>으로 변환한 다음 이 값을 <xref:System.Windows.Controls.TextBlock> 요소의 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 속성에 전달합니다.  
  
 이 예제는 실행되지 않습니다.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## 참고 항목  
 <xref:System.Windows.FontSizeConverter>