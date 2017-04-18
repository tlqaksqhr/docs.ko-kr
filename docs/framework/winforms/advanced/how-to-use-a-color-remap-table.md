---
title: "방법: 색 매핑 변경 테이블 사용 | Microsoft Docs"
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
  - "색 매핑 변경 테이블, using"
  - "색 테이블, 색 매핑 변경"
  - "사용자 지정 색, 색 매핑 변경 테이블로 만들기"
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 색 매핑 변경 테이블 사용
매핑 변경은 색 매핑 변경 테이블에 따라 이미지의 색을 변환하는 과정입니다.  색 매핑 변경 테이블은 <xref:System.Drawing.Imaging.ColorMap> 개체의 배열입니다.  배열의 각 <xref:System.Drawing.Imaging.ColorMap> 개체에는 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 속성과 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성이 있습니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 이미지를 그릴 때 이미지의 각 픽셀을 이전 색의 배열과 비교합니다.  픽셀의 색이 이전 색과 일치하면 상응하는 새로운 색으로 변경됩니다.  이러한 색 변경은 렌더링에만 적용되며, <xref:System.Drawing.Image> 개체나 <xref:System.Drawing.Bitmap> 개체에 저장되어 있는 이미지 자체의 색 값은 그대로입니다.  
  
 매핑이 변경된 이미지를 그리려면 <xref:System.Drawing.Imaging.ColorMap> 개체의 배열을 초기화합니다.  해당 배열을 <xref:System.Drawing.Imaging.ImageAttributes> 개체의 <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> 메서드에 전달한 다음, <xref:System.Drawing.Imaging.ImageAttributes> 개체를 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 전달합니다.  
  
## 예제  
 다음 예제에서는 RemapInput.bmp 파일에서 <xref:System.Drawing.Image> 개체를 만듭니다.  이 코드에서는 단일 <xref:System.Drawing.Imaging.ColorMap> 개체로 구성되는 색 매핑 변경 테이블을 만듭니다.  `ColorRemap` 개체의 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 속성은 빨강이고 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성은 파랑입니다.  이 코드에서는 매핑을 변경하기 전에 한 번, 매핑을 변경한 후 한 번 이미지를 그립니다.  매핑 변경에서는 빨강 픽셀을 모두 파랑으로 바꿉니다.  
  
 아래 그림에서 왼쪽은 원래 이미지이고 오른쪽은 매핑이 변경된 이미지입니다.  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)   
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)