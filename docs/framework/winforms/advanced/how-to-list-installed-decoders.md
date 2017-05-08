---
title: "방법: 설치된 디코더 나열 | Microsoft Docs"
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
  - "이미지 코덱, 목록 표시"
  - "이미지 디코더, 목록 표시"
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 설치된 디코더 나열
응용 프로그램에서 특정 이미지 파일 형식을 읽을 수 있는지 여부를 확인하기 위해 컴퓨터에서 사용할 수 있는 이미지 디코더를 나열해야 할 수 있습니다.  <xref:System.Drawing.Imaging.ImageCodecInfo> 클래스에서는 이미지 디코더를 사용할 수 있는지 확인할 수 있도록 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 정적 메서드를 제공합니다.  <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>는 <xref:System.Drawing.Imaging.ImageCodecInfo> 개체의 배열을 반환합니다.  
  
## 예제  
 다음 코드 예제에서는 설치된 디코더와 해당 속성 값의 목록을 출력합니다.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Windows Forms 응용 프로그램입니다.  
  
-   <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs>입니다.  
  
## 참고 항목  
 [방법: 설치된 인코더 나열](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [관리 GDI\+에서 이미지 인코더 및 디코더 사용](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)