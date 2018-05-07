---
title: '연습: 백그라운드에서 작업 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: 59447bb589eb019f81beb1db2ea254a9fe3a889e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>연습: 백그라운드에서 작업 실행
완료하는 데 오랜 시간이 걸리는 작업이 있으며 사용자 인터페이스에서 지연이 발생되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행할 수 있습니다.  
  
 이 예에서 사용 된 코드의 전체 목록을 보려면 [하는 방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-run-an-operation-in-the-background"></a>백그라운드에서 작업을 실행 하려면  
  
1.  끌어 Windows Forms 디자이너에서 활성 사용자 양식을 사용 하 여 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 양식과 설정에는 `Name` 및 <xref:System.Windows.Forms.Control.Text%2A> 다음 표에 따라 단추의 속성입니다.  
  
    |단추|이름|텍스트|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**Start**|  
    |`button2`|`cancelBtn`|**취소**|  
  
2.  열기는 **도구 상자**, 클릭는 **구성 요소** 탭 한 다음 끌어는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 폼입니다.  
  
     `backgroundWorker1` 구성 요소에 표시 된 **구성 요소 트레이**합니다.  
  
3.  에 **속성** 창에서 설정 된 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다.  
  
4.  에 **속성** 창을 **이벤트** 단추를 클릭 한 다음 두 번 클릭는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 만드는 이벤트입니다.  
  
5.  시간이 많이 걸리는 코드에 삽입 된 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기입니다.  
  
6.  작업에 필요한 모든 매개 변수를 추출는 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 의 속성은 <xref:System.ComponentModel.DoWorkEventArgs> 매개 변수입니다.  
  
7.  할당에 대 한 계산의 결과 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 속성은 <xref:System.ComponentModel.DoWorkEventArgs>합니다.  
  
     됩니다에 사용할 수는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  작업의 결과 검색 하기 위한 코드를 삽입 하는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. `TimeConsumingOperation` 메서드를 구현합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. Windows Forms 디자이너에서 두 번 클릭 `startButton` 만들려는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.  
  
11. 호출 된 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 에서 메서드는 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기 `startButton`합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. Windows Forms 디자이너에서 두 번 클릭 `cancelButton` 만들려는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.  
  
13. 호출 된 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 에서 메서드는 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기 `cancelButton`합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. 파일 맨 위에 있는 System.ComponentModel 및 System.Threading 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. F6 키를 눌러 솔루션을 작성 하 고 디버거 외부에서 응용 프로그램을 실행 하려면 CTRL + f 5를 누릅니다.  
  
> [!NOTE]
>  F5 키를 눌러 디버거에서 응용 프로그램을 실행 하는 예외에서 발생 된 `TimeConsumingOperation` 메서드를 포착 하 디버거에 표시 합니다. 디버거, 외부 응용 프로그램을 실행 하면는 <xref:System.ComponentModel.BackgroundWorker> 예외를 처리 하 고 캐시에 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> 의 속성은 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>합니다.  
  
1.  클릭는 **시작** 비동기 작업을 실행 하려면 단추를 선택한 다음 클릭는 **취소** 단추를 실행 중인 비동기 작업을 중지 합니다.  
  
     각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.  
  
## <a name="next-steps"></a>다음 단계  
  
-   비동기 작업 진행 상태를 보고 하는 폼을 구현 합니다. 자세한 내용은 참조 [하는 방법: 백그라운드 작업을 사용 하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)합니다.  
  
-   구성 요소에 대 한 비동기 패턴을 지 원하는 클래스를 구현 합니다. 자세한 내용은 참조 [이벤트 기반 비동기 패턴 구현](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [방법: 배경 작업을 사용하는 양식 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
