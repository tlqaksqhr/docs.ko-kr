---
title: "Windows Forms 좌표 | Microsoft Docs"
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
  - "클라이언트 좌표"
  - "좌표, Windows Forms"
  - "화면 좌표"
  - "Windows Forms 좌표"
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Windows Forms 좌표
Windows Form의 좌표계는 장치 좌표를 기반으로 하며 Windows Forms에서 그릴 때 기본 측정 단위는 장치 단위\(일반적으로 픽셀\)입니다.  화면의 점은 오른쪽으로 이동하면 증가하는 X 좌표와 위에서 아래로 이동하면 증가하는 Y 좌표를 사용하여 X와 Y 좌표 쌍으로 표시됩니다.  화면과 관련된 원점의 위치는 화면 좌표를 지정하는지 아니면 클라이언트 좌표를 지정하는지에 따라 달라집니다.  
  
## 화면 좌표  
 Windows Forms 응용 프로그램은 화면 좌표를 사용하여 화면에서 창의 위치를 지정합니다.  화면 좌표의 경우 원점은 화면의 왼쪽 위 모퉁이에 있습니다.  창의 왼쪽 위 모퉁이와 오른쪽 아래 모퉁이를 정의하는 두 점의 화면 좌표를 포함하는 <xref:System.Drawing.Rectangle> 구조를 사용하여 창의 전체 위치를 설명하기도 합니다.  
  
## 클라이언트 좌표  
 Windows Forms 응용 프로그램은 클라이언트 좌표를 사용하여 폼 또는 컨트롤에서 점의 위치를 지정합니다.  클라이언트 좌표의 원점은 컨트롤 또는 폼의 클라이언트 영역 왼쪽 위 모퉁이입니다.  클라이언트 좌표를 사용하면 폼이나 컨트롤에서 그리는 동안 화면에서 폼이나 컨트롤의 위치에 관계없이 응용 프로그램이 항상 같은 좌표 값을 사용할 수 있습니다.  
  
 영역에 대한 클라이언트 좌표를 포함하는 <xref:System.Drawing.Rectangle> 구조를 사용하여 클라이언트 영역의 차원을 설명할 수도 있습니다.  어떠한 경우에도 사각형의 왼쪽 위 좌표는 클라이언트 영역에 포함되고 오른쪽 아래 좌표는 제외됩니다.  그래픽 작업은 클라이언트 영역의 오른쪽 아래 가장자리를 포함하지 않습니다.  예를 들어, <xref:System.Drawing.Graphics.FillRectangle%2A> 메서드는 지정한 사각형의 오른쪽 아래 가장자리를 채우지만 이러한 가장자리를 포함하지는 않습니다.  
  
## 좌표 형식을 다른 형식으로 매핑  
 경우에 따라 화면 좌표에서 클라이언트 좌표로 매핑이 필요할 수 있습니다.  <xref:System.Windows.Forms.Control> 클래스에서 사용 가능한 <xref:System.Windows.Forms.Control.PointToClient%2A> 및 <xref:System.Windows.Forms.Control.PointToScreen%2A> 메서드를 사용하면 쉽게 매핑할 수 있습니다.  예를 들어, <xref:System.Windows.Forms.Control>의 <xref:System.Windows.Forms.Control.MousePosition%2A> 속성은 화면 좌표에서 보고되지만 클라이언트 좌표로 변경할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.PointToClient%2A>   
 <xref:System.Windows.Forms.Control.PointToScreen%2A>