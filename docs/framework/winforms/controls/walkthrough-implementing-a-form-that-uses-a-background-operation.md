---
title: "연습: 백그라운드 작업을 사용하는 폼 구현 | Microsoft Docs"
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
  - "BackgroundWorker 구성 요소"
  - "폼, 백그라운드 작업"
  - "폼, 다중 스레딩"
  - "스레딩[Windows Forms], 백그라운드 작업"
  - "스레딩[Windows Forms], 폼"
  - "스레딩[Windows Forms], 연습"
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# 연습: 백그라운드 작업을 사용하는 폼 구현
완료하는 데 시간이 오래 걸리는 작업을 수행하면서 UI\(사용자 인터페이스\)가 응답을 중지하지 않게 하거나 "중단"되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 해당 작업을 실행할 수 있습니다.  
  
 이 연습에서는 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 시간이 많이 걸리는 계산을 "백그라운드에서" 수행하고 사용자 인터페이스는 응답 가능한 상태로 유지하는 방법을 보여 줍니다.  이 연습을 마치면 피보나치 수\(Fibonacci number\)를 비동기적으로 계산하는 응용 프로그램을 갖게 됩니다.  큰 피보나치 수\(Fibonacci number\)를 계산하는 데에는 시간이 많이 걸릴 수 있지만 주 UI 스레드는 이러한 지연에 의해 중단되지 않으며 계산 중에 폼이 응답합니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows 기반 응용 프로그램 만들기  
  
-   폼에 <xref:System.ComponentModel.BackgroundWorker> 만들기  
  
-   비동기 이벤트 처리기 추가  
  
-   진행률 보고 및 취소 지원 추가  
  
 이 예제에서 사용된 코드의 전체 목록은 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 백그라운드 작업을 사용하는 폼을 만들려면  
  
1.  `BackgroundWorkerExample`이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  **솔루션 탐색기**에서 **Form1**을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.  파일 이름을 `FibonacciCalculator`로 변경합니다.  코드 요소 '`Form1`'에 대한 모든 참조의 이름을 변경할 것인지 묻는 메시지가 나타나면 **예** 단추를 클릭합니다.  
  
3.  **도구 상자**의 <xref:System.Windows.Forms.NumericUpDown> 컨트롤을 폼으로 끌어 옵니다.  <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> 속성을 `1`로 설정하고 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> 속성을 `91`로 설정합니다.  
  
4.  두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 추가합니다.  
  
5.  첫 번째 <xref:System.Windows.Forms.Button> 컨트롤 이름을 `startAsyncButton`으로 변경하고 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `Start Async`로 설정합니다.  두 번째 <xref:System.Windows.Forms.Button> 컨트롤 이름을 `cancelAsyncButton`으로 변경하고 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `Cancel Async`로 설정합니다.  <xref:System.Windows.Forms.Control.Enabled%2A> 속성을 `false`로 설정합니다.  
  
6.  두 <xref:System.Windows.Forms.Button> 컨트롤 모두의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.  자세한 내용은 [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ko-kr/8461e9b8-14e8-406f-936e-3726732b23d2)를 참조하십시오.  
  
7.  **도구 상자**의 <xref:System.Windows.Forms.Label> 컨트롤을 폼으로 끌어 온 다음 이름을 `resultLabel`로 변경합니다.  
  
8.  **도구 상자**의 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 폼으로 끌어 옵니다.  
  
## 폼에 BackgroundWorker 만들기  
 **Windows** **Forms 디자이너**를 사용하여 비동기 작업에 사용할 <xref:System.ComponentModel.BackgroundWorker>를 만들 수 있습니다.  
  
#### 디자이너로 BackgroundWorker를 만들려면  
  
-   **도구 상자**에서 **구성 요소** 탭에 있는 <xref:System.ComponentModel.BackgroundWorker>를 폼으로 끌어 옵니다.  
  
## 비동기 이벤트 처리기 추가  
 이제 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 비동기 이벤트에 대한 이벤트 처리기를 추가할 수 있습니다.  백그라운드에서 실행되고 시간이 많이 걸리는 피보나치 수\(Fibonacci number\) 계산 작업은 이러한 이벤트 처리기 중 하나에서 호출됩니다.  
  
#### 비동기 이벤트 처리기를 구현하려면  
  
1.  **속성** 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 선택하고 **이벤트** 단추를 클릭합니다.  <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 두 번 클릭하여 이벤트 처리기를 만듭니다.  이벤트 처리기를 사용하는 방법에 대한 자세한 내용은 [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ko-kr/8461e9b8-14e8-406f-936e-3726732b23d2)을 참조하십시오.  
  
