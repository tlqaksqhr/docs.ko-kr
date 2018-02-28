---
title: "관리되는 스레딩 기본 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 035834959aa5f9340727327b22cae93b3f21b056
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="managed-threading-basics"></a>관리되는 스레딩 기본 사항
이 섹션의 첫 5개 항목은 관리되는 스레딩을 사용하는 시기를 결정하도록 돕고 몇 가지 기본 기능을 설명하도록 설계되었습니다. 추가 기능을 제공하는 클래스에 대한 내용은 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md) 및 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하세요.  
  
 이 섹션의 나머지 항목에서는 Windows 운영 체제와 관리되는 스레딩의 상호 작용을 비롯한 고급 주제를 다룹니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 작업 병렬 라이브러리 및 PLINQ는 다중 스레드 프로그램에서 작업 및 데이터 병렬 처리를 위한 API를 제공합니다. 자세한 내용은 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)을 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [스레드 및 스레딩](../../../docs/standard/threading/threads-and-threading.md)  
 다중 스레드의 장단점에 대해 설명하고 스레드를 만들거나 스레드 풀 스레드를 사용할 수 있는 시나리오를 간략하게 설명합니다.  
  
 [관리되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 .NET Framework의 여러 버전에 대해 스레드의 처리되지 않은 예외의 동작(특히 응용 프로그램 종료를 발생시키는 상황에서)에 대해 설명합니다.  
  
 [다중 스레딩을 위한 데이터 동기화](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 다중 스레드에서 사용할 클래스의 데이터를 동기화하기 위한 전략에 대해 설명합니다.  
  
 [관리되는 스레드 상태](../../../docs/standard/threading/managed-thread-states.md)  
 기본 스레드 상태를 설명하고 스레드가 실행 중인지 여부를 감지하는 방법에 대해 설명합니다.  
  
 [포그라운드 및 백그라운드 스레드](../../../docs/standard/threading/foreground-and-background-threads.md)  
 포그라운드 스레드와 백그라운드 스레드 간의 차이점에 대해 설명합니다.  
  
 [Windows에서 관리되는 스레딩 및 관리되지 않는 스레딩](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 관리되는 스레딩과 관리되지 않는 스레딩, 간의 관계에 대해 설명하고, Windows 스레딩 API에 대해 관리되는 스레딩을 나열하고, COM 아파트 및 관리되는 스레드의 상호 작용에 대해 설명합니다.  
  
 [Thread.Suspend, 가비지 수집, 안전한 시점](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 스레드 일시중단 및 가비지 수집에 대해 설명합니다.  
  
 [스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 스레드 관련 저장소 메커니즘을 설명합니다.  
  
 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 취소 토큰을 사용하여 비동기 또는 장기 실행 동기 작업을 취소할 수 있는 방법에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Threading.Thread>  
 비관리 코드에서 가져왔는지 또는 관리되는 응용 프로그램에서 만들어졌는지에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 사용자 인터페이스 개체와 함께 다중 스레딩을 구현할 수 있는 안전한 방법을 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 다중 스레드의 활동을 동기화하는 데 사용되는 관리되는 클래스에 대해 설명합니다.  
  
 [관리되는 스레딩을 구현하는 최선의 방법](../../../docs/standard/threading/managed-threading-best-practices.md)  
 문제를 피할 수 있도록 다중 스레딩 및 전략에 대한 일반적인 문제를 설명합니다.  
  
 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)  
 비동기 및 다중 스레드 .NET Framework 응용 프로그램을 만드는 작업을 크게 간소화하는 작업 병렬 라이브러리 및 PLINQ에 대해 설명합니다.
