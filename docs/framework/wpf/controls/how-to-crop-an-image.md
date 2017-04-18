---
title: "방법: 이미지 잘라내기 | Microsoft Docs"
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
  - "클래스, CroppedBitmap"
  - "CroppedBitmap 클래스"
  - "이미지 자르기"
  - "이미지, 자르기"
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 이미지 잘라내기
이 예제에서는 <xref:System.Windows.Media.Imaging.CroppedBitmap>을 사용하여 이미지를 잘라내는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>은 이미지의 잘려진 버전을 인코딩하여 파일로 저장할 때 주로 사용됩니다.  표시를 위해 이미지를 잘라내는 방법에 대한 자세한 내용은 [Create a Clip Region](http://msdn.microsoft.com/ko-kr/56e4bed6-78d7-4292-b917-d72d0b3e4376) 항목을 참조하십시오.  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 아래의 샘플에 사용된 리소스를 정의합니다.  
  
 [!code-xml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Imaging.CroppedBitmap>을 소스로 사용하여 이미지를 만듭니다.  
  
 [!code-xml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>을 다른 <xref:System.Windows.Media.Imaging.CroppedBitmap>의 소스로 사용하여 잘라내기 작업을 연속적으로 수행할 수 있습니다.  <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A>는 원래 이미지가 아니라 잘려진 소스 비트맵에 대해 상대적인 값을 사용합니다.  
  
 [!code-xml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## 참고 항목  
 [Create a Clip Region](http://msdn.microsoft.com/ko-kr/56e4bed6-78d7-4292-b917-d72d0b3e4376)