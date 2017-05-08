---
title: "방법: 메타파일 로드 및 표시 | Microsoft Docs"
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
  - "예제[Windows Forms], 메타파일"
  - "메타파일, 표시"
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 메타파일 로드 및 표시
<xref:System.Drawing.Image> 클래스에서 상속되는 <xref:System.Drawing.Imaging.Metafile> 클래스에는 벡터 이미지를 기록하고 표시 및 검사하는 데 사용하는 메서드가 있습니다.  
  
## 예제  
 화면에 벡터 이미지\(메타파일\)를 표시하려면 <xref:System.Drawing.Imaging.Metafile> 개체와 <xref:System.Drawing.Graphics> 개체가 필요합니다.  파일 또는 스트림의 이름을 <xref:System.Drawing.Imaging.Metafile> 생성자에 전달합니다.  <xref:System.Drawing.Imaging.Metafile> 개체를 만든 뒤에는 이 <xref:System.Drawing.Imaging.Metafile> 개체를 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 전달합니다.  
  
 다음 예제에서는 EMF\(확장 메타파일\) 파일을 사용하여 <xref:System.Drawing.Imaging.Metafile> 개체를 만든 다음 왼쪽 위 모퉁이가 \(60, 10\)인 이미지를 그립니다.  
  
 아래 그림에서는 지정한 위치에 그려진 메타파일을 보여 줍니다.  
  
 ![이미지 위치](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)