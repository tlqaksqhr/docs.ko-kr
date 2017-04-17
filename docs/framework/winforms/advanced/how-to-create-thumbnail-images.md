---
title: "방법: 축소판 이미지 만들기 | Microsoft Docs"
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
  - "이미지[Windows Forms], 축소판 만들기"
  - "축소판 이미지, 만들기"
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 방법: 축소판 이미지 만들기
축소판 이미지는 이미지를 축소한 버전입니다.  <xref:System.Drawing.Image> 개체의 <xref:System.Drawing.Image.GetThumbnailImage%2A> 메서드를 호출하여 축소판 이미지를 만들 수 있습니다.  
  
## 예제  
 다음 예제에서는 JPG 파일에서 <xref:System.Drawing.Image> 개체를 만듭니다.  원래 이미지의 너비는 640픽셀이고 높이는 479픽셀입니다.  이 코드에서는 너비와 높이가 100 픽셀인 축소판 이미지를 만듭니다.  
  
 아래 그림에 축소판 이미지가 나와 있습니다.  
  
 ![축소판 이미지](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  이 예제에서는 콜백 메서드가 선언되지만 사용되지는 않습니다.  이는 GDI\+의 모든 버전을 지원합니다.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  예제를 실행하려면 다음 단계를 수행합니다.  
  
1.  새 Windows Forms 응용 프로그램을 만듭니다.  
  
2.  예제 코드를 폼에 추가합니다.  
  
3.  폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트에 대한 처리기를 만듭니다.  
  
4.  <xref:System.Windows.Forms.Control.Paint> 처리기에서 `GetThumbnail` 메서드를 호출하고 <xref:System.Windows.Forms.PaintEventArgs>에 `e` 를 전달합니다.  
  
5.  미리 보기를 만들 이미지 파일을 찾습니다.  
  
6.  `GetThumbnail` 메서드에서 이미지의 경로 및 파일 이름을 지정합니다.  
  
7.  F5 키를 눌러 예제를 실행합니다.  
  
     100 X 100 크기의 미리 보기 이미지가 폼에 나타납니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)