---
title: "방법: 인쇄 작업 문제 진단 | Microsoft Docs"
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
  - "인쇄 작업, 문제 진단"
  - "인쇄 작업, 문제 해결"
  - "인쇄 작업 문제 해결"
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 인쇄 작업 문제 진단
인쇄되지 않거나 느리게 인쇄되는 인쇄 작업과 관련된 사용자의 불만을 네트워크 관리자가 해결하는 경우가 흔히 있습니다.  [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]의 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에 노출된 다양한 인쇄 작업 속성 집합은 인쇄 작업을 원격에서 빠르게 진단할 수 있는 방법을 제공합니다.  
  
## 예제  
 이러한 종류의 유틸리티를 만드는 주요 단계는 다음과 같습니다.  
  
1.  사용자가 불만족을 표시하는 인쇄 작업을 식별합니다.  사용자는 이 작업을 정확하게 수행할 수 없는 경우가 많습니다.  사용자는 인쇄 서버나 프린터의 이름을 모를 수 있습니다.  또한 해당 <xref:System.Printing.PrintQueue.Location%2A> 속성을 설정할 때 사용한 것과 다른 용어로 프린터 위치를 설명할 수 있습니다.  따라서 사용자가 현재 제출한 작업의 목록을 생성하는 것이 좋습니다.  둘 이상의 작업이 있는 경우 사용자와 인쇄 시스템 관리자 간의 통신으로 문제가 있는 작업을 찾을 수 있습니다.  하위 단계는 다음과 같습니다.  
  
    1.  모든 인쇄 서버의 목록을 가져옵니다.  
  
    2.  서버를 순환 검색하여 해당 인쇄 큐를 쿼리합니다.  
  
    3.  서버 루프의 각 처리 내에서 모든 서버 큐를 순환하며 해당 작업을 쿼리합니다  
  
    4.  큐 루프의 각 처리 내에서 해당 작업을 순환하며 불평하는 사용자가 제출한 작업에 대한 식별 정보를 수집합니다.  
  
2.  문제가 있는 인쇄 작업을 식별했으면 관련 속성을 검사하여 문제를 확인합니다.  예를 들어 작업이 오류 상태이거나 작업이 인쇄되기 전에 큐를 처리하는 프린터가 오프라인으로 전환되었는지 확인합니다.  
  
 아래의 코드는 일련의 코드 예제입니다.  첫 번째 코드 예제에는 인쇄 큐 순환이 포함되어 있습니다\(위의  단계 1c 참조\). `myPrintQueues` 변수는 현재 인쇄 서버의 <xref:System.Printing.PrintQueueCollection> 개체입니다.  
  
 이 코드 예제에서는 먼저 <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=fullName>를 사용하여 현재 인쇄 큐를 새로 고칩니다.  그러면 개체의 속성이 해당하는 실제 프린터의 상태가 정확하게 나타나게 됩니다.  그런 다음 응용 프로그램에서는 <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>을 사용하여 현재 인쇄 큐에 있는 인쇄 작업을 컬렉션을 가져옵니다.  
  
 다음으로 응용 프로그램에서는 <xref:System.Printing.PrintSystemJobInfo> 컬렉션을 순환하며 각 <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> 속성과 불평하는 사용자의 별칭을 비교합니다.  이 둘이 일치하면 응용 프로그램에서는 작업에 대한 식별 정보를 표시할 문자열에 추가합니다.  `userName` 및 `jobList` 변수는 응용 프로그램에서 이전에 초기화했습니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 다음 코드 예제에서는 2단계의 응용 프로그램을  선택합니다\(앞 부분 참조\). 문제 있는 작업을 식별하고 나면 응용 프로그램에 문제를 식별할 정보를 입력하라는 메시지가 표시됩니다.  이 정보를 사용하여 <xref:System.Printing.PrintServer>, <xref:System.Printing.PrintQueue> 및 <xref:System.Printing.PrintSystemJobInfo> 개체를 만듭니다.  
  
 이제 응용 프로그램에는 인쇄 작업의 상태를 확인하는 두 가지 방법에 해당하는 분기 구조가 있습니다.  
  
-   형식이 <xref:System.Printing.PrintJobStatus>인 <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> 속성의 플래그를 읽을 수 있습니다.  
  
-   <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> 및 <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>와 같은 관련된 각 속성을 읽을 수 있습니다.  
  
 이 예제에서는 두 메서드를 모두 보여 줍니다. 따라서 사용자는 이전에 사용할 메서드를 묻는 메시지가 표시될 때 <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> 속성의 플래그를 사용하려는 경우 "Y"로 대답했을 것입니다.  두 메서드의 세부 사항은 아래를 참조하십시오.  마지막으로 응용 프로그램에서는 **ReportQueueAndJobAvailability**라는 메서드를 사용하여 작업을 현재 인쇄할 수 있는지 여부를 보고합니다.  이 메서드에 대해서는 [인쇄 작업을 현재 인쇄할 수 있는지 확인](../../../../docs/framework/wpf/advanced/how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md)에서 설명합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> 속성의 플래그를 사용하여 인쇄 작업 상태를 검사하려면 관련된 각 플래그를 검사하여 설정되어 있는지 확인합니다.  한 비트가 비트 플래그 집합에 설정되어 있는지 알아볼 수 있는 표준 방법은 플래그 집합을 한 피연산자로 사용하고 플래그 자체를 다른 피연산자로 사용하여 논리 AND 연산을 수행하는 것입니다.  플래그 자체는 한 비트만 설정되므로 논리 AND의 결과는 기껏해야 같은 비트를 설정하는 것입니다.  해당 비트가 설정되어 있는지 확인하려면 논리 AND의 결과를 플래그 자체와 비교하면 됩니다.  자세한 내용은 <xref:System.Printing.PrintJobStatus>, [& 연산자\(C\# 참조\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) 및 <xref:System.FlagsAttribute>를 참조하십시오.  
  
 비트가 설정된 각 특성에 대해 코드에서는 이를 콘솔 화면에 보고하고 경우에 따라 응답 방법을 제안합니다.  작업 또는 큐가 일시 중지하는 경우 호출하는 **HandlePausedJob** 메서드에 대해서는 아래에서 설명합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 별도의 속성을 사용하여 인쇄 작업 상태를 검사하려면 각 속성을 읽고 속성이 `true`인 경우 콘솔 화면에 보고하고 가능한 경우 응답 방법을 제안하면 됩니다.  작업 또는 큐가 일시 중지하는 경우 호출하는 **HandlePausedJob** 메서드에 대해서는 아래에서 설명합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 **HandlePausedJob** 메서드를 사용하면 응용 프로그램의 사용자가 일시 중지된 작업을 원격으로 다시 시작할 수 있습니다.  인쇄 큐가 일시 중지된 이유가 있을 것이므로 메서드에서는 먼저 작업을 다시 시작할지 여부에 대한 사용자의 결정을 묻는 메시지를 표시합니다.  "Y"로 대답하면 <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
 그런 다음, 작업이 인쇄 큐와 별개로 일시 중지된 경우에 한해 작업 자체를 다시 시작할지 여부를 결정하라는 메시지를 표시합니다.  <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=fullName>와 <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=fullName>를 비교해 보십시오. "Y"로 대답하면 <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=fullName> 메서드를 호출하고 그렇지 않으면 <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> 메서드를 호출합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## 참고 항목  
 <xref:System.Printing.PrintJobStatus>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintQueue>   
 [& 연산자\(C\# 참조\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)