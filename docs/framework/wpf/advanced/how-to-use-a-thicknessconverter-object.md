---
title: "방법: ThicknessConverter 개체 사용 | Microsoft Docs"
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
  - "테두리 두께"
  - "ThicknessConverter 개체"
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ThicknessConverter 개체 사용
## 예제  
 이 예제에서는<xref:System.Windows.ThicknessConverter> 인스턴스를 만들어 이를 통해 테두리 두께를 변경하는 방법을 보여 줍니다.  
  
 이 예제에서는 별도의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일에 정의되어 있는 대로 <xref:System.Windows.Controls.ListBoxItem>의 콘텐츠를 <xref:System.Windows.Thickness> 인스턴스로 변환하고 나중에 다시 <xref:System.String>으로 변환하는 `changeThickness`라는 사용자 지정 메서드를 정의합니다.  이 메서드는 <xref:System.Windows.ThicknessConverter> 개체에 <xref:System.Windows.Controls.ListBoxItem>을 전달하고 이는 <xref:System.Windows.Controls.ListBoxItem>의 <xref:System.Windows.Controls.ContentControl.Content%2A>를 <xref:System.Windows.Thickness> 인스턴스로 변환합니다.  그런 다음 이 값을 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Border.BorderThickness%2A> 속성 값으로 다시 전달합니다.  
  
 이 예제는 실행되지 않습니다.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Thickness>   
 <xref:System.Windows.ThicknessConverter>   
 <xref:System.Windows.Controls.Border>   
 [How to: Change the Margin Property](http://msdn.microsoft.com/ko-kr/8a313efd-5f99-4097-b4c1-8fa49d8379a2)   
 [How to: Convert a ListBoxItem to a new Data Type](http://msdn.microsoft.com/ko-kr/7a080b88-184e-4b27-bb61-d42bafba9727)   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)