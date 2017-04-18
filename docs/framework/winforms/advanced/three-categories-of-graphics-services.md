---
title: "세 가지 범주의 그래픽 서비스 | Microsoft Docs"
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
  - "2차원 벡터 그래픽"
  - "그래픽, 범주"
  - "이미징"
  - "입력 체계"
  - "벡터 그래픽"
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 세 가지 범주의 그래픽 서비스
Windows Forms의 그래픽 서비스는 다음 세 가지 큰 범주 중 하나에 속합니다.  
  
-   2\-D\(2차원\) 벡터 그래픽  
  
-   이미징  
  
-   입력 체계  
  
## 2\-D 벡터 그래픽  
 2차원 벡터 그래픽은 좌표계의 점 집합에 의해 지정된 선, 곡선 및 그림과 같은 기본 형식입니다.  예를 들어, 직선은 두 끝점으로 지정하고 사각형은 왼쪽 위 모퉁이의 위치를 나타내는 점과 너비 및 높이 값으로 지정합니다.  직선으로 연결되는 점 배열로 간단한 경로를 지정할 수 있습니다.  Bézier 스플라인은 네 개의 제어 점으로 지정되는 정교한 곡선입니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 기본 형식 자체에 대한 정보를 저장하는 클래스 및 구조체와 기본 형식을 그리는 방법에 대한 정보를 저장하는 클래스, 실제로 그리기를 수행하는 클래스 등을 제공합니다.  예를 들어, <xref:System.Drawing.Rectangle> 구조체는 사각형의 위치와 크기를 저장하고, <xref:System.Drawing.Pen> 클래스는 선 색, 선 너비 및 선 스타일에 대한 정보를 저장하며, <xref:System.Drawing.Graphics> 클래스에는 선, 사각형, 경로 및 다른 그림을 그리기 위한 메서드가 있습니다.  또한 닫혀 있는 그림과 경로를 색이나 패턴으로 채우는 방법에 대한 정보를 저장하는 <xref:System.Drawing.Brush> 클래스가 여러 개 있습니다.  
  
 그래픽 명령 시퀀스인 벡터 이미지를 메타파일에 기록할 수 있습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 메타파일의 기록, 표시 및 저장을 위한 <xref:System.Drawing.Imaging.Metafile> 클래스를 제공합니다.  <xref:System.Drawing.Imaging.MetafileHeader> 및 <xref:System.Drawing.Imaging.MetaHeader> 클래스를 사용하여 메타파일 헤더에 저장된 데이터를 검사할 수 있습니다.  
  
## 이미징  
 특정 종류의 그림은 벡터 그래픽 기술로 표시하기 어렵거나 불가능합니다.  예를 들어, 도구 모음 단추의 그림과 아이콘으로 표시되는 그림은 선과 곡선의 컬렉션으로 지정하기 어렵습니다.  붐비는 야구 경기장의 고해상도 디지털 사진은 벡터 기술로 생성하기가 더욱 어려울 것입니다.  이러한 형식의 이미지는 화면에 있는 각 점의 색을 나타내는 숫자 배열인 비트맵으로 저장됩니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 비트맵의 표시, 조작 및 저장을 위한 <xref:System.Drawing.Bitmap> 클래스를 제공합니다.  
  
## 입력 체계  
 입력 체계는 다양한 글꼴, 크기 및 스타일로 텍스트를 표시하는 것입니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 이러한 복잡한 작업을 위하여 광범위한 지원 기능을 제공합니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]의 새로운 기능 중 하나는 LCD 화면에 렌더링된 텍스트가 부드럽게 보이도록 하는 하위 픽셀의 앤티 앨리어싱입니다.  
  
 또한 Windows Forms에는 <xref:System.Windows.Forms.TextRenderer> 클래스에서 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 기능을 사용하여 텍스트를 그리는 옵션이 있습니다.  
  
## 참고 항목  
 [그래픽 개요](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [GDI\+ 관리 코드 정보](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [관리되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)