2.  `ComputeFibonacci`라는 새 메서드를 폼에 만듭니다.  이 메서드가 실제 작업을 수행하며 백그라운드에서 실행됩니다.  이 코드에서는 계산해야 할 수가 커질수록 시간은 기하급수적으로 늘어나는 비효율적인 피보나치\(Fibonacci\) 알고리즘을 재귀적으로 구현하여 보여 줍니다.  이 코드는 설명을 위해 제공되었으며, 응용 프로그램을 오래 지연시킬 수 있는 작업을 보여 줍니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에서 `ComputeFibonacci` 메서드 호출을 추가합니다.  <xref:System.ComponentModel.DoWorkEventArgs>의 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 속성에서 `ComputeFibonacci`에 대한 첫 번째 매개 변수를 가져옵니다.  <xref:System.ComponentModel.BackgroundWorker> 및 <xref:System.ComponentModel.DoWorkEventArgs> 매개 변수는 나중에 진행률 보고 및 취소 지원에 사용됩니다.  `ComputeFibonacci`에서 반환된 값을 <xref:System.ComponentModel.DoWorkEventArgs>의 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 속성에 할당합니다.  이 결과는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 사용할 수 있습니다.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기가 `backgroundWorker1` 인스턴스 변수를 직접 참조하지 않습니다. 이를 통해 이 이벤트 처리기는 <xref:System.ComponentModel.BackgroundWorker>의 특정 인스턴스에 결합됩니다.  대신 이 이벤트를 발생시킨 <xref:System.ComponentModel.BackgroundWorker>에 대한 참조가 `sender` 매개 변수에서 복구됩니다.  이것은 폼이 두 개 이상의 <xref:System.ComponentModel.BackgroundWorker>를 호스트하는 경우에 중요합니다.  <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에서 사용자 인터페이스 개체를 조작하지 않는 것도 중요합니다.  대신 <xref:System.ComponentModel.BackgroundWorker> 이벤트를 통해 사용자 인터페이스와 통신합니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  `startAsyncButton` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 비동기 작업을 시작하는 코드를 추가합니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 계산 결과를 `resultLabel` 컨트롤에 할당합니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## 진행률 보고 및 취소 지원 추가  
 시간이 오래 걸리는 비동기 작업의 경우 사용자에게 진행률을 보고하여 사용자가 작업을 취소할 수 있도록 하는 것이 좋습니다.  <xref:System.ComponentModel.BackgroundWorker> 클래스는 백그라운드 작업이 수행될 때 진행률을 게시할 수 있는 이벤트를 제공합니다.  또한 해당 클래스는 작업자 코드가 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>에 대한 호출을 감지하여 스스로 중지할 수 있게 하는 플래그를 제공합니다.  
  
#### 진행률 보고를 구현하려면  
  
1.  **속성** 창에서 `backgroundWorker1`을 선택합니다.  <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`로 설정합니다.  
  
2.  `FibonacciCalculator` 폼에 두 개의 변수를 선언합니다.  이러한 변수는 진행률을 추적하는 데 사용됩니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 대한 이벤트 처리기를 추가합니다.  <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기에서 <xref:System.Windows.Forms.ProgressBar>를 <xref:System.ComponentModel.ProgressChangedEventArgs> 매개 변수의 <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> 속성으로 업데이트합니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### 취소에 대한 지원을 구현하려면  
  
1.  `cancelAsyncButton` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 비동기 작업을 취소하는 코드를 추가합니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  `ComputeFibonacci` 메서드의 다음 코드 조각이 진행률을 보고하고 취소를 지원합니다.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## 검사점  
 이 시점에서 피보나치\(Fibonacci\) 계산기 응용 프로그램을 컴파일하고 실행할 수 있습니다.  
  
#### 프로젝트를 테스트하려면  
  
-   F5 키를 눌러 응용 프로그램을 컴파일하고 실행합니다.  
  
     백그라운드에서 계산이 실행되는 동안 완료될 때까지의 계산 진행률을 표시하는 <xref:System.Windows.Forms.ProgressBar>가 표시됩니다.  또한 보류 중인 작업을 취소할 수 있습니다.  
  
     숫자가 작은 경우 계산이 빠르지만 숫자가 큰 경우에 작업이 현격하게 지연되는 것을 볼 수 있습니다.  30 이상의 값을 입력하면 컴퓨터의 속도에 따라 몇 초의 시간이 지연됩니다.  40 이상의 값을 입력하면 계산을 완료하는 데 몇 분 또는 몇 시간이 걸릴 수 있습니다.  계산기로 큰 피보나치 수\(Fibonacci number\)를 계산하는 동안 폼을 자유롭게 이동, 최소화, 최대화할 수 있을 뿐만 아니라 폼을 닫을 수도 있습니다.  이는 주 UI 스레드가 계산이 완료될 때까지 기다리지 않기 때문입니다.  
  
## 다음 단계  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하여 백그라운드에서 계산을 실행하는 폼을 구현했으므로 비동기 작업에 대한 다른 예도 찾아볼 수 있습니다.  
  
-   여러 동시 작업에 여러 개의 <xref:System.ComponentModel.BackgroundWorker> 개체를 사용합니다.  
  
-   다중 스레드 응용 프로그램을 디버깅하려면 [방법: 스레드 창 사용](../Topic/How%20to:%20Use%20the%20Threads%20Window.md)을 참조하십시오.  
  
-   비동기 프로그래밍 모델을 지원하는 고유한 구성 요소를 구현합니다.  자세한 내용은 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)를 참조하십시오.  
  
    > [!CAUTION]
    >  다중 스레딩을 사용하는 경우 심각하고 복잡한 버그에 노출될 수 있습니다.  다중 스레딩을 사용하는 솔루션을 구현하기 전에 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)   
 [구성 요소에서 다중 스레딩](../Topic/Multithreading%20in%20Components.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ko-kr/c731a50c-09c1-4468-9646-54c86b75d269)   
 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [연습: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)   
 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)