---
title: "방법: 응용 프로그램 제스처 인식 | Microsoft Docs"
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
  - "응용 프로그램 제스처, 인식"
  - "제스처, 인식"
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 응용 프로그램 제스처 인식
다음 예제에서는 사용자가 <xref:System.Windows.Controls.InkCanvas>에 <xref:System.Windows.Ink.ApplicationGesture> 제스처를 만들 때 잉크를 지우는 방법을 보여 줍니다.  이 예제에서는 `inkCanvas1`이라는 <xref:System.Windows.Controls.InkCanvas>가 XAML 파일에 선언되어 있는 것으로 가정합니다.  
  
## 예제  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Ink.ApplicationGesture>   
 <xref:System.Windows.Controls.InkCanvas>   
 <xref:System.Windows.Controls.InkCanvas.Gesture>