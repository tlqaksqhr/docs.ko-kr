---
title: "How to: Use Components That Support the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use Components That Support the Event-based Asynchronous Pattern
많은 구성 요소들은 작업을 비동기식으로 수행하는 옵션을 제공합니다.  예를 들어, <xref:System.Media.SoundPlayer> 및 <xref:System.Windows.Forms.PictureBox> 구성 요소를 사용하면 주 스레드가 중단 없이 계속 실행되는 동안 소리 및 이미지를 "백그라운드로" 로드할 수 있습니다.  
  
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) 를 지원하는 클래스에 비동기 메서드를 사용하는 작업은 다른 이벤트의 경우에서와 같이 구성 요소의 *MethodName*`Completed` 이벤트에 이벤트 처리기를 연결하는 것처럼 간단히 수행할 수 있습니다.  *MethodName*`Async` 메서드를 호출할 떄 응용 프로그램은 *MethodName*`Completed` 이벤트가 발생될 때까지 중단 없이 계속 실행됩니다.  이벤트 처리기에서 <xref:System.ComponentModel.AsyncCompletedEventArgs> 매개 변수를 검토하여 비동기 작업이 완료되었는지 아니면 취소되었는지 확인할 수 있습니다.  
  
 이벤트 처리기를 사용하는 방법에 대한 자세한 내용은 [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)를 참조하십시오.  
  
 다음 절차에서는 <xref:System.Windows.Forms.PictureBox> 컨트롤의 비동기 이미지 로드 기능을 사용하는 방법을 보여 줍니다.  
  
### PictureBox 컨트롤을 사용하여 이미지를 비동기식으로 로드하려면  
  
1.  폼에 <xref:System.Windows.Forms.PictureBox> 구성 요소의 인스턴스를 만듭니다.  
  
2.  <xref:System.Windows.Forms.PictureBox.LoadCompleted> 이벤트에 이벤트 처리기를 할당합니다.  
  
     여기에서 비동기 다운로드 중에 발생했을 수 있는 오류를 확인합니다.  작업의 취소 여부도 확인할 수 있습니다.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  폼에 `loadButton` 및 `cancelLoadButton`의 두 단추를 추가합니다.  <xref:System.Windows.Forms.Control.Click> 이벤트를 추가하여 다운로드를 시작 및 취소합니다.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  응용 프로그램을 실행합니다.  
  
     이미지 다운로드가 진행될 때 폼을 자유롭게 이동하고 최소화하고 최대화할 수 있습니다.  
  
## 참고 항목  
 [방법: 백그라운드에서 작업 실행](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ko-kr/c731a50c-09c1-4468-9646-54c86b75d269)