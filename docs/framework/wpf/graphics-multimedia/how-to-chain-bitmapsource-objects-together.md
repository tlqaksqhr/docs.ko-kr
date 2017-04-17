---
title: "방법: 여러 BitmapSource 개체 연결 | Microsoft Docs"
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
  - "BitmapSource 개체, 연결"
  - "BitmapSource 개체 연결"
  - "그래픽, BitmapSource 개체 연결"
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 여러 BitmapSource 개체 연결
이 예제에서는 <xref:System.Windows.Media.Imaging.BitmapSource>에서 파생된 여러 개의 개체를 연결하여 이미지 소스에 다양한 효과를 적용하는 방법을 보여 줍니다.  
  
 다음 예제에서는 연결을 통해 이미지 소스를 대칭 이동하고 이미지 소스의 픽셀 형식을 변경합니다.  
  
## 예제  
 [!code-xml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]