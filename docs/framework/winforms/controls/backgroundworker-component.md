---
title: "BackgroundWorker 구성 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbcbc786c19ad1af74114915b0fd0689d466fcbe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="backgroundworker-component"></a>BackgroundWorker 구성 요소
`BackgroundWorker` 폼 이나 컨트롤을 작업을 비동기적으로 실행할 수 있도록 하는 구성 요소입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [BackgroundWorker 구성 요소 개요](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 설명의 `BackgroundWorker` 구성 요소를 응용 프로그램의 주 UI 스레드와에서 다른 스레드에서 시간이 많이 걸리는 작업을 비동기적으로 ("백그라운드에서")를 실행 하는 기능을 제공 합니다.  
  
 [연습: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 사용 하는 방법을 보여 줍니다.는 `BackgroundWorker` 별도 스레드에서 시간이 많이 걸리는 작업을 실행 하려면 디자이너에서 구성 요소입니다.  
  
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 사용 하는 방법을 보여 줍니다.는 `BackgroundWorker` 구성 요소가 별도 스레드에서 시간이 많이 걸리는 작업을 실행 합니다.  
  
 [연습: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 수치 계산을 비동기적으로 수행 하는 디자이너를 사용 하 여 응용 프로그램을 만듭니다.  
  
 [방법: 배경 작업을 사용하는 양식 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 수치 계산을 비동기적으로 수행 하는 응용 프로그램을 만듭니다.  
  
 [방법: 백그라운드에서 파일 다운로드](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 사용 하는 방법을 보여 줍니다.는 `BackgroundWorker` 구성 요소는 별도 스레드에서 파일을 다운로드 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ComponentModel.BackgroundWorker>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 에 대 한 데이터를 보유 하는 형식을 설명는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트입니다.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 에 대 한 데이터를 보유 하는 형식을 설명는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [이벤트 기반 비동기 패턴 개요](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 어떻게 비동기 패턴을 통해 사용할 수 있는 다중 스레드 응용 프로그램의 장점을 여러 가지 다중 스레드 디자인에 내재 된 복잡 한 문제를 숨기면 서 설명 합니다.
