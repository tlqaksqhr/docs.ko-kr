---
title: "방법: 인쇄 작업을 현재 인쇄할 수 있는지 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "인쇄 작업, 타이밍"
  - "인쇄 대기열, 타이밍"
  - "프린터, 가용성"
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 인쇄 작업을 현재 인쇄할 수 있는지 확인
인쇄 큐를 하루 24시간 내내 사용할 수 있는 것은 아닙니다.  인쇄 큐에는 특정 시간에 사용할 수 없도록 설정할 수 있는 시작 및 종료 시간 속성이 있습니다.  예를 들어 오후 5시 이후에는 프린터를 특정 부서가 독점적으로 사용하도록 예약하는 데 이 기능을 사용할 수 있습니다.  해당 부서에서는 다른 부서에서 사용하는 것과 다른 큐에서 프린터를 처리하게 됩니다.  다른 부서의 큐는 오후 5시 이후에는 사용할 수 없도록 설정하고 선택한 부서의 큐는 항상 사용할 수 있도록 설정할 수 있습니다.  
  
 또한 인쇄 작업 자체는 지정한 시간 범위 내에서만 인쇄 가능하도록 설정할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]의 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에 노출된 <xref:System.Printing.PrintQueue> 및 <xref:System.Printing.PrintSystemJobInfo> 클래스를 사용하면 현재 시간에 지정한 큐에서 지정한 인쇄 작업을 인쇄할 수 있는지 여부를 원격으로 확인할 수 있습니다.  
  
## 예제  
 아래의 예제는 인쇄 작업 문제를 진단할 수 있는 샘플입니다.  
  
 이러한 종류의 기능에 대한 두 가지 주요 단계는 다음과 같습니다.  
  
1.  <xref:System.Printing.PrintQueue>의 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성을 읽고 현재 시간이 이 둘 사이에 있는지 확인합니다.  
  
2.  <xref:System.Printing.PrintSystemJobInfo>의 <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> 속성을 읽고 현재 시간이 이 둘 사이에 있는지 확인합니다.  
  
 그러나 이러한 속성이 <xref:System.DateTime> 개체가 아니라는 것 때문에 문제가 발생합니다.  이러한 속성은 시간을 자정 이후의 시간\(분\)으로 표시하는 <xref:System.Int32> 개체입니다.  또한 이 자정이 현재 시간대의 자정이 아니라 UTC \(협정 세계시\) 자정입니다.  
  
 첫 번째 코드 예제에서는 정적 메서드 **ReportQueueAndJobAvailability**를 보여 줍니다. 이 메서드는 <xref:System.Printing.PrintSystemJobInfo>를 전달받고 도우미 메서드를 호출하여 현재 시간에 작업을 인쇄할 수 있는지, 그리고 인쇄할 수 없는 경우 언제 인쇄할 수 있는지를 확인합니다.  <xref:System.Printing.PrintQueue>는 이 메서드에 전달되지 않습니다.  그 이유는 <xref:System.Printing.PrintSystemJobInfo>에서 해당 <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> 속성에서 큐에 대한 참조를 포함하고 있기 때문입니다.  
  
 하위 수준 메서드에는 <xref:System.Printing.PrintQueue> 또는 <xref:System.Printing.PrintSystemJobInfo>를 매개 변수로 사용하는 오버로드된 **ReportAvailabilityAtThisTime** 메서드가 포함되어 있습니다.  또한 **TimeConverter.ConvertToLocalHumanReadableTime**도 있습니다.  이러한 메서드에 대해서는 아래에서 설명합니다.  
  
 **ReportQueueAndJobAvailability** 메서드에서는 먼저 현재 시간에 큐 또는 인쇄 작업을 사용할 수 없는지 확인합니다.  이들 중 하나라도 사용할 수 없는 경우 큐를 사용할 수 없는지 확인합니다.  사용할 수 없는 경우 메서드에서는 이 사실과 큐를 다시 사용할 수 있게 될 시간을 보고합니다.  그런 다음 작업을 확인하고 작업을 사용할 수 없는 경우 다음에 인쇄할 수 있는 시간 범위를 보고합니다.  마지막으로 이 메서드는 작업을 인쇄할 수 있는 가장 이른 시간을 보고합니다.  이 시간은 다음 두 시간 중 나중 시간입니다.  
  
