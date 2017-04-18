---
title: "방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리 | Microsoft Docs"
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
  - "이미지[Windows Forms], 품질 관리"
  - "이미지[Windows Forms], 배율"
  - "보간 모드, 이미지 품질 관리"
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리
<xref:System.Drawing.Graphics> 개체의 보간 모드는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 이미지의 배율을 조정\(늘임 및 줄임\)하는 데 영향을 줍니다.  <xref:System.Drawing.Drawing2D.InterpolationMode> 열거형에서는 몇 가지의 보간 모드를 정의하며 다음 목록에 그 중 일부가 나와 있습니다.  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
 이미지를 확대하려면 원래 이미지에 있는 각 픽셀을 큰 이미지에 있는 픽셀의 그룹으로 매핑해야 합니다.  이미지를 축소하려면 원래 이미지에 있는 픽셀의 그룹을 작은 이미지에 있는 단일 픽셀로 매핑해야 합니다.  이러한 매핑을 수행하는 알고리즘이 효율적인지에 따라 배율을 조정한 이미지의 품질이 결정됩니다.  품질이 더 나은 배율 조정된 이미지를 만드는 알고리즘일수록 처리 시간은 더 오래 걸립니다.  위 목록에서 <xref:System.Drawing.Drawing2D.InterpolationMode>는 가장 품질이 낮은 모드이고 <xref:System.Drawing.Drawing2D.InterpolationMode>는 가장 품질이 우수한 모드입니다.  
  
 보간 모드를 설정하려면 <xref:System.Drawing.Drawing2D.InterpolationMode> 열거형의 멤버 중 하나를 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.InterpolationMode%2A> 속성에 지정합니다.  
  
## 예제  
 아래 예제에서는 이미지를 그린 다음 세 가지의 보간 모드를 사용하여 이미지를 축소합니다.  
  
 아래 그림에서는 원래 이미지 및 세 종류의 작은 이미지를 보여 줍니다.  
  
 ![다양한 보간 설정의 이미지](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)