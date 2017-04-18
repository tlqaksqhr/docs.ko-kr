---
title: "방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHInvalidOperation.WinForms.IllegalCrossThreadCall"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "스레드 보안, 호출 컨트롤 [Windows Forms]"
  - "호출 컨트롤, 스레드 보안 [Windows Forms]"
  - "CheckForIllegalCrossThreadCalls 속성[Windows Forms]"
  - "Windows Forms 컨트롤, 다중 스레딩"
  - "BackgroundWorker 클래스, 예제"
  - "스레딩 [Windows Forms], 크로스 스레드 호출"
  - "컨트롤 [Windows Forms], 다중 스레딩"
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출
Windows Forms 응용 프로그램의 성능을 개선하기 위해 다중 스레딩을 사용하는 경우에는 스레드로부터 안전한 방식으로 컨트롤을 호출할 수 있습니다.  
  
 Windows Forms 컨트롤에 대한 액세스는 기본적으로 스레드로부터 안전하지 않습니다. 둘 이상의 스레드가 컨트롤 상태를 조작하는 경우 컨트롤이 불일치하는 상태로 강제 지정될 수 있습니다. 또한 경합 상태와 교착 상태 등의 기타 스레드 관련 버그도 발생할 수 있습니다. 컨트롤에 액세스할 때는 스레드로부터 안전한 방식을 사용해야 합니다.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A> 메서드를 사용하지 않고 컨트롤을 만든 스레드가 아닌 다른 스레드에서 컨트롤을 호출하는 것은 안전하지 않습니다. 아래에는 스레드로부터 안전하지 않은 호출의 예제가 나와 있습니다.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#6)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#6)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#6)]  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 스레드로부터 안전하지 않은 방식으로 컨트롤에 액세스하는 경우를 검색할 수 있습니다. 디버거에서 응용 프로그램을 실행할 때 컨트롤을 만든 스레드가 아닌 다른 스레드가 해당 컨트롤을 호출하려고 하면 디버거에서 <xref:System.InvalidOperationException>이 발생하고 "*컨트롤 이름* 컨트롤이 자신이 만들어진 스레드가 아닌 스레드에서 액세스되었습니다." 메시지가 표시됩니다.  
  
 이 예외는 안전하지 않은 액세스를 안정적으로 확인할 수 있도록 디버깅 중에 발생하며 가끔 런타임에 발생하는 경우도 있습니다.[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이전 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 버전을 사용하여 작성한 응용 프로그램을 디버그할 때 이 예외가 표시될 수 있습니다. 이 문제는 표시되는 경우 해결하는 것이 좋지만 <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> 속성을 `false`로 설정하면 비활성화할 수 있습니다. 이렇게 하면 컨트롤이 Visual Studio.NET 2003 및 [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)]에서 실행되는 것처럼 실행됩니다.  
  
> [!NOTE]
>  폼에서 ActiveX 컨트롤을 사용하는 경우 디버거에서 실행 시 크로스 스레드 <xref:System.InvalidOperationException>이 발생할 수 있습니다. 이 예외가 발생하면 ActiveX 컨트롤이 다중 스레딩을 지원하지 않습니다. Windows Forms에서 ActiveX 컨트롤을 사용하는 방법에 대한 자세한 내용은 [Windows Forms 및 관리되지 않는 응용 프로그램](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)를 참조하세요. Visual Studio를 사용하는 경우 Visual Studio 호스팅 프로세스를 사용하지 않도록 설정하여 이 예외를 방지할 수 있습니다\([방법: 호스팅 프로세스 비활성화](../Topic/How%20to:%20Disable%20the%20Hosting%20Process.md) 참조\).  
  
## 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출  
  
#### 스레드로부터 안전한 방식으로 Windows Forms 컨트롤을 호출하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.Control.InvokeRequired%2A> 속성을 쿼리합니다.  
  
2.  <xref:System.Windows.Forms.Control.InvokeRequired%2A>가 `true`를 반환하면 실제 컨트롤 호출을 수행하는 대리자를 포함하여 <xref:System.Windows.Forms.Control.Invoke%2A>를 호출합니다.  
  
3.  <xref:System.Windows.Forms.Control.InvokeRequired%2A>가 `false`를 반환하면 컨트롤을 직접 호출합니다.  
  
 다음 코드 예제에서는 백그라운드 스레드를 통해 실행되는 `ThreadProcSafe` 메서드에서 스레드로부터 안전한 호출이 구현됩니다.<xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.InvokeRequired%2A>가 `true`를 반환하면 `ThreadProcSafe` 메서드는 `SetTextCallback` 인스턴스를 만들어 폼의 <xref:System.Windows.Forms.Control.Invoke%2A> 메서드로 전달합니다. 이 경우 `SetText` 컨트롤을 만든 스레드에서 <xref:System.Windows.Forms.TextBox> 메서드가 호출되며 이 스레드 컨텍스트에서 <xref:System.Windows.Forms.Control.Text%2A> 속성이 직접 설정됩니다.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#7)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#7)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#3)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#8)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#8)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#8)]  
  
