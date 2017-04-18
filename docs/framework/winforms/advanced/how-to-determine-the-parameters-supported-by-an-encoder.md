---
title: "방법: 인코더에서 지원하는 매개 변수 확인 | Microsoft Docs"
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
  - "인코더 매개 변수, 지원 여부 확인"
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 인코더에서 지원하는 매개 변수 확인
품질 및 압축 수준 같은 이미지 매개 변수를 조정할 수 있지만 이 경우 특정 이미지 인코더에서 지원되는 매개 변수를 알고 있어야 합니다.  <xref:System.Drawing.Image> 클래스에서는 특정 인코더에서 지원되는 이미지 매개 변수를 확인할 수 있도록 <xref:System.Drawing.Image.GetEncoderParameterList%2A> 메서드를 제공합니다.  인코더는 GUID로 지정합니다.  <xref:System.Drawing.Image.GetEncoderParameterList%2A> 메서드는 <xref:System.Drawing.Imaging.EncoderParameter> 개체의 배열을 반환합니다.  
  
## 예제  
 다음 예제 코드에서는 JPEG 인코더에 대해 지원되는 매개 변수를 출력합니다.  <xref:System.Drawing.Imaging.Encoder> 클래스 개요에 있는 이 매개 변수 범주 및 연관된 GUID 목록을 사용하여 각 매개 변수의 범주를 확인합니다.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Windows Forms 응용 프로그램입니다.  
  
-   <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs>입니다.  
  
## 참고 항목  
 [방법: 설치된 인코더 나열](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [비트맵의 유형](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [관리 GDI\+에서 이미지 인코더 및 디코더 사용](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)