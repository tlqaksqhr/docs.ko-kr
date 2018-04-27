---
title: '방법: 원격으로 프린터 상태 조사'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3d0faedbe8ce3394fb888a6509ece1441f0a353a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>방법: 원격으로 프린터 상태 조사
중간 규모 및 대규모 기업에는 언제든지 종이 걸림이나 용지 부족 또는 다른 문제 상황으로 인해 여러 프린터가 작동하지 않을 수 있습니다. 다양 한 프린터 속성에서 노출 되는 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] Microsoft.NET Framework의 프린터의 상태를 신속 하 게 조사를 수행 하기 위한 수단을 제공 합니다.  
  
## <a name="example"></a>예제  
 이러한 종류의 유틸리티를 만드는 주요 단계는 다음과 같습니다.  
  
1.  모든 인쇄 서버 목록을 가져옵니다.  
  
2.  서버를 반복하여 해당 인쇄 큐를 쿼리합니다.  
  
3.  서버 루프의 각 단계 내에서 모든 서버 큐를 반복하고 큐가 현재 작동하지 않는다는 것을 나타내는 각 속성을 읽습니다.  
  
 아래의 코드는 일련의 코드 조각입니다. 편의를 위해 이 예제에서는 인쇄 서버의 CRLF로 구분된 목록이 있다고 가정합니다. 변수 `fileOfPrintServers` 는 <xref:System.IO.StreamReader> 이 파일에 대 한 개체입니다. 호출의 자체 줄에 각 서버 이름 이므로 <xref:System.IO.StreamReader.ReadLine%2A> 다음 서버의 이름을 가져오고 이동는 <xref:System.IO.StreamReader>의 다음 줄의 시작 부분에는 커서입니다.  
  
 외부 루프 내에서 코드 만듭니다는 <xref:System.Printing.PrintServer> 최신 인쇄 서버에 대 한 개체를 응용 프로그램 서버에 대 한 관리 권한이 임을 지정 합니다.  
  
> [!NOTE]
>  서버가 많은 경우에 사용 하 여 성능을 개선할 수 있습니다는 <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> 만 해야 할 속성을 초기화 하는 생성자입니다.  
  
 이 예제에서는 다음 사용 하 여 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 서버의 모든 컬렉션을 만들 수의 큐 대기 되 고 루프를 시작 합니다. 이 내부 루프에는 프린터의 상태를 검사하는 두 가지 방법에 해당하는 분기 구조가 포함되어 있습니다.  
  
-   플래그를 읽을 수는 <xref:System.Printing.PrintQueue.QueueStatus%2A> 형식인 속성 <xref:System.Printing.PrintQueueStatus>합니다.  
  
-   와 같은 관련 된 각 속성을 읽을 수 있습니다 <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, 및 <xref:System.Printing.PrintQueue.IsPaperJammed%2A>합니다.  
  
 사용자가 이전에 사용할 방법에 대 한 메시지가 표시 되 고의 플래그를 사용 하려는 경우 "y" 응답 두 메서드를 보여 주는이 예제는 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성입니다. 두 가지 방법에 대한 자세한 내용은 아래를 참조하세요.  
  
 마지막으로 결과가 사용자에게 표시됩니다.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 플래그를 사용 하 여 프린터 상태를 확인 하 고 <xref:System.Printing.PrintQueue.QueueStatus%2A> 각 관련 플래그를 설정 하는 경우 참조 확인 속성을 합니다. 일련의 비트 플래그에 하나의 비트가 설정되었는지 확인하는 표준 방법은 일련의 플래그가 있는 논리적 AND 연산을 하나의 피연산자로 수행하고 플래그 자체를 다른 피연산자로 수행하는 것입니다. 플래그 자체가 하나의 비트만 설정하므로 논리적 AND의 결과는 비트가 설정되는 것과 거의 동일합니다. 여부를 확인하려면 플래그 자체와 논리적 AND의 결과를 비교합니다. 자세한 내용은 참조 <xref:System.Printing.PrintQueueStatus>, [& 연산자 (C# 참조)](~/docs/csharp/language-reference/operators/and-operator.md), 및 <xref:System.FlagsAttribute>합니다.  
  
 비트가 설정된 각 특성의 경우 코드는 사용자에게 표시될 최종 보고서에 메시지를 추가합니다. 코드의 끝에 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래 설명되어 있습니다.  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 각 속성을 사용하여 프린터 상태를 확인하려면 단순히 각 속성을 읽고 속성이 `true`인지 여부를 사용자에게 표시할 수 있는 최종 보고서에 메시지를 추가합니다. 코드의 끝에 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래 설명되어 있습니다.  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 **ReportAvailabilityAtThisTime** 메서드는 현재 시간에 큐를 사용 가능한지 확인해야 할 경우에 생성됩니다.  
  
 메서드가 아무 작업도 수행 하는 경우는 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성은 항상 프린터를 사용할 수 있는 경우 때문에 같고 합니다. 메서드 다음 때문에 자정 이후 경과 된 전체 분으로 변환 될 수 있는 현재 시간을 가져옵니다 다른 경우는 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성은 <xref:System.Int32>없는 자정 이후의 시간 (분)을 나타내는 s <xref:System.DateTime> 개체입니다. 마지막으로 메서드는 현재 시간이 시작과 "끝" 시간 사이인지를 확인합니다.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>참고 항목  
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
 [& 연산자 (C# 참조)](~/docs/csharp/language-reference/operators/and-operator.md)  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)
