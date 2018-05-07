---
title: 추적 레코드
ms.date: 03/30/2017
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
ms.openlocfilehash: b07175943f85b61024030c1e0251e24d1eb35c86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tracking-records"></a>추적 레코드
워크플로 런타임을 계측하여 워크플로 인스턴스 실행을 추적하는 추적 레코드를 내보냅니다.  
  
## <a name="tracking-records"></a>추적 레코드  
 다음 표에서는 워크플로 런타임에서 내보내는 추적 레코드에 대해 자세히 설명합니다.  
  
|추적 레코드|설명|  
|---------------------|-----------------|  
|워크플로 수명 주기 레코드|워크플로 인스턴스 수명 주기의 다양한 단계에서 내보냅니다. 예를 들어 워크플로가 시작되거나 완료되면 레코드를 내보냅니다.|  
|활동 수명 주기 레코드|활동 실행에 대해 자세히 설명합니다. 이러한 레코드는 활동이 예약된 시점, 활동이 완료된 시점, 오류가 발생한 시점 등과 같은 워크플로 활동 상태를 나타냅니다.|  
|책갈피 다시 시작 레코드|워크플로 인스턴스 내의 책갈피를 다시 시작할 때마다 내보냅니다.|  
|사용자 지정 추적 레코드|워크플로 작성자가 사용자 지정 추적 레코드를 만들어 사용자 지정 활동 중에 내보낼 수 있습니다.|  
  
 WF 런타임에 내보내는 모든 추적 관련 레코드는 일반 데이터 집합을 포함하는 기본 클래스 <xref:System.Activities.Tracking.TrackingRecord>에서 파생됩니다. 추적 레코드에는 단순 워크플로에 대한 수명 주기가 표시됩니다. 각 추적 레코드에는 <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A> 및 추적 레코드 유형 관련 추가 정보와 같은 관련 추적 이벤트에 대한 자세한 정보가 포함됩니다.  
  
 워크플로 런타임에서 내보내는 <xref:System.Activities.Tracking.TrackingRecord> 개체 형식은 다음과 같습니다.  
  
-   **WorkflowInstanceRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 워크플로 인스턴스의 수명 주기에 대해 설명 합니다. 예를 들어 워크플로가 시작되거나 완료되면 레코드를 내보냅니다. 이 레코드에는 워크플로 인스턴스 상태가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.WorkflowInstanceRecord>를 참조하세요.  
  
-   **WorkflowInstanceAbortedRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 는 워크플로 인스턴스가 중단 될 때 내보내집니다. 이 레코드에는 워크플로 인스턴스 중단 이유가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>를 참조하세요.  
  
-   **WorkflowInstanceUnhandledExceptionRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 예외가 워크플로 인스턴스에서 발생 하 고 모든 활동에서 처리 되지 않은 경우에 내보내집니다. 이 레코드에는 자세한 예외 정보가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>를 참조하세요.  
  
-   **WorkflowInstanceSuspendedRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 워크플로 인스턴스가 일시 중단 될 때마다 발생 합니다. 이 레코드에는 워크플로 인스턴스 일시 중지 이유가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>를 참조하세요.  
  
-   **WorkflowInstanceTerminatedRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 워크플로 인스턴스가 종료 될 때마다 발생 합니다. 이 레코드에는 워크플로 인스턴스 종료 이유가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>를 참조하세요.  
  
-   **ActivityStateRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 워크플로 내의 활동이 실행 될 때 내보내집니다. 이 레코드는 워크플로 인스턴스 내의 활동 상태를 나타냅니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.ActivityStateRecord>를 참조하세요.  
  
-   **ActivityScheduledRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 는 자식 활동 예약 될 때 내보내집니다. 이 레코드에는 활동을 예약하는 부모 활동과 예약된 자식 활동에 대한 자세한 정보가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.ActivityScheduledRecord>를 참조하세요.  
  
-   **FaultPropagationRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 레코드에서 보이는 처리 될 때까지 각 처리기에 대해 내보내집니다. 이 레코드는 워크플로 인스턴스 내에서 오류가 발생한 경로를 나타내는 데 사용됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.FaultPropagationRecord>를 참조하세요.  
  
-   **CancelRequestedRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 자식 활동 취소 하려고 때마다 내보내집니다. 이 레코드에는 부모 활동과 취소되는 자식 활동에 대한 자세한 정보가 포함됩니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.CancelRequestedRecord>를 참조하세요.  
  
-   **BookmarkResumptionRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 이 성공적으로 다시 시작 하는 책갈피를 추적 합니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.BookmarkResumptionRecord>를 참조하세요.  
  
-   **CustomTrackingRecord** -이 <xref:System.Activities.Tracking.TrackingRecord> 를 만들어 사용자 지정 워크플로 활동 내에서 워크플로 작성자입니다. 사용자 지정 추적 레코드를 레코드와 함께 내보낼 데이터로 채울 수 있습니다. 이 레코드에 대한 자세한 내용은 <xref:System.Activities.Tracking.CustomTrackingRecord>를 참조하세요.  
  
 예를 들어 추적 레코드를 다음 순서로 내보내는 <xref:System.Activities.Statements.Sequence> 작업을 포함하는 간단한 <xref:System.Activities.Statements.WriteLine> 활동이 있습니다.  
  
1.  <xref:System.Activities.Tracking.WorkflowInstanceRecord>는 워크플로가 시작되었음을 나타냅니다.  
  
2.  <xref:System.Activities.Tracking.ActivityScheduledRecord>는 활동이 예약되어 있음을 나타냅니다. 이 경우 <xref:System.Activities.Statements.Sequence> 활동입니다.  
  
3.  <xref:System.Activities.Tracking.ActivityScheduledRecord>는 <xref:System.Activities.Statements.WriteLine> 활동을 나타냅니다.  
  
4.  두 가지 활동의 완료를 나타내는 두 <xref:System.Activities.Tracking.ActivityStateRecord> 레코드가 있습니다.  
  
5.  <xref:System.Activities.Tracking.WorkflowInstanceRecord>는 워크플로가 완료되었음을 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Server App Fabric 모니터링](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [App Fabric로 응용 프로그램 모니터링](http://go.microsoft.com/fwlink/?LinkId=201275)
