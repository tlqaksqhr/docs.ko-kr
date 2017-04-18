---
title: "방법: JPEG 압축 수준 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "이미지[Windows Forms], 인코더 매개 변수 변경"
  - "JPEG 이미지, 품질 수준 설정"
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: JPEG 압축 수준 설정
이미지를 디스크에 저장할 때는 파일 크기를 최소화하거나 이미지 품질을 개선하기 위해 이미지의 매개 변수를 수정해야 할 수 있습니다.  이미지의 압축 수준을 수정하면 JPEG 이미지의 품질을 조정할 수 있습니다.  JPEG 이미지를 저장할 때 압축 수준을 지정하려면 <xref:System.Drawing.Imaging.EncoderParameters> 개체를 만들어 <xref:System.Drawing.Image> 클래스의 <xref:System.Drawing.Image.Save%2A> 메서드에 전달해야 합니다.  <xref:System.Drawing.Imaging.EncoderParameters> 개체에 하나의 <xref:System.Drawing.Imaging.EncoderParameter>로 구성된 배열이 포함되도록 해당 개체를 초기화합니다.  <xref:System.Drawing.Imaging.EncoderParameter>를 만드는 경우 <xref:System.Drawing.Imaging.Encoder.Quality> 인코더와 원하는 압축 수준을 지정합니다.  
  
## 예제  
 다음 예제 코드에서는 <xref:System.Drawing.Imaging.EncoderParameter> 개체를 만들고 세 개의 JPEG 이미지를 저장합니다.  각 JPEG 이미지는 <xref:System.Drawing.Imaging.EncoderParameter> 생성자에 전달된 `long` 값을 수정하여 서로 다른 품질 수준으로 저장됩니다.  품질 수준이 0이면 가장 큰 압축률에 해당하며 품질 수준이 100이면 가장 낮은 압축률에 해당합니다.  
  
 [!code-csharp[UsingImageEncodersDecoders#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#8)]
 [!code-vb[UsingImageEncodersDecoders#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#8)]  
[!code-csharp[UsingImageEncodersDecoders#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#6)]
[!code-vb[UsingImageEncodersDecoders#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#6)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Windows Forms 응용 프로그램입니다.  
  
-   <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs>입니다.  
  
-   **c:\\**에 있는 `TestPhoto.jpg`라는 이미지 파일입니다.  
  
## 참고 항목  
 [방법: 인코더에서 지원하는 매개 변수 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)   
 [비트맵의 유형](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [관리 GDI\+에서 이미지 인코더 및 디코더 사용](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)