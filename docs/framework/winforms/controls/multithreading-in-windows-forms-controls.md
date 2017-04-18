---
title: "Windows Forms 컨트롤의 다중 스레딩 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BackgroundWorker 구성 요소"
  - "BeginInvoke 메서드"
  - "스레딩[Windows Forms], 컨트롤"
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Windows Forms 컨트롤의 다중 스레딩
응용 프로그램에서 시간이 많이 걸리는 작업을 다른 스레드에서 수행하여 UI\(사용자 인터페이스\)의 응답 기능을 향상시킬 수 있는 경우가 많습니다.  <xref:System.Threading> 네임스페이스, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName> 메서드 및 `BackgroundWorker` 구성 요소를 비롯한 수많은 도구를 사용하여 Windows Forms 컨트롤을 다중 스레딩할 수 있습니다.  
  
> [!NOTE]
>  `BackgroundWorker`는 <xref:System.Threading> 네임스페이스와 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName> 메서드를 대체하고 여기에 다른 기능을 추가하여 새로 도입된 구성 요소이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 이러한 네임스페이스와 메서드를 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [BackgroundWorker 구성 요소 개요](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)를 참조하십시오.  
  
## 단원 내용  
 [방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 스레드로부터 안전한 방식으로 Windows Forms 컨트롤을 호출하는 방법을 보여 줍니다.  
  
 [방법: 백그라운드 스레드를 사용하여 파일 검색](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <xref:System.Threading> 네임스페이스와 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 메서드를 사용하여 파일을 비동기적으로 검색하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.ComponentModel.BackgroundWorker>  
 비동기 작업을 위해 작업자 스레드를 캡슐화하는 구성 요소를 설명합니다.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 소리를 비동기적으로 로드하는 방법을 설명합니다.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 이미지를 비동기적으로 로드하는 방법을 설명합니다.  
  
## 관련 단원  
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하여 시간이 많이 걸리는 작업을 수행하는 방법을 보여 줍니다.  
  
 [BackgroundWorker 구성 요소 개요](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 비동기 작업에 사용하는 방법을 설명하는 항목을 제공합니다.