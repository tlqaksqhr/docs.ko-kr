---
title: '방법: 인쇄 작업을 현재 인쇄할 수 있는지 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
ms.openlocfilehash: e5ea5ad3bcb10bfbc091f0b5852ee181a2c3fa8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548037"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>방법: 인쇄 작업을 현재 인쇄할 수 있는지 확인
인쇄 큐 항상 사용할 수 없는 하루 24 시간에 대 한 합니다. 하루 중 특정 시간에 사용할 수 없도록 설정할 수 있는 시작 및 종료 시간 속성을 갖게 됩니다. 예를 들어 특정 부서 오후 5 시 이후에 단독으로 사용에 대 한 프린터를 예약 하 고이 기능을 사용할 수 있습니다. 해당 부서 사용 되는 다른 큐에서는 다른 부서에서 프린터를 처리 해야 합니다. 다른 부서에 대 한 큐 오후 5 시 이후에 사용할 수 없게 설정 됩니다, 그리고 부서에서 선호 하는 방식된에 대 한 큐 수로 설정 되어 동안 항상 사용 가능한 합니다.  
  
 또한 인쇄 작업 자체는 지정한 시간 범위 내 에서만 인쇄 가능 하도록 설정할 수 있습니다.  
  
 <xref:System.Printing.PrintQueue> 및 <xref:System.Printing.PrintSystemJobInfo> 클래스에 노출 된 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] Microsoft.NET Framework의 원격으로 현재 시간에 지정된 된 큐에 지정된 된 인쇄 작업 인쇄할 수 있는지를 확인 하기 위한 수단을 제공 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 인쇄 작업 문제를 진단할 수 있는 샘플입니다.  
  
 이러한 종류의 기능에 대 한 두 가지 주요 단계는 다음과 같습니다.  
  
1.  읽기는 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 의 속성은 <xref:System.Printing.PrintQueue> 현재 시간 사이 인지 여부를 확인 합니다.  
  
2.  읽기는 <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> 의 속성은 <xref:System.Printing.PrintSystemJobInfo> 현재 시간 사이 인지 여부를 확인 합니다.  
  
 이러한 속성은 사실에서 문제가 발생 하지만 <xref:System.DateTime> 개체입니다. 대신 된 <xref:System.Int32> 하루 중 시간으로 자정 이후의 시간을 분 단위로 표현 하는 개체입니다. 또한 자정 표현에 현재 표준 시간대 하지만 utc (협정 세계시)입니다.  
  
 정적 메서드를 제공 하는 첫 번째 코드 예제에서는 **ReportQueueAndJobAvailability**, 전달 되는 <xref:System.Printing.PrintSystemJobInfo> 작업을 현재 시간에 인쇄할 수 있는지 여부를 확인 하는 도우미 메서드를 호출 하 고, 그렇지 않은 경우 인쇄할 수 있는 경우. 에 <xref:System.Printing.PrintQueue> 메서드에 전달 되지 않습니다. 때문에 이것이 <xref:System.Printing.PrintSystemJobInfo> 큐에 대 한 참조가 포함 해당 <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> 속성입니다.  
  
 하위 메서드 오버 로드 된 포함 **ReportAvailabilityAtThisTime** 하나를 사용할 수 있는 메서드는 <xref:System.Printing.PrintQueue> 또는 <xref:System.Printing.PrintSystemJobInfo> 매개 변수로 합니다. 또한 한 **TimeConverter.ConvertToLocalHumanReadableTime**합니다. 이러한 모든 메서드는 아래 설명 되어 있습니다.  
  
 **ReportQueueAndJobAvailability** 큐 또는 인쇄 작업이 사용할 수 없을 경우이 이번에 참조를 확인 하 여 메서드를 시작 합니다. 둘 중 하나를 사용할 수 없는 경우 다음 확인 하는 경우 큐를 사용할 수 없습니다. 사용할 수 없는 경우이 팩트 및 때 큐를 사용할 수 있는 다시 시간 메서드가 보고 합니다. 그런 다음 작업을 확인 하 고 다음에 사용할 수 없는 경우 보고 범위 인쇄할 수 있는 것입니다. 마지막으로 메서드가 때 작업을 인쇄할 수는 가장 빠른 시간을 보고 합니다. 뒤에 두 번 이상입니다.  
  
