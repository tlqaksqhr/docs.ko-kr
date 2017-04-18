---
title: "GDI+의 메타파일 | Microsoft Docs"
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
  - "GDI+, 메타파일"
  - "이미지[Windows Forms], 메타파일"
  - "메타파일"
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# GDI+의 메타파일
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 메타파일을 기록하고 표시할 수 있도록 <xref:System.Drawing.Imaging.Metafile> 클래스를 제공합니다.  벡터 이미지라고도 불리는 메타파일은 그리기 명령 및 설정 시퀀스로서 저장되는 이미지입니다.  <xref:System.Drawing.Imaging.Metafile> 개체에 기록되는 명령과 설정은 메모리나 파일 또는 스트림에 저장될 수 있습니다.  
  
## 메타파일 형식  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 다음 형식으로 저장된 메타파일을 표시할 수 있습니다.  
  
-   Windows 메타파일\(WMF\)  
  
-   확장 메타파일\(EMF\)  
  
-   EMF\+  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 메타파일을 EMF 및 EMF\+ 형식으로 기록할 수 있지만 WMF 형식으로는 기록할 수 없습니다.  
  
 EMF\+는 EMF를 확장한 것으로 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드를 저장할 수 있습니다.  EMF\+ 형식에는 EMF\+ 전용과 EMF\+ 복합이라는 두 가지 변형이 있습니다.  EMF\+ 전용 메타파일에는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드만 포함됩니다.  이러한 메타파일은 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 표시할 수 있지만 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]에서 표시할 수 없습니다.  EMF\+ 복합 메타파일에는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드가 포함됩니다.  EMF\+ 복합 메타파일에 포함된 각 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드는 대체 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드와 쌍을 이룹니다.  이러한 메타파일은 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 또는 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]에서 표시할 수 있습니다.  
  
 다음 예제에서는 파일로 저장되었던 메타파일을 표시합니다.  이 메타파일은 \(100, 100\)에 왼쪽 위 모퉁이를 갖습니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)