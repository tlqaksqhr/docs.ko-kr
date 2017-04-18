---
title: "Scheduling Threads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], scheduling"
  - "scheduling threads"
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Scheduling Threads
각 스레드에는 스레드 우선 순위가 지정됩니다.  공용 언어 런타임 내에서 만들어진 스레드에는 처음에는 **ThreadPriority.Normal**의 우선 순위가 할당됩니다.  런타임 외부에서 만들어진 스레드는 관리되는 환경에 들어오기 전의 우선 순위를 그대로 유지합니다.  **Thread.Priority** 속성을 사용하여 스레드의 우선 순위를 가져오거나 설정할 수 있습니다.  
  
 스레드는 우선 순위에 따라 실행 일정이 잡힙니다.  스레드가 런타임 내에서 실행 중이더라도 운영 체제에서 모든 스레드에 프로세서 시간 간격을 할당합니다.  스레드가 실행되는 순서를 지정할 때 사용되는 스케줄링 알고리즘의 세부 항목은 운영 체제에 따라 달라집니다.  일부 운영 체제에서는 실행될 스레드 중 우선 순위가 가장 높은 스레드가 가장 먼저 실행됩니다.  우선 순위가 동일한 여러 스레드가 모두 사용 가능할 경우 스케줄러에서 해당 스레드를 순환하면서 각 스레드가 실행될 고정 시간 간격을 부여합니다.  우선 순위가 높은 스레드가 실행 가능한 동안에는 우선 순위가 낮은 스레드는 실행되지 못합니다.  특정 우선 순위에서 실행 가능한 스레드가 더 이상 없으면 스케줄러는 다음으로 낮은 우선 순위로 이동하여 해당 스레드를 실행하도록 일정을 설정합니다.  우선 순위가 높은 스레드가 실행 가능해지면 우선 순위가 낮은 스레드는 선점되고 우선 순위가 높은 스레드가 다시 한 번 실행됩니다.  무엇보다 응용 프로그램 사용자 인터페이스가 포그라운드와 백그라운드 간에 이동될 경우 운영 체제에서 스레드 우선 순위를 동적으로 조정할 수 있습니다.  운영 체제에 따라 다른 스케줄링 알고리즘을 사용할 수도 있습니다.  
  
## 참고 항목  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)