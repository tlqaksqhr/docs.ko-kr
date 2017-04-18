---
title: "관리 GDI+에서 이미지 인코더 및 디코더 사용 | Microsoft Docs"
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
  - "이미지 디코더, using"
  - "이미지 인코더, using"
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 관리 GDI+에서 이미지 인코더 및 디코더 사용
<xref:System.Drawing> 네임스페이스에서는 이미지를 저장 및 조작하기 위한 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 클래스를 제공합니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 이미지 인코더를 사용하면 메모리의 이미지를 디스크에 쓸 수 있습니다. 또한 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 이미지 디코더를 사용하면 디스크의 이미지를 메모리로 로드할 수 있습니다.  인코더는 <xref:System.Drawing.Image> 또는 <xref:System.Drawing.Bitmap> 개체의 데이터를 지정된 디스크 파일 형식으로 변환합니다.  디코더는 디스크 파일의 데이터를 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 개체에서 요구되는 형식으로 변환합니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에는 다음과 같은 파일 형식을 지원하는 인코더와 디코더가 기본적으로 제공됩니다.  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에는 다음과 같은 파일 형식을 지원하는 디코더가 기본적으로 제공됩니다.  
  
-   WMF  
  
-   EMF  
  
-   아이콘  
  
 다음 항목에서는 인코더와 디코더에 대해 좀 더 자세히 설명합니다.  
  
## 단원 내용  
 [방법: 설치된 인코더 나열](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 컴퓨터에서 사용할 수 있는 인코더를 나열하는 방법에 대해 설명합니다.  
  
 [방법: 설치된 디코더 나열](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 컴퓨터에서 사용할 수 있는 디코더를 나열하는 방법에 대해 설명합니다.  
  
 [방법: 인코더에서 지원하는 매개 변수 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 인코더에서 지원하는 <xref:System.Drawing.Imaging.EncoderParameters>를 나열하는 방법에 대해 설명합니다.  
  
 [방법: BMP 이미지를 PNG 이미지로 변환](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 이미지를 서로 다른 이미지 형식으로 저장하는 방법에 대해 설명합니다.  
  
 [방법: JPEG 압축 수준 설정](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 이미지의 품질 수준을 변경하는 방법에 대해 설명합니다.  
  
## 참조  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## 관련 단원  
 [GDI\+ 관리 코드 정보](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)