-   인쇄 큐를 사용할 수 있는 다음 시간  
  
-   인쇄 작업을 사용할 수 있는 다음 시간  
  
 시간을 보고할 때는 출력에서 년, 월 및 일을 표시하지 않도록 만드는 <xref:System.DateTime.ToShortTimeString%2A> 메서드도 호출합니다.  인쇄 큐나 인쇄 작업의 가용성을 특정 년, 월 또는 일로 제한할 수는 없습니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 **ReportAvailabilityAtThisTime** 메서드의 두 오버로드는 전달받는 형식을 제외하고는 동일합니다. 따라서 아래에서는 <xref:System.Printing.PrintQueue> 버전만 표시됩니다.  
  
> [!NOTE]
>  이들 메서드가 형식을 제외하고는 동일한데 샘플에서 제네릭 메서드 **ReportAvailabilityAtThisTime\<T\>**를 만들지 않은 이유가 궁금할 것입니다.  그 이유는 이러한 메서드는 메서드에서 호출하는 **StartTimeOfDay** 및 **UntilTimeOfDay** 속성이 있는 클래스로 제한해야 하지만 제네릭 메서드는 단일 클래스로만 제한할 수 있고 상속 트리에서 <xref:System.Printing.PrintQueue> 및 <xref:System.Printing.PrintSystemJobInfo> 모두에 공통인 클래스는 이러한 속성이 없는 <xref:System.Printing.PrintSystemObject>뿐이기 때문입니다.  
  
 아래 코드 예제에 표시된 **ReportAvailabilityAtThisTime** 메서드는 먼저 <xref:System.Boolean> 센티널 변수를 `true`로 초기화합니다.  큐를 사용할 수 없는 경우 이 변수가 `false`로 재설정됩니다.  
  
 그런 다음 이 메서드는 시작 및 "끝" 시간이 동일한지 확인합니다.  동일한 경우 큐를 항상 사용할 수 있으므로 메서드는 `true`를 반환합니다.  
  
 큐를 항상 사용할 수 없는 경우 이 메서드에서는 정적 <xref:System.DateTime.UtcNow%2A> 속성을 사용하여 현재 시간을 <xref:System.DateTime> 개체로 가져옵니다.  <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성 자체가 UTC 시간에 있으므로 현지 시간은 필요하지 않습니다.  
  
 그러나 이러한 두 속성은 <xref:System.DateTime> 개체가 아닙니다.  이러한 속성은 시간을 UTC 자정 이후의 시간\(분\)으로 표시하는 <xref:System.Int32>입니다.  따라서 <xref:System.DateTime> 개체를 자정 이후의 시간\(분\)으로 변환해야 합니다.  변환을 마치면 메서드에서는 "지금"이 큐의 시작 및 "끝" 시간 사이에 있는지 확인하고 "지금"이 두 시간 사이에 없으면 센티널을 false로 설정한 다음 센티널을 반환합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 아래 코드 예제에 표시된 **TimeConverter.ConvertToLocalHumanReadableTime** 메서드는 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]에 새로 추가된 메서드를 사용하지 않으므로 간략히 설명하고 넘어갑니다.  이 메서드는 이중 변환 작업을 수행합니다. 자정 이후의 시간\(분\)을 표시하는 정수를 가져와서 사람이 인식할 수 있는 시간으로 변환한 다음 이를 현지 시간으로 변환해야 합니다.  이를 수행하기 위해 먼저 UTC 자정으로 설정된 <xref:System.DateTime> 개체를 만든 다음 <xref:System.DateTime.AddMinutes%2A> 메서드를 사용하여 메서드에 전달된 시간\(분\)을 추가합니다.  그러면 메서드에 전달된 원래 시간을 표시하는 새 <xref:System.DateTime>이 반환됩니다.  그런 다음 <xref:System.DateTime.ToLocalTime%2A> 메서드에서 이 시간을 현지 시간으로 변환합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## 참고 항목  
 <xref:System.DateTime>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.Printing.PrintQueue>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)