---
title: "연습: 백그라운드에서 작업 실행 | Microsoft Docs"
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
  - "백그라운드 작업"
  - "백그라운드 작업"
  - "백그라운드 스레드"
  - "BackgroundWorker 클래스, 예제"
  - "폼, 백그라운드 작업"
  - "폼, 다중 스레딩"
  - "스레딩[Windows Forms], 백그라운드 작업"
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 연습: 백그라운드에서 작업 실행
완료하는 데 시간이 많이 걸리는 작업이 있는데 사용자 인터페이스에서 지연이 발생하지 않게 하려면 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행합니다.  
  
 이 예제에 사용된 코드에 대한 전체 목록을 보려면 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 백그라운드에서 작업을 실행하려면  
  
1.  Windows Forms 디자이너에서 폼을 활성화한 후 **도구 상자**에 있는 두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 놓은 다음 단추의 `Name` 및 <xref:System.Windows.Forms.Control.Text%2A> 속성을 다음 표에 따라 설정합니다.  
  
    |Button|Name|Text|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|Start|  
    |`button2`|`cancelBtn`|Cancel|  
  
2.  **도구 상자**를 열고 **구성 요소** 탭을 클릭한 다음 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 끌어서 폼에 놓습니다.  
  
     **구성 요소 트레이**에 `backgroundWorker1` 구성 요소가 나타납니다.  
  
3.  **속성** 창에서 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`로 설정합니다.  
  
4.  **속성** 창에서 **이벤트** 단추를 클릭한 다음 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 두 번 클릭하여 이벤트 처리기를 만듭니다.  
  
5.  시간이 많이 걸리는 코드를 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에 삽입합니다.  
  
6.  <xref:System.ComponentModel.DoWorkEventArgs> 매개 변수의 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 속성에서 작업에 필요한 모든 매개 변수를 추출합니다.  
  
7.  계산 결과를 <xref:System.ComponentModel.DoWorkEventArgs>의 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 속성에 할당합니다.  
  
     이 결과는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 사용할 수 있습니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  작업 결과를 검색하는 코드를 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에 삽입합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. `TimeConsumingOperation` 메서드를 구현합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. Windows Forms 디자이너에서 `startButton`을 두 번 클릭하여 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만듭니다.  
  
11. `startButton`의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드를 호출합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. Windows Forms 디자이너에서 `cancelButton`을 두 번 클릭하여 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만듭니다.  
  
13. <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 `cancelButton`에 대해 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드를 호출합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. 파일 맨 위에서 System.ComponentModel 및 System.Threading 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. F6 키를 눌러 솔루션을 빌드한 다음 Ctrl\+F5를 눌러 디버거 외부에서 응용 프로그램을 실행합니다.  
  
> [!NOTE]
>  F5 키를 눌러 디버거에서 응용 프로그램을 실행할 경우 `TimeConsumingOperation` 메서드에서 발생한 예외가 디버거에 의해 catch되어 표시됩니다.  응용 프로그램을 디버거 외부에서 실행하면 <xref:System.ComponentModel.BackgroundWorker>가 예외를 처리하고 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>의 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> 속성에 예외를 캐시합니다.  
  
1.  **시작** 단추를 클릭하여 비동기 작업을 실행한 다음 **취소** 단추를 클릭하여 실행 중인 비동기 작업을 중지합니다.  
  
     각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.  
  
## 다음 단계  
  
-   비동기 작업의 진행 상태를 보고하는 폼을 구현합니다.  자세한 내용은 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)을 참조하십시오.  
  
-   구성 요소의 비동기 패턴을 지원하는 클래스를 구현합니다.  자세한 내용은 [Implementing the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)