## BackgroundWorker를 사용하여 스레드로부터 안전한 호출 수행  
 응용 프로그램에서 다중 스레딩을 구현하는 기본 방법은 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하는 것입니다.<xref:System.ComponentModel.BackgroundWorker> 구성 요소는 다중 스레딩에 이벤트 구동 모델을 사용합니다. 백그라운드 스레드는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 실행하며 컨트롤을 만드는 스레드는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 실행합니다.<xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 컨트롤을 호출할 수 있습니다.  
  
#### BackgroundWorker를 사용하여 스레드로부터 안전한 호출을 수행하려면  
  
1.  백그라운드 스레드에서 수행하려는 작업을 수행하는 메서드를 만듭니다. 이 메서드에서 Main 메서드가 만든 컨트롤을 호출하지 마세요.  
  
2.  백그라운드 작업이 완료된 후 해당 작업의 결과를 보고하는 메서드를 만듭니다. 이 메서드에서는 Main 메서드가 만든 컨트롤을 호출할 수 있습니다.  
  
3.  1단계에서 만든 메서드를 <xref:System.ComponentModel.BackgroundWorker.DoWork> 인스턴스의 <xref:System.ComponentModel.BackgroundWorker> 이벤트에 바인딩하고 2단계에서 만든 메서드를 같은 인스턴스의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트에 바인딩합니다.  
  
4.  백그라운드 스레드를 시작하려면 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 인스턴스의 <xref:System.ComponentModel.BackgroundWorker> 메서드를 호출합니다.  
  
 다음 코드 예제에서 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기는 <xref:System.Threading.Thread.Sleep%2A>를 사용하여 시간이 오래 걸리는 작업을 시뮬레이트합니다. 그러나 폼의 <xref:System.Windows.Forms.TextBox> 컨트롤은 호출하지 않습니다.<xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성은 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에서 직접 설정됩니다.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#5)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#5)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#5)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#9)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#9)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#9)]  
  
 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 사용하여 백그라운드 작업의 진행률을 보고할 수도 있습니다. 해당 이벤트가 통합되어 있는 예제를 보려면 <xref:System.ComponentModel.BackgroundWorker>를 참조하세요.  
  
## 예제  
 다음 코드 예제는 단추 세 개와 텍스트 상자 하나가 포함된 폼으로 구성되는 완전한 Windows Forms 응용 프로그램입니다. 첫 번째 단추는 안전하지 않은 크로스 스레드 액세스를, 두 번째 단추는 <xref:System.Windows.Forms.Control.Invoke%2A>를 사용하는 안전한 액세스를, 세 번째 단추는 <xref:System.ComponentModel.BackgroundWorker>를 사용하는 안전한 액세스를 보여 줍니다.  
  
> [!NOTE]
>  예제를 실행하는 방법에 대한 지침은 [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/ko-kr/cc447f7e-4c3b-4397-9d05-aeba3ca49416)를 참조하세요. 이 예제를 실행하려면 System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조가 필요합니다.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#1)]  
  
 응용 프로그램을 실행하고 **Unsafe Call** 단추를 클릭하는 즉시 텍스트 상자에 "Written by the main thread"가 표시됩니다. 그리고 2초 후에 안전하지 않은 호출을 시도하면 Visual Studio 디버거에 예외가 발생했음이 표시됩니다. 그러면 디버거가 텍스트 상자에 직접 쓰기를 시도한 백그라운드 스레드의 줄에서 중지됩니다. 나머지 두 단추를 테스트하려면 응용 프로그램을 다시 시작해야 합니다.**Safe Call** 단추를 클릭하면 텍스트 상자에 "Written by the main thread"가 표시되고, 2초 후에 텍스트 상자는 <xref:System.Windows.Forms.Control.Invoke%2A> 메서드가 호출되었음을 나타내는 "Written by the background thread \(Invoke\)"로 설정됩니다.**Safe BW Call** 단추를 클릭하면 텍스트 상자에 "Written by the main thread"가 표시되고, 2초 후에 텍스트 상자는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>의 <xref:System.ComponentModel.BackgroundWorker> 이벤트에 대한 처리기가 호출되었음을 나타내는 "Written by the main thread after the background thread completed"가 표시됩니다.  
  
## 강력한 프로그래밍  
  
> [!CAUTION]
>  모든 종류의 다중 스레딩을 사용할 때는 코드에서 매우 심각하고 복잡한 버그가 발생할 수 있습니다. 따라서 다중 스레딩을 사용하는 솔루션을 구현하기 전에 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)에서 자세한 내용을 참조하세요.  
  
## 참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>   
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Windows Forms 및 관리되지 않는 응용 프로그램](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)