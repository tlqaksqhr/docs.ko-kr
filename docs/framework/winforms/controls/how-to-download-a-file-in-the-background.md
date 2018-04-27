---
title: '방법: 백그라운드에서 파일 다운로드'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc04931fbe60a12aab692de468b16188f10b4492
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-download-a-file-in-the-background"></a>방법: 백그라운드에서 파일 다운로드
파일 다운로드는 일반 작업이며, 대체로 시간이 많이 걸릴 수 있는 이 작업을 별도 스레드에서 실행하는 데 유용합니다. 매우 적은 양의 코드로 이 작업을 수행려면 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하여 URL에서 XML 파일을 로드하는 방법을 보여 줍니다. 사용자가 클릭할 때는 **다운로드** 단추를는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 호출의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 의 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소 다운로드 작업을 시작 합니다. 다운로드 기간 중에는 단추를 사용할 수 없으며, 다운로드가 완료되면 사용할 수 있습니다. <xref:System.Windows.Forms.MessageBox>는 파일 내용을 표시합니다.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **파일 다운로드**  
  
 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 실행하는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 작업자 스레드에서 파일이 다운로드됩니다. 이 스레드는 코드에서 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드를 호출할 때 시작됩니다.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **BackgroundWorker가 완료될 때까지 대기**  
  
 `downloadButton_Click` 이벤트 처리기는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 비동기 작업을 완료할 때까지 기다리는 방법을 보여 줍니다.  
  
 응용 프로그램에서 이벤트에 응답만 하고 백그라운드 스레드가 완료될 때까지 기다리는 동안 주 스레드에서 작업을 수행하지 않으려는 경우 처리기를 종료합니다.  
  
 주 스레드에서 작업을 계속하려는 경우 <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> 속성을 사용하여 <xref:System.ComponentModel.BackgroundWorker> 스레드가 여전히 실행되고 있는지 여부를 확인합니다. 예제에서는 다운로드가 처리되는 동안 진행률 표시줄이 업데이트됩니다. <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 메서드를 호출하여 UI 응답성을 유지해야 합니다.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **결과 표시**  
  
 `backgroundWorker1_RunWorkerCompleted` 메서드는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 처리하며, 백그라운드 작업이 완료될 때 호출됩니다. 이 메서드는 먼저 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 속성을 확인합니다. <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>가 `null`이면 이 메서드는 파일 내용을 표시합니다. 다운로드를 시작할 때 사용할 수 없게 된 다운로드 단추를 사용할 수 있도록 하며 진행률 표시줄을 다시 설정합니다.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Drawing, System.Windows.Forms 및 System.Xml 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> 속성이나 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기의 영향을 받았을 수 있는 다른 개체에 액세스하기 전에 항상 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기의 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 속성을 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>  
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [방법: 배경 작업을 사용하는 양식 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
