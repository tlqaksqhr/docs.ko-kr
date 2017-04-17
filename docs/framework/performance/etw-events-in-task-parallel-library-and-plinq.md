---
title: "작업 병렬 라이브러리 및 PLINQ의 ETW 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "작업, ETW 이벤트"
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 작업 병렬 라이브러리 및 PLINQ의 ETW 이벤트
작업 병렬 라이브러리 및 PLINQ는 Windows Performance Analyzer 같은 도구로 응용 프로그램을 프로파일링하고 문제를 해결하는 데 사용할 수 있는 ETW\(Windows용 이벤트 추적\) 이벤트를 생성합니다.  그러나 대부분의 시나리오에서 병렬 응용 프로그램 코드를 프로파일링하는 최상의 방법은 [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)]에서 [동시성 시각화 도우미](../Topic/Concurrency%20Visualizer.md)를 사용하는 것입니다.  
  
## 작업 병렬 라이브러리 ETW 이벤트  
 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName>에서 생성하는 이벤트에 대한 EVENT\_HEADER 구조체의 ProviderId GUID는 다음과 같습니다.  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### 병렬 루프 시작  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### 사용자 데이터  
  
|**Name**|**형식**|**설명**|  
|--------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 TaskScheduler의 ID입니다.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 작업의 ID입니다.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|분기\/조인 의미 체계를 사용하여 이벤트의 중첩과 쌍을 나타내는 데 사용되는 고유 식별자입니다.|  
|OperationType|<xref:System.Int32?displayProperty=fullName>|루프 형식을 나타냅니다.<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|InclusiveFrom|<xref:System.Int64?displayProperty=fullName>|루프 카운터의 시작 값입니다.|  
|ExclusiveTo|<xref:System.Int64?displayProperty=fullName>|루프 카운터의 끝 값입니다.|  
  
### 병렬 루프 끝  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### 사용자 데이터  
  
|**Name**|**형식**|**설명**|  
|--------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 TaskScheduler의 ID입니다.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 작업의 ID입니다.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|분기\/조인 의미 체계를 사용하여 이벤트의 중첩과 쌍을 나타내는 데 사용되는 고유 식별자입니다.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|총 반복 수입니다.|  
  
### 병렬 호출 시작  
 EVENT\_DESCRIPTOR.Task \= 3  
  
 EVENT\_DESCRIPTOR.Id \= 3  
  
#### 사용자 데이터  
  
|**Name**|**형식**|**설명**|  
|--------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 TaskScheduler의 ID입니다.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 작업의 ID입니다.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|분기\/조인 의미 체계를 사용하여 이벤트의 중첩과 쌍을 나타내는 데 사용되는 고유 식별자입니다.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|총 반복 수입니다.|  
|operationType|<xref:System.Int32?displayProperty=fullName>|루프 형식을 나타냅니다.<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|ActionCount|<xref:System.Int32?displayProperty=fullName>|병렬 호출에서 실행될 작업의 수입니다.|  
  
### 병렬 호출 끝  
 EVENT\_DESCRIPTOR.Task \= 4  
  
 EVENT\_DESCRIPTOR.Id \= 4  
  
#### 사용자 데이터  
  
|**Name**|**형식**|**설명**|  
|--------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 TaskScheduler의 ID입니다.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 작업의 ID입니다.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|분기\/조인 의미 체계를 사용하여 이벤트의 중첩과 쌍을 나타내는 데 사용되는 고유 식별자입니다.|  
  
## PLINQ ETW 이벤트  
 PLINQ에 대한 EVENT\_HEADER.ProviderId GUID는 다음과 같습니다.  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### 병렬 쿼리 시작  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### 사용자 데이터  
  
|**Name**|**형식**|**설명**|  
|--------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 TaskScheduler의 ID입니다.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 작업의 ID입니다.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|고유 쿼리 식별자입니다.|  
  
### 병렬 쿼리 끝  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### 사용자 데이터  
  
|**Name**|**형식**|**설명**|  
|--------------|------------|------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 TaskScheduler의 ID입니다.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|루프를 시작한 작업의 ID입니다.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|고유 쿼리 식별자입니다.|  
  
## 참고 항목  
 [.NET Framework의 ETW 이벤트](../../../docs/framework/performance/etw-events.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)