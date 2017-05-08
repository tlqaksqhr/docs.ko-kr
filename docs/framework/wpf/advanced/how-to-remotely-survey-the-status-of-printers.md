---
title: "방법: 원격으로 프린터 상태 조사 | Microsoft Docs"
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
  - "프린터 상태, 원격 조사"
  - "프린터 상태 원격 조사"
  - "상태, 프린터, 원격 조사"
  - "프린터 상태 원격 조사"
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 원격으로 프린터 상태 조사
중대형 기업에서 언제든지 용지 걸림이나 용지 부족 또는 다른 문제 상황으로 인해 작동하지 않는 여러 프린터가 있을 수 있습니다.  [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]의 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에 노출된 다양한 프린터 속성 집합은 프린터의 상태를 빠르게 조사할 수 있는 수단을 제공합니다.  
  
## 예제  
 이러한 종류의 유틸리티를 만드는 주요 단계는 다음과 같습니다.  
  
1.  모든 인쇄 서버의 목록을 가져옵니다.  
  
2.  서버를 순환 검색하여 해당 인쇄 큐를 쿼리합니다.  
  
3.  서버 루프의 각 처리 내에서 모든 서버 큐를 순환 검색하고 큐가 현재 작동하고 있지 않음을 나타낼 수 있는 각 속성을 읽습니다.  
  
 아래의 코드는 일련의 코드 조각입니다.  편의상 이 예제에서는 프린터 서버에 대한 CRLF 구분 목록을 사용합니다.  `fileOfPrintServers` 변수는 이 파일에 대한 <xref:System.IO.StreamReader> 개체입니다.  각 서버 이름은 자신의 줄에 있기 때문에 <xref:System.IO.StreamReader.ReadLine%2A>을 호출하면 다음 서버의 이름을 가져오며 <xref:System.IO.StreamReader>의 커서를 다음 줄의 시작 부분으로 이동합니다.  
  
 바깥쪽 루프 내에서 코드는 최신 인쇄 서버에 대해 <xref:System.Printing.PrintServer> 개체를 만들고 응용 프로그램에서 해당 서버에 대한 관리자 권한을 가져야 함을 지정합니다.  
  
> [!NOTE]
>  서버가 많은 경우 필요한 속성만 초기화하는 [PrintServer\(String, String\<xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> 생성자를 사용하여 성능을 향상시킬 수 있습니다.  
  
 그런 다음 예제에서는 <xref:System.Printing.PrintServer.GetPrintQueues%2A>를 사용하여 모든 서버 큐의 컬렉션을 만들고 이러한 큐를 순환 검색합니다.  안쪽 루프에는 프린터의 상태를 검사하는 두 가지 방법에 해당하는 분기 구조가 있습니다.  
  
-   형식이 <xref:System.Printing.PrintQueueStatus>인 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 읽을 수 있습니다.  
  
-   <xref:System.Printing.PrintQueue.IsOutOfPaper%2A> 및 <xref:System.Printing.PrintQueue.IsPaperJammed%2A>와 같은 각 관련 속성을 읽을 수 있습니다.  
  
 이 예제에서는 두 메서드를 모두 보여 줍니다. 따라서 사용자는 이전에 사용할 메서드를 묻는 메시지가 표시될 때 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 사용하려는 경우 "Y"로 대답했을 것입니다.  두 메서드의 세부 사항은 아래를 참조하십시오.  
  
 마지막으로 결과가 사용자에게 표시됩니다.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 사용하여 프린터 상태를 검사하려면 각 관련 플래그를 검사하여 설정되어 있는지 확인합니다.  한 비트가 비트 플래그 집합에 설정되어 있는지 알아볼 수 있는 표준 방법은 플래그 집합을 한 피연산자로 사용하고 플래그 자체를 다른 피연산자로 사용하여 논리 AND 연산을 수행하는 것입니다.  플래그 자체는 한 비트만 설정되므로 논리 AND의 결과는 기껏해야 같은 비트를 설정하는 것입니다.  해당 비트가 설정되어 있는지 확인하려면 논리 AND의 결과를 플래그 자체와 비교하면 됩니다.  자세한 내용은 <xref:System.Printing.PrintQueueStatus>, [& 연산자\(C\# 참조\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) 및 <xref:System.FlagsAttribute>를 참조하십시오.  
  
 비트가 설정된 각 특성에 대해 코드에서 사용자에게 표시될 최종 보고서에 메시지를 추가합니다.  코드의 끝 부분에서 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래에서 설명합니다.  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 각 속성을 사용하여 프린터 상태를 검사하려면 각 속성을 읽고 속성이 `true`인 경우 사용자에게 표시할 최종 보고서에 메모를 추가하면 됩니다.  코드의 끝 부분에서 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래에서 설명합니다.  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 해당 요일의 현재 시간에 큐를 사용할 수 있는지 확인하기 위해 **ReportAvailabilityAtThisTime** 메서드를 생성했습니다.  
  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성이 같은 경우 언제든지 프린터를 사용할 수 있으므로 메서드에서 아무 작업도 수행하지 않습니다.  두 속성이 다른 경우 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성은 <xref:System.DateTime> 개체가 아니라 자정 이후 시간\(분\)을 나타내는 <xref:System.Int32>이므로 메서드는 자정 이후 총 시간\(분\)으로 변환될 현재 시간을 가져옵니다.  마지막으로 메서드에서 현재 시간이 시작과 "끝" 시간 내에 있는지 알아보기 위해 검사합니다.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## 참고 항목  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>   
 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>   
 <xref:System.DateTime>   
 <xref:System.Printing.PrintQueueStatus>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 [& 연산자\(C\# 참조\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)