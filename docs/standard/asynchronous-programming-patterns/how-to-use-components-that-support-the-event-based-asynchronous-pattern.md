---
title: "방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 사용
여러 구성 요소를 비동기적으로 작업을 수행할 수 제공 합니다. <xref:System.Media.SoundPlayer> 및 <xref:System.Windows.Forms.PictureBox> 구성 요소, 예를 들어 소리 로드할 수 있습니다 및 하면 주 스레드가 계속 중단 없이 실행 되는 동안 백그라운드"에서" 이미지를 사용 합니다.  
  
 지 원하는 클래스에서 비동기 메서드를 사용 하 여는 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) 구성 요소의 이벤트 처리기를 연결할 처럼 간단 해질 수 *MethodName* `Completed` 이벤트 와 마찬가지로 다른 이벤트에 대 한 합니다. 호출 하는 경우는 *MethodName* `Async` 메서드, 응용 프로그램이 실행 될 때까지 중단 없이 계속 됩니다는 *MethodName* `Completed` 이벤트가 발생 합니다. 이벤트 처리기에서 검사할 수 있습니다는 <xref:System.ComponentModel.AsyncCompletedEventArgs> 매개 변수를 비동기 작업이 성공적으로 완료 또는 취소 되었는지 확인 합니다.  
  
 이벤트 처리기를 사용 하는 방법에 대 한 자세한 내용은 참조 [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)합니다.  
  
 다음 절차에서는 비동기 이미지 로드 기능을 사용 하는 <xref:System.Windows.Forms.PictureBox> 제어 합니다.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>이미지를 비동기적으로 로드 하려면 PictureBox 컨트롤을 사용 하도록 설정 하려면  
  
1.  인스턴스를 만들고는 <xref:System.Windows.Forms.PictureBox> 양식에 구성 요소입니다.  
  
2.  이벤트 처리기를 할당 된 <xref:System.Windows.Forms.PictureBox.LoadCompleted> 이벤트입니다.  
  
     여기에서 비동기 다운로드 하는 동안 발생 했을 수 있는 오류를 확인 하십시오. 또한 취소를 확인 하는 위치입니다.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  호출 하는 두 개의 단추 추가 `loadButton` 및 `cancelLoadButton`, 폼에 있습니다. 추가 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 시작 하 고 다운로드를 취소 합니다.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  응용 프로그램을 실행합니다.  
  
     이미지 다운로드 진행 됨에 따라 폼을 자유롭게 이동할 수, 최소화 및 최대화 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 백그라운드에서 작업 실행](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [빌드에 없음: Visual Basic의 다중 스레딩](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
