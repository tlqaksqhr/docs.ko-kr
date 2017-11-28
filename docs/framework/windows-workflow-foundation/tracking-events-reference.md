---
title: "추적 이벤트 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d54c8bd4c6a73b9ff5b4066832b557041d7dec0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="tracking-events-reference"></a>추적 이벤트 참조
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]의 워크플로는 다양한 수명 단계를 거치면서 실행되는 동안 추적 이벤트를 발생시킵니다. 호스트는 이 이벤트의 알림을 신청하여 수명 중에 워크플로 진행 상태를 계속 업데이트할 수 있습니다. 이 단원에서는 발생하는 추적 이벤트를 설명합니다.  
  
## <a name="event-reference"></a>이벤트 참조  
  
|이벤트 ID|이벤트 수준|이벤트 메시지|키워드|  
|--------------|-----------------|-------------------|--------------|  
|[100 - WorkflowInstanceRecord](../../../docs/framework/windows-workflow-foundation/100-workflowinstancerecord.md)|정보|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[101 - WorkflowInstanceUnhandledExceptionRecord](../../../docs/framework/windows-workflow-foundation/101-workflowinstanceunhandledexceptionrecord.md)|오류|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[102 - WorkflowInstanceAbortedRecord](../../../docs/framework/windows-workflow-foundation/102-workflowinstanceabortedrecord.md)|경고|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[103 - ActivityStateRecord](../../../docs/framework/windows-workflow-foundation/103-activitystaterecord.md)|정보|TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[104 - ActivityScheduledRecord](../../../docs/framework/windows-workflow-foundation/104-activityscheduledrecord.md)|정보|TrackRecord = ActivityScheduledRecord, InstanceID = %1,  RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[105 - FaultPropagationRecord](../../../docs/framework/windows-workflow-foundation/105-faultpropagationrecord.md)|경고|TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8,  FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[106 - CancelRequestRecord](../../../docs/framework/windows-workflow-foundation/106-cancelrequestrecord.md)|정보|TrackRecord = CancelRequestedRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[107 -- BookmarkResumptionRecord](../../../docs/framework/windows-workflow-foundation/107-bookmarkresumptionrecord.md)|정보|TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5,  OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[108 - CustomTrackingRecordInfo](../../../docs/framework/windows-workflow-foundation/108-customtrackingrecordinfo.md)|정보|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[110 - CustomTrackingRecordWarning](../../../docs/framework/windows-workflow-foundation/110-customtrackingrecordwarning.md)|경고|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[111 - CustomTrackingRecordError](../../../docs/framework/windows-workflow-foundation/111-customtrackingrecorderror.md)|오류|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[112 - WorkflowInstanceSuspendedRecord](../../../docs/framework/windows-workflow-foundation/112-workflowinstancesuspendedrecord.md)|정보|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[113 - WorkflowInstanceTerminatedRecord](../../../docs/framework/windows-workflow-foundation/113-workflowinstanceterminatedrecord.md)|오류|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|[114 - WorkflowInstanceRecordWithId](../../../docs/framework/windows-workflow-foundation/114-workflowinstancerecordwithid.md)|정보|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[115 - WorkflowInstanceAbortedRecordWithId](../../../docs/framework/windows-workflow-foundation/115-workflowinstanceabortedrecordwithid.md)|경고|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity %8 =|HealthMonitoring, WFTracking|  
|[116 - WorkflowInstanceSuspendedRecordWithId](../../../docs/framework/windows-workflow-foundation/116-workflowinstancesuspendedrecordwithid.md)|정보|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[117 - WorkflowInstanceTerminatedRecordWithId](../../../docs/framework/windows-workflow-foundation/117-workflowinstanceterminatedrecordwithid.md)|오류|TrackRecord WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8 =|HealthMonitoring, WFTracking|  
|[118 - WorkflowInstanceUnhandledExceptionRecordWithId](../../../docs/framework/windows-workflow-foundation/118-workflowinstanceunhandledexceptionrecordwithid.md)|오류|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName = = %8, Exception = %9, Annotations = %10, ProfileName = %11, WorkflowDefinitionIdentity = %12|HealthMonitoring, WFTrackingHealthMonitoring, WFTracking|  
|[119 - WorkflowInstanceUpdatedRecord](../../../docs/framework/windows-workflow-foundation/119-workflowinstanceupdatedrecord.md)|정보|TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9|HealthMonitoring, WFTracking|  
|[225 - TraceCorrelationKeys](../../../docs/framework/windows-workflow-foundation/225-tracecorrelationkeys.md)|정보|'%3' 부모 범위에서 '%2' 값을 사용하여 '%1' 상관 관계 키를 계산했습니다.|WFServices 문제 해결|  
|[440 - StartSignpostEvent1](../../../docs/framework/windows-workflow-foundation/440-startsignpostevent.md)|정보|동작 경계입니다.|WFServices 문제 해결|  
|[441- StopSignpostEvent1](../../../docs/framework/windows-workflow-foundation/441-stopsignpostevent.md)|정보|동작 경계입니다.|WFServices 문제 해결|  
|[1001 - WorkflowApplicationCompleted](../../../docs/framework/windows-workflow-foundation/1001-workflowapplicationcompleted.md)|정보|WorkflowInstance Id: '%1'이(가) Closed 상태에서 완료되었습니다.|WFRuntime|  
|[1002 - WorkflowApplicationTerminated](../../../docs/framework/windows-workflow-foundation/1002-workflowapplicationterminated.md)|정보|WorkflowApplication Id: '%1'이(가) 종료되었습니다. 예외가 발생하여 오류 상태로 완료되었습니다.|WFRuntime|  
|[1003 - WorkflowInstanceCanceled](../../../docs/framework/windows-workflow-foundation/1003-workflowinstancecanceled.md)|정보|WorkflowInstance Id: '%1'이(가) Canceled 상태에서 완료되었습니다.|WFRuntime|  
|[1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md)|정보|WorkflowInstance Id: '%1'이(가) 예외와 함께 중단되었습니다.|WFRuntime|  
|[1005 - WorkflowApplicationIdled](../../../docs/framework/windows-workflow-foundation/1005-workflowapplicationidled.md)|정보|WorkflowApplication Id: '%1'이(가) 유휴 상태가 되었습니다.|WFRuntime|  
|[1006 - WorkflowApplicationUnhandledException](../../../docs/framework/windows-workflow-foundation/1006-workflowapplicationunhandledexception.md)|오류|WorkflowInstance Id: '%1'에 처리 되지 않은 예외가 발생 했습니다.  '%2', DisplayName 활동에서 발생 한 예외: '%3'.  다음과 같은 조치가 취해집니다: %4입니다.|WFRuntime|  
|[1007 - WorkflowApplicationPersisted](../../../docs/framework/windows-workflow-foundation/1007-workflowapplicationpersisted.md)|정보|WorkflowApplication Id: '%1'이(가) 지속되었습니다.|WFRuntime|  
|[1008 - WorkflowApplicationUnloaded](../../../docs/framework/windows-workflow-foundation/1008-workflowapplicationunloaded.md)|정보|WorkflowInstance Id: '%1'이(가) 언로드되었습니다.|WFRuntime|  
|[1009 - ActivityScheduled](../../../docs/framework/windows-workflow-foundation/1009-activityscheduled.md)|정보|Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1010 - ActivityCompleted](../../../docs/framework/windows-workflow-foundation/1010-activitycompleted.md)|정보|Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1011 - ScheduleExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1011-scheduleexecuteactivityworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 예약되었습니다.|WFRuntime|  
|[1012 - StartExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1012-startexecuteactivityworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.|WFRuntime|  
|[1013 - CompleteExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1013-completeexecuteactivityworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 완료되었습니다.|WFRuntime|  
|[1014 - ScheduleCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1014-schedulecompletionworkitem.md)|자세히|부모 작업 '%1', DisplayName에 대해 CompletionWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.  작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.|WFRuntime|  
|[1015 - StartCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1015-startcompletionworkitem.md)|자세히|부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.|WFRuntime|  
|[1016 - CompleteCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1016-completecompletionworkitem.md)|자세히|부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.|WFRuntime|  
|[1017 - ScheduleCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1017-schedulecancelactivityworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 예약되었습니다.|WFRuntime|  
|[1018 - StartCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1018-startcancelactivityworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem의 실행을 시작합니다.|WFRuntime|  
|[1019 - CompleteCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1019-completecancelactivityworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 완료되었습니다.|WFRuntime|  
|[1020 - CreateBookmark](../../../docs/framework/windows-workflow-foundation/1020-createbookmark.md)|자세히|책갈피를 만든 작업 '%1', DisplayName: '%2', InstanceId: '%3'.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1021 - ScheduleBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1021-schedulebookmarkworkitem.md)|자세히|작업 '%1', DisplayName에 대해 BookmarkWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1022 - StartBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1022-startbookmarkworkitem.md)|자세히|작업 '%1', DisplayName에 BookmarkWorkItem의 실행 시작: '%2', InstanceId: '%3'.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1023 - CompleteBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1023-completebookmarkworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 BookmarkWorkItem이 완료되었습니다. BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1024 - CreateBookmarkScope](../../../docs/framework/windows-workflow-foundation/1024-createbookmarkscope.md)|자세히|%1 BookmarkScope를 만들었습니다.|WFRuntime|  
|[1025 - BookmarkScopeInitialized](../../../docs/framework/windows-workflow-foundation/1025-bookmarkscopeinitialized.md)|자세히|TemporaryId: '%1'인 BookmarkScope가 Id: '%2'(으)로 초기화되었습니다.|WFRuntime|  
|[1026 - ScheduleTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1026-scheduletransactioncontextworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 예약되었습니다.|WFRuntime|  
|[1027 - StartTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1027-starttransactioncontextworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem의 실행 시작입니다.|WFRuntime|  
|[1028 - CompleteTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1028-completetransactioncontextworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 완료되었습니다.|WFRuntime|  
|[1029 - ScheduleFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1029-schedulefaultworkitem.md)|자세히|작업 '%1', DisplayName에 대해 FaultWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.  작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.|WFRuntime|  
|[1030 - StartFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1030-startfaultworkitem.md)|자세히|작업 '%1', DisplayName에 FaultWorkItem의 실행 시작: '%2', InstanceId: '%3'.  작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.|WFRuntime|  
|[1031 - CompleteFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1031-completefaultworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.|WFRuntime|  
|[1032 - ScheduleRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1032-scheduleruntimeworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.|WFRuntime|  
|[1033 - StartRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1033-startruntimeworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목의 실행을 시작합니다.|WFRuntime|  
|[1034 - CompleteRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1034-completeruntimeworkitem.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 완료되었습니다.|WFRuntime|  
|[1035 - RuntimeTransactionSet](../../../docs/framework/windows-workflow-foundation/1035-runtimetransactionset.md)|자세히|런타임 트랜잭션이 작업 '%1', DisplayName가 설정한: '%2', InstanceId: '%3'.  실행에만 작업 '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1036 - RuntimeTransactionCompletionRequested](../../../docs/framework/windows-workflow-foundation/1036-runtimetransactioncompletionrequested.md)|자세히|작업 '%1', DisplayName: '%2', InstanceId: '%3'이(가) 런타임 트랜잭션 완료를 예약했습니다.|WFRuntime|  
|[1037 - RuntimeTransactionComplete](../../../docs/framework/windows-workflow-foundation/1037-runtimetransactioncomplete.md)|자세히|런타임 트랜잭션이 '%1' 상태로 완료되었습니다.|WFRuntime|  
|[1038 - EnterNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1038-enternopersistblock.md)|자세히|비지속성 블록으로 들어갑니다.|WFRuntime|  
|[1039 - ExitNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1039-exitnopersistblock.md)|자세히|비지속성 블록에서 나옵니다.|WFRuntime|  
|[1040 - InArgumentBound](../../../docs/framework/windows-workflow-foundation/1040-inargumentbound.md)|자세히|작업 '%2', DisplayName: '%3', InstanceId: '%4'에 대한 In Argument '%1'이(가) 값: %5에 바인딩되었습니다.|WFActivities|  
|[1041 - WorkflowApplicationPersistableIdle](../../../docs/framework/windows-workflow-foundation/1041-workflowapplicationpersistableidle.md)|정보|WorkflowApplication Id: '%1'는 유휴 상태로 지속 됩니다.  다음과 같은 조치가 취해집니다: %2입니다.|WFRuntime|  
|[1101 - WorkflowActivityStart](../../../docs/framework/windows-workflow-foundation/1101-workflowactivitystart.md)|정보|WorkflowInstance Id: '%1' E2E 작업|WFRuntime|  
|[1102 - WorkflowActivityStop](../../../docs/framework/windows-workflow-foundation/1102-workflowactivitystop.md)|정보|WorkflowInstance Id: '%1' E2E 작업|WFRuntime|  
|[1103 - WorkflowActivitySuspend](../../../docs/framework/windows-workflow-foundation/1103-workflowactivitysuspend.md)|정보|WorkflowInstance Id: '%1' E2E 작업|WFRuntime|  
|[1104 - WorkflowActivityResume](../../../docs/framework/windows-workflow-foundation/1104-workflowactivityresume.md)|정보|WorkflowInstance Id: '%1' E2E 작업|WFRuntime|  
|[1124 - InvokeMethodIsStatic](../../../docs/framework/windows-workflow-foundation/1124-invokemethodisstatic.md)|정보|InvokeMethod '%1' - 메서드가 Static입니다.|WFRuntime|  
|[1125 - InvokeMethodIsNotStatic](../../../docs/framework/windows-workflow-foundation/1125-invokemethodisnotstatic.md)|정보|InvokeMethod ''%1' - 메서드가 Static이 아닙니다.|WFRuntime|  
|[1126 - InvokedMethodThrewException](../../../docs/framework/windows-workflow-foundation/1126-invokedmethodthrewexception.md)|정보|작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다. %2|WFRuntime|  
|[1131 - InvokeMethodUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1131-invokemethoduseasyncpattern.md)|정보|InvokeMethod '%1'' - 메서드에서 ''%2' 및 '%3'의 비동기 패턴을 사용합니다.|WFRuntime|  
|[1132 - InvokeMethodDoesNotUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1132-invokemethoddoesnotuseasyncpattern.md)|정보|InvokeMethod '%1' - 메서드에서 비동기 패턴을 사용하지 않습니다.|WFRuntime|  
|[1140 - FlowchartStart](../../../docs/framework/windows-workflow-foundation/1140-flowchartstart.md)|정보|Flowchart '%1' - 시작이 예약되었습니다.|WFActivities|  
|[1141 - FlowchartEmpty](../../../docs/framework/windows-workflow-foundation/1141-flowchartempty.md)|경고|Flowchart '%1' - 노드 없이 실행되었습니다. 작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다. %2|WFActivities|  
|[1143 - FlowchartNextNull](../../../docs/framework/windows-workflow-foundation/1143-flowchartnextnull.md)|정보|Flowchart '%1'/FlowStep - 다음 노드가 null입니다. Flowchart 실행이 종료됩니다.|WFActivities|  
|[1146 - FlowchartSwitchCase](../../../docs/framework/windows-workflow-foundation/1146-flowchartswitchcase.md)|정보|Flowchart '%1'/FlowSwitch - Case '%2'을(를) 선택했습니다.|WFActivities|  
|[1147 - FlowchartSwitchDefault](../../../docs/framework/windows-workflow-foundation/1147-flowchartswitchdefault.md)|정보|Flowchart '%1'/FlowSwitch - Default Case를 선택했습니다.|WFActivities|  
|[1148 - FlowchartSwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1148-flowchartswitchcasenotfound.md)|정보|Flowchart '%1'/FlowSwitch - Expression 결과와 일치하는 Case 작업 및 Default Case를 찾을 수 없습니다. Flowchart 실행이 종료됩니다.|WFActivities|  
|[1150 - CompensationState](../../../docs/framework/windows-workflow-foundation/1150-compensationstate.md)|정보|CompensableActivity '%1'은(는) '%2' 상태입니다.|WFActivities|  
|[1223 - SwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1223-switchcasenotfound.md)|정보|Switch 작업 '%1'에서 Expression 결과와 일치하는 Case 작업을 찾을 수 없습니다.|WFActivities|  
|[1449 - WfMessageReceived](../../../docs/framework/windows-workflow-foundation/1449-wfmessagereceived.md)|정보|워크플로가 메시지를 수신함|WFServices|  
|[1450 - WfMessageSent](../../../docs/framework/windows-workflow-foundation/1450-wfmessagesent.md)|정보|워크플로에서 메시지가 전송됨|WFServices|  
|[2021 - ExecuteWorkItemStart](../../../docs/framework/windows-workflow-foundation/2021-executeworkitemstart.md)|자세히|작업 항목 실행 시작|WFRuntime|  
|[2022 - ExecuteWorkItemStop](../../../docs/framework/windows-workflow-foundation/2022-executeworkitemstop.md)|자세히|작업 항목 실행 중지|WFRuntime|  
|[2023 - SendMessageChannelCacheMiss](../../../docs/framework/windows-workflow-foundation/2023-sendmessagechannelcachemiss.md)|자세히|SendMessageChannelCache 누락|WFRuntime|  
|[2024 - InternalCacheMetadataStart](../../../docs/framework/windows-workflow-foundation/2024-internalcachemetadatastart.md)|자세히|InternalCacheMetadata가 작업 '%1'에서 시작되었습니다.|WFRuntime|  
|[2025 - InternalCacheMetadataStop](../../../docs/framework/windows-workflow-foundation/2025-internalcachemetadatastop.md)|자세히|InternalCacheMetadata가 작업 '%1'에서 중지되었습니다.|WFRuntime|  
|[2026 - CompileVbExpressionStart](../../../docs/framework/windows-workflow-foundation/2026-compilevbexpressionstart.md)|자세히|VB 식 '%1' 컴파일 중|WFRuntime|  
|[2027 - CacheRootMetadataStart](../../../docs/framework/windows-workflow-foundation/2027-cacherootmetadatastart.md)|자세히|CacheRootMetadata가 작업 '%1'에서 시작되었습니다.|WFRuntime|  
|[2028 - CacheRootMetadataStop](../../../docs/framework/windows-workflow-foundation/2028-cacherootmetadatastop.md)|자세히|CacheRootMetadata가 작업 '%1'에서 중지되었습니다.|WFRuntime|  
|[2029 - CompileVbExpressionStop](../../../docs/framework/windows-workflow-foundation/2029-compilevbexpressionstop.md)|자세히|VB 식 컴파일이 완료되었습니다.|WFRuntime|  
|[2576 - TryCatchExceptionFromTry](../../../docs/framework/windows-workflow-foundation/2576-trycatchexceptionfromtry.md)|정보|TryCatch 작업 '%1'에서 '%2' 형식의 예외를 catch했습니다.|WFActivities|  
|[2577 - TryCatchExceptionDuringCancelation](../../../docs/framework/windows-workflow-foundation/2577-trycatchexceptionduringcancelation.md)|경고|취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.|WFActivities|  
|[2578 - TryCatchExceptionFromCatchOrFinally](../../../docs/framework/windows-workflow-foundation/2578-trycatchexceptionfromcatchorfinally.md)|경고|TryCatch 작업 '%1'에 연결된 Catch 또는 Finally 작업에서 예외가 throw되었습니다.|WFActivities|  
|[3501 - InferredContractDescription](../../../docs/framework/windows-workflow-foundation/3501-inferredcontractdescription.md)|정보|Name='%1'이고 Namespace='%2'인 ContractDescription이 WorkflowService에서 유추되었습니다.|WFServices|  
|[3502 - InferredOperationDescription](../../../docs/framework/windows-workflow-foundation/3502-inferredoperationdescription.md)|정보|계약 '%2'에서 Name='%1'인 OperationDescription이 WorkflowService에서 유추되었습니다. IsOneWay=%3.|WFServices|  
|[3503 - DuplicateCorrelationQuery](../../../docs/framework/windows-workflow-foundation/3503-duplicatecorrelationquery.md)|경고|Where='%1'인 중복 CorrelationQuery가 있습니다. 이 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.|WFServices|  
|[3507 - ServiceEndpointAdded](../../../docs/framework/windows-workflow-foundation/3507-serviceendpointadded.md)|정보|주소 '%1', 바인딩 '%2' 및 계약 '%3'에 대해 서비스 끝점이 추가되었습니다.|WFServices|  
|[3508 - TrackingProfileNotFound](../../../docs/framework/windows-workflow-foundation/3508-trackingprofilenotfound.md)|자세히|ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다. 구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.|WFServices|  
|[3550 - BufferOutOfOrderMessageNoInstance](../../../docs/framework/windows-workflow-foundation/3550-bufferoutofordermessagenoinstance.md)|정보|현재는 '%1' 작업을 수행할 수 없습니다. 서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.|WFServices|  
|[3551 - BufferOutOfOrderMessageNoBookmark](../../../docs/framework/windows-workflow-foundation/3551-bufferoutofordermessagenobookmark.md)|정보|현재는 서비스 인스턴스 '%1'에서 '%2' 작업을 수행할 수 없습니다. 서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.|WFServices|  
|[3552 - MaxPendingMessagesPerChannelExceeded](../../../docs/framework/windows-workflow-foundation/3552-maxpendingmessagesperchannelexceeded.md)|경고|스로틀 ' maxpendingmessagesperchannel ' '%1'에 도달 했습니다. 이 한도를 늘리려면 BufferedReceiveServiceBehavior에서 MaxPendingMessagesPerChannel 속성을 조정하세요.|할당량 WFServices|  
|[3557 - TransactedReceiveScopeEndCommitFailed](../../../docs/framework/windows-workflow-foundation/3557-transactedreceivescopeendcommitfailed.md)|정보|ID = '%1'인 CommittableTransaction에 대한 EndCommit 호출에서 다음 메시지와 함께 TransactionException이 발생했습니다. '%2'.|WFServices|  
|[4201 - EndSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4201-endsqlcommandexecute.md)|자세히|SQL 명령 실행 종료: %1|WFInstanceStore|  
|[4202 - StartSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4202-startsqlcommandexecute.md)|자세히|SQL 명령 실행 시작: %1|WFInstanceStore|  
|[4203 - RenewLockSystemError](../../../docs/framework/windows-workflow-foundation/4203-renewlocksystemerror.md)|오류|잠금 만료를 연장하지 못했습니다. 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었습니다. SqlWorkflowInstanceStore를 중단하는 중입니다.|WFInstanceStore|  
|[4205 - FoundProcessingError](../../../docs/framework/windows-workflow-foundation/4205-foundprocessingerror.md)|오류|명령 실패: %1|WFInstanceStore|  
|[4206 - UnlockInstanceException](../../../docs/framework/windows-workflow-foundation/4206-unlockinstanceexception.md)|오류|인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.|WFInstanceStore|  
|[4207 - MaximumRetriesExceededForSqlCommand](../../../docs/framework/windows-workflow-foundation/4207-maximumretriesexceededforsqlcommand.md)|정보|최대 재시도 횟수를 초과하여 SQL 명령 재시도를 중단합니다.|할당량 WFInstanceStore|  
|[4208 - RetryingSqlCommandDueToSqlError](../../../docs/framework/windows-workflow-foundation/4208-retryingsqlcommandduetosqlerror.md)|정보|SQL 오류 %1번으로 인해 SQL 명령을 재시도합니다.|WFInstanceStore|  
|[4209 - TimeoutOpeningSqlConnection](../../../docs/framework/windows-workflow-foundation/4209-timeoutopeningsqlconnection.md)|오류|SQL 연결을 열려는 중 시간이 초과했습니다. 할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다. 이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.|WFInstanceStore|  
|[4210 - SqlExceptionCaught](../../../docs/framework/windows-workflow-foundation/4210-sqlexceptioncaught.md)|경고|SQL 예외 %1번 메시지 %2을(를) catch했습니다.|WFInstanceStore|  
|[4211 - QueuingSqlRetry](../../../docs/framework/windows-workflow-foundation/4211-queuingsqlretry.md)|경고|%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.|WFInstanceStore|  
|[4212 - LockRetryTimeout](../../../docs/framework/windows-workflow-foundation/4212-lockretrytimeout.md)|경고|인스턴스 잠금을 얻으려는 중 시간이 초과 되었습니다.  할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다. 이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.|WFInstanceStore|  
|[4213 - RunnableInstancesDetectionError](../../../docs/framework/windows-workflow-foundation/4213-runnableinstancesdetectionerror.md)|오류|다음 예외로 인해 실행 가능한 인스턴스를 검색하지 못했습니다.|WFInstanceStore|  
|[4214 - InstanceLocksRecoveryError](../../../docs/framework/windows-workflow-foundation/4214-instancelocksrecoveryerror.md)|오류|다음 예외로 인해 인스턴스 잠금을 복구하지 못했습니다.|WFInstanceStore|  
|[39456 - TrackingRecordDropped](../../../docs/framework/windows-workflow-foundation/39456-trackingrecorddropped.md)|경고|추적 레코드 %1의 크기가 %2 공급자의 ETW 세션에서 허용된 최대값을 초과합니다.|WFTracking|  
|[39457 - TrackingRecordRaised](../../../docs/framework/windows-workflow-foundation/39457-trackingrecordraised.md)|정보|추적 레코드 %1이(가) %2(으)로 증가했습니다.|WFRuntime|  
|[39458 - TrackingRecordTruncated](../../../docs/framework/windows-workflow-foundation/39458-trackingrecordtruncated.md)|경고|잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다. 변수/주석/사용자 데이터가 제거되었습니다.|WFTracking|  
|[39459 - TrackingDataExtracted](../../../docs/framework/windows-workflow-foundation/39459-trackingdataextracted.md)|자세히|추적 데이터 %1이(가) %2 작업에서 추출되었습니다.|WFRuntime|  
|[39460 - TrackingValueNotSerializable](../../../docs/framework/windows-workflow-foundation/39460-trackingvaluenotserializable.md)|경고|추출된 인수/변수 '%1'은(는) serialize할 수 없습니다.|WFTracking|  
|[57398 - MaxInstancesExceeded](../../../docs/framework/windows-workflow-foundation/57398-maxinstancesexceeded.md)|경고|시스템이 'MaxConcurrentInstances' 스로틀에 대해 설정된 한계에 도달했습니다. 이 스로틀에 대한 제한은 %1(으)로 설정되었습니다. serviceThrottle 요소에서 'maxConcurrentInstances' 특성을 수정하거나 ServiceThrottlingBehavior 동작에서 'MaxConcurrentInstances' 속성을 수정하여 스로틀 값을 변경할 수 있습니다.|WFServices|