-   인쇄 큐가 사용 가능한 다음 시간입니다.  
  
-   인쇄 작업을 사용할 다음 시간입니다.  
  
 하루 중 시간을 보고할 때는 <xref:System.DateTime.ToShortTimeString%2A> 되므로이 메서드는 년, 월 및 일의 출력에도 메서드가 호출 됩니다. 특정 연도, 월 또는 일에 인쇄 큐 또는 인쇄 작업의 가용성을 제한할 수 없습니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 두 오버 로드는 **ReportAvailabilityAtThisTime** 메서드 항목에 전달 하는 형식을 제외한 동일는 <xref:System.Printing.PrintQueue> 버전은 아래 제시 된 합니다.  
  
> [!NOTE]
>  메서드는 형식 제외 하면 동일한 팩트에 대 한 문제를 발생 시킵니다 때문에 샘플에서는 변수를 제네릭 메서드 **ReportAvailabilityAtThisTime\<T >** 합니다. 이유는 이러한 메서드를 가진 에게만 부여 되어야 해야 하는 **StartTimeOfDay** 및 **UntilTimeOfDay** 메서드를 호출 하는 속성 이지만 제네릭 메서드만 제한할 수 있습니다는 단일 클래스 및 모두에 공통적인 유일한 클래스 <xref:System.Printing.PrintQueue> 및 <xref:System.Printing.PrintSystemJobInfo> 상속 트리는 <xref:System.Printing.PrintSystemObject> 있는 이러한 속성이 없습니다.  
  
 **ReportAvailabilityAtThisTime** 메서드 (아래 코드 예제에 제공 된)을 초기화 하 여 시작 된 <xref:System.Boolean> 센티널 변수를 `true`합니다. 으로 다시 설정 `false`큐를 사용할 수 없는 경우, 합니다.  
  
 메서드가 있는지를 확인 하는 다음으로 시작 및 "끝" 시간은 동일 합니다. 인 경우 큐는 항상 사용할 수, 메서드가 반환 되므로 `true`합니다.  
  
 큐를 사용할 수 없는 항상 정적 사용 <xref:System.DateTime.UtcNow%2A> 현재 시간을 가져올 속성을 <xref:System.DateTime> 개체입니다. (때문에 현지 시간 필요 하지 않습니다는 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성은 UTC 시간으로 자체입니다.)  
  
 그러나 이러한 두 속성은 <xref:System.DateTime> 개체입니다. 이들은 <xref:System.Int32>의시간 (분) 후 UTC 자정 수로 표현 합니다. 변환 해야 하므로 우리의 <xref:System.DateTime> 개체 자정 이후의 시간 (분)입니다. 완료 되 면 해당 메서드 단순히 확인 되는지 "now" 여부를 확인할 큐의 시작 간 및 "끝" 시간 집합 센티널 false "지금"을 두 번 사이 있지 않습니다와 센티널을 반환 합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 **TimeConverter.ConvertToLocalHumanReadableTime** 메서드 (아래 코드 예제에 제공 된) 토론은 간단한 Microsoft.NET Framework와 함께 도입 하는 메서드를 사용 하지 않습니다. 메서드에 이중 변환 작업: 자정 이후의 시간 (분)을 표현 하는 정수를 사람이 읽을 수 시간으로 변환 해야 하 고이 현지 시간으로 변환 해야 합니다. 먼저 만들어이 작업을 수행 하기는 <xref:System.DateTime> UTC 다음 변수를 사용 하는 자정으로 설정 된 개체는 <xref:System.DateTime.AddMinutes%2A> 메서드를 메서드에 전달 된 시간 (분)을 추가 합니다. 반환 합니다. 새 <xref:System.DateTime> 메서드에 전달 된 원래 시간을 표현 합니다. <xref:System.DateTime.ToLocalTime%2A> 메서드 다음이 현지 시간으로 변환 합니다.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)
