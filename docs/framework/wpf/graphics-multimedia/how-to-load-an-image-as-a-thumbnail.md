---
title: "방법: 이미지를 축소판으로 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "이미지, 축소판 그림으로 로드"
  - "축소판 그림으로 이미지 로드"
  - "축소판 그림, 이미지 로드"
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 이미지를 축소판으로 로드
다음 예제에서는 <xref:System.Windows.Controls.Image>를 축소판으로 로드하여 응용 프로그램 메모리를 절약하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 이미지를 로드하는 데 필요한 메모리를 줄이기 위해 <xref:System.Windows.Media.Imaging.BitmapImage>의 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 속성을 설정합니다.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## 예제  
 다음 예제에서는 이미지를 로드하는 데 필요한 메모리를 줄이기 위해 코드에서 <xref:System.Windows.Media.Imaging.BitmapImage>의 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 속성을 설정합니다.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)