---
title: "방법: 이미지 자르기 및 배율 조정 | Microsoft Docs"
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
  - "이미지[Windows Forms], 자르기"
  - "이미지[Windows Forms], 배율"
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 이미지 자르기 및 배율 조정
<xref:System.Drawing.Graphics> 클래스에는 몇 가지 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드가 있으며, 그 중 일부에는 이미지를 자르고 배율을 조정하는 데 사용할 수 있는 원본 및 대상 사각형 매개 변수가 있습니다.  
  
## 예제  
 아래 예제에서는 디스크에 있는 Apple.gif 파일을 사용하여 <xref:System.Drawing.Image> 개체를 만듭니다.  이 코드에서는 원래 크기로 전체 사과 이미지를 그린 다음,  <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 호출하여 원래 사과 이미지보다 큰 대상 사각형에 사과의 일부분을 그립니다.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에서는 세 번째, 네 번째, 다섯 번째 및 여섯 번째 인수에 지정된 원본 사각형을 조사하여 사과의 어느 부분을 그릴지 결정합니다.  이 예제에서는 사과를 원래 너비 및 높이의 75%로 자릅니다.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에서는 두 번째 인수에 지정된 대상 사각형을 조사하여 자른 사과를 그릴 위치 및 배율을 결정합니다.  이 예제에서 대상 사각형은 원래 이미지보다 너비 및 높이가 30% 더 큽니다.  
  
 아래 그림에서는 원래 사과 및 일부를 잘라 배율을 조정한 사과를 보여 줍니다.  
  
 ![자르기 및 배율 조정](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  `Apple.gif`를 시스템에서 사용할 수 있는 이미지 파일 이름 및 경로로 바꿔야 합니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)