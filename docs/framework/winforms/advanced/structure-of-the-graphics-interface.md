---
title: "그래픽 인터페이스의 구조 | Microsoft Docs"
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
  - "GDI+, 관리되는 인터페이스 사용"
  - "그래픽, 클래스 구조"
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 그래픽 인터페이스의 구조
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]의 관리되는 클래스 인터페이스에는 약 60개의 클래스, 50개의 열거형과 8개의 구조체가 포함되어 있습니다.  <xref:System.Drawing.Graphics> 클래스는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 기능의 핵심이며 선, 곡선, 그림, 이미지 및 텍스트를 실제로 그리는 클래스입니다.  
  
## 중요 클래스  
 <xref:System.Drawing.Graphics> 클래스와 함께 동작하는 클래스에는 여러 가지가 있습니다.  예를 들어, <xref:System.Drawing.Graphics.DrawLine%2A> 메서드는 <xref:System.Drawing.Pen> 개체를 받습니다. 이 개체에는 그려야 하는 선의 특성\(색, 너비, 대시 스타일 등\)이 들어 있습니다.  <xref:System.Drawing.Graphics.FillRectangle%2A> 메서드는 <xref:System.Drawing.Graphics> 개체와 함께 동작하여 사각형에 그라데이션 효과를 적용하는 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 개체에 대한 포인터를 받습니다.  <xref:System.Drawing.Font> 및 <xref:System.Drawing.StringFormat> 개체는 <xref:System.Drawing.Graphics> 개체가 텍스트를 그리는 방식에 영향을 줍니다.  <xref:System.Drawing.Drawing2D.Matrix> 개체는 <xref:System.Drawing.Graphics> 개체의 전역 변환을 저장하고 조작하는데, 이것은 이미지의 회전, 배율 조정 및 대칭 이동에 사용됩니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 제공하는 <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point> 및 <xref:System.Drawing.Size> 같은 여러 가지 구조체를 사용하여 그래픽 데이터를 구성할 수 있습니다.  또한, 특정 클래스는 주로 구조적 데이터 형식으로 사용됩니다.  예를 들어 <xref:System.Drawing.Imaging.BitmapData> 클래스는 <xref:System.Drawing.Bitmap> 클래스의 도우미이며 <xref:System.Drawing.Drawing2D.PathData> 클래스는 <xref:System.Drawing.Drawing2D.GraphicsPath> 클래스의 도우미입니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 관련 있는 상수의 컬렉션인 여러 열거형을 정의합니다.  예를 들어, <xref:System.Drawing.Drawing2D.LineJoin> 열거형에는 두 개의 선을 연결할 때 스타일을 지정하는 <xref:System.Drawing.Drawing2D.LineJoin>, <xref:System.Drawing.Drawing2D.LineJoin> 및 <xref:System.Drawing.Drawing2D.LineJoin> 요소가 포함됩니다.  
  
## 참고 항목  
 [그래픽 개요](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [GDI\+ 관리 코드 정보](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [관리되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)