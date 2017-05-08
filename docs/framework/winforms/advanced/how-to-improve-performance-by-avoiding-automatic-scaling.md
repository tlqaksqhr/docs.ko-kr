---
title: "방법: 자동 배율 조정 없이 성능 향상 | Microsoft Docs"
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
  - "자동 크기 조정"
  - "이미지[Windows Forms], 성능 향상"
  - "이미지[Windows Forms], 자동 크기 조정 없이 사용"
  - "성능, 이미지 향상"
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 자동 배율 조정 없이 성능 향상
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 사용자가 이미지를 그릴 때 이미지 배율을 자동으로 조정할 수 있습니다. 이 경우 성능이 저하됩니다.  또한 대상 사각형의 크기를 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 전달하여 이미지의 배율을 제어할 수 있습니다.  
  
 예를 들어, <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 대한 아래의 호출에서는 왼쪽 위 모퉁이를 \(50, 30\)으로 지정하고 대상 사각형은 지정하지 않았습니다.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 이 방법은 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 호출하는 데 있어 필요한 인수의 개수가 적다는 점에서는 간편하지만 가장 효율적이지는 않습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에 사용되는 해상도\(일반적으로 96dpi\)가 <xref:System.Drawing.Image> 개체에 저장된 해상도와 다를 경우 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 의해 이미지 배율이 조정됩니다.  예를 들어, <xref:System.Drawing.Image> 개체의 너비가 216픽셀이고 저장된 가로 해상도 값이 72dpi일 수 있습니다.  216\/72는 3이므로 <xref:System.Drawing.Graphics.DrawImage%2A>에 의해 3인치의 너비가 96dpi인 해상도가 되도록 이미지 배율이 조정됩니다.  즉, <xref:System.Drawing.Graphics.DrawImage%2A>에 의해 너비가 96x3 \= 288픽셀인 이미지가 표시됩니다.  
  
 사용자 화면 해상도가 96dpi와 다르더라도 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에 의해 화면 해상도가 96dpi인 것처럼 이미지 배율이 조정됩니다.  다시 말해서 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> 개체는 장치 컨텍스트에 연결되기 때문에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에 의해 장치 컨텍스트에 화면 해상도에 대한 쿼리가 이루어질 때 실제 화면 해상도에 관계없이 결과는 항상 96입니다.  <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 대항 사각형을 지정하여 자동 배율 조정을 수행하지 않을 수 있습니다.  
  
## 예제  
 아래 예제에서는 동일한 이미지를 두 번 그립니다.  첫 번째 이미지에서는 대상 사각형의 너비와 높이를 지정하지 않으므로 이미지의 배율이 자동으로 조정됩니다.  두 번째 이미지에서는 원래 이미지의 너비 및 높이와 동일하게 픽셀 단위로 대상 사각형의 너비와 높이를 지정합니다.  아래 그림에서는 두 번에 걸쳐 렌더링된 이미지를 보여 줍니다.  
  
 ![배율 조정된 질감](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  Texture.jpg를 시스템에서 사용할 수 있는 이미지 이름 및 경로로 바꿉니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)