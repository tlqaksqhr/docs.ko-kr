---
title: "방법: 사용자 지정 컨트롤에서 잉크 지우기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 지정 컨트롤, 잉크 지우기"
  - "잉크, 사용자 지정 컨트롤에서 지우기"
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 사용자 지정 컨트롤에서 잉크 지우기
<xref:System.Windows.Ink.IncrementalStrokeHitTester>는 현재 그려진 스트로크가 다른 스트로크와 교차하는지 확인합니다.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>가 <xref:System.Windows.Controls.InkCanvasEditingMode>로 설정되었을 때 <xref:System.Windows.Controls.InkCanvas>에서 사용자가 스트로크 일부를 지울 수 있는 컨트롤을 만들 때 유용한 클래스입니다.  
  
## 예제  
 다음 예제에서는 사용자가 스트로크의 일부를 지울 수 있는 사용자 지정 컨트롤을 만듭니다.  이 예제에서는 초기화될 때 잉크가 포함되는 컨트롤을 만듭니다.  잉크를 수집하는 컨트롤을 만들려면 [잉크 입력 컨트롤 만들기](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)를 참조하십시오.  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]