---
title: "BackgroundWorker 구성 요소 | Microsoft Docs"
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
  - "비동기 패턴"
  - "백그라운드 작업"
  - "백그라운드 작업"
  - "BackgroundWorker 구성 요소"
  - "구성 요소[Windows Forms], 비동기"
  - "폼, 백그라운드 작업"
  - "폼, 다중 스레딩"
  - "스레딩[Windows Forms], 백그라운드 작업"
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# BackgroundWorker 구성 요소
`BackgroundWorker` 구성 요소를 통해 폼이나 컨트롤에서 비동기적으로 작업을 실행할 수 있습니다.  
  
## 단원 내용  
 [BackgroundWorker 구성 요소 개요](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 시간이 많이 걸리는 작업을 응용 프로그램의 주 UI 스레드가 아닌 다른 스레드에서 비동기적으로\("백그라운드에서"\) 실행하는 데 사용되는 `BackgroundWorker` 구성 요소에 대해 설명합니다.  
  
 [연습: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 디자이너에서 `BackgroundWorker` 구성 요소를 사용하여 시간이 많이 걸리는 작업을 별개의 스레드에서 실행하는 방법을 보여 줍니다.  
  
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 `BackgroundWorker` 구성 요소를 사용하여 시간이 많이 걸리는 작업을 별개의 스레드에서 실행하는 방법을 보여 줍니다.  
  
 [연습: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 디자이너를 사용하여 수치 계산을 비동기적으로 수행하는 응용 프로그램을 만듭니다.  
  
 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 수치 계산을 비동기적으로 수행하는 응용 프로그램을 만듭니다.  
  
 [방법: 백그라운드에서 파일 다운로드](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 `BackgroundWorker` 구성 요소를 사용하여 별개의 스레드에서 파일을 다운로드하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.ComponentModel.BackgroundWorker>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크가 포함되어 있습니다.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트에 대한 데이터가 저장되는 형식에 대해 설명합니다.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 대한 데이터가 저장되는 형식에 대해 설명합니다.  
  
## 관련 단원  
 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 비동기 패턴을 통해 다중 스레드 디자인과 관련된 수많은 복잡한 문제에 신경 쓰지 않고 다중 스레드 응용 프로그램의 장점을 활용할 수 있는 방법에 대해 설명합니다.