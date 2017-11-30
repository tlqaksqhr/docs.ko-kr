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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a>관리되는 스레딩 기본 사항
이 섹션의 처음 5 개 항목은 관리 되는 스레딩을 사용 하 고 몇 가지 기본 기능을 설명 하는 경우를 결정할 수 있도록 디자인 되었습니다. 참조 추가 기능을 제공 하는 클래스에 대 한 내용은 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md) 및 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)합니다.  
  
 이 섹션의 검사 항목의 나머지 부분 고급 항목, 관리 되는 스레딩 Windows 운영 체제와의 상호 작용을 포함 하 여 합니다.  
  
> [!NOTE]
>  에 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 작업 병렬 라이브러리 및 PLINQ 다중 스레드 프로그램의 작업 및 데이터 병렬 처리에 대 한 Api를 제공 합니다. 자세한 내용은 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)을 참조하세요.  
  
## <a name="in-this-section"></a>단원 내용  
 [스레드 및 스레딩](../../../docs/standard/threading/threads-and-threading.md)  
 다중 스레드 장단점에 대해 설명 하 고 스레드를 만들 하거나 스레드 풀 스레드를 사용할 수 있는 시나리오를 간략하게 설명 합니다.  
  
 [관리되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 동작에 설명 다른 버전의.NET Framework에 대 한 스레드에서 처리 되지 않은 예외의 특히 있는 상황에서 응용 프로그램의 종료에서 될 있습니다.  
  
 [다중 스레딩을 위한 데이터 동기화](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 여러 스레드에서 사용할 수 있는 클래스의에서 데이터를 동기화 하기 위한 전략을 설명 합니다.  
  
 [관리되는 스레드 상태](../../../docs/standard/threading/managed-thread-states.md)  
 기본 스레드 상태를 설명 하 고는 스레드가 실행 되 고 있는지 여부를 검색 하는 방법에 설명 합니다.  
  
 [포그라운드 및 백그라운드 스레드](../../../docs/standard/threading/foreground-and-background-threads.md)  
 포그라운드 및 백그라운드 스레드 간의 차이점에 설명 합니다.  
  
 [Windows에서 관리되는 스레딩 및 관리되지 않는 스레딩](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 관리 되는 관리 되지 않는 스레드 간의 관계를 설명, 스레딩 Api, Windows에 대 한 관리 되는 해당 항목을 나열 하 고 관리 되는 스레드 및 COM 아파트와의 상호 작용을 설명 합니다.  
  
 [Thread.Suspend, 가비지 컬렉션, 안전한 시점](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 스레드 일시 중단 및 가비지 컬렉션에 설명합니다.  
  
 [스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 스레드 관련 저장 메커니즘을 설명합니다.  
  
 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 어떻게 비동기 또는 장기 실행 동기 작업에 설명 취소 토큰을 사용 하 여 취소할 수 있습니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Threading.Thread>  
 비관리 코드에서 가져왔는지 또는 관리되는 응용 프로그램에서 만들어졌는지에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 구현 하는 안전한 방법을 제공 된 사용자 인터페이스 개체에에서 다중 스레딩을 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 다중 스레드 작업을 동기화 하는 데 사용 하는 관리 되는 클래스를 설명 합니다.  
  
 [관리되는 스레딩을 구현하는 최선의 방법](../../../docs/standard/threading/managed-threading-best-practices.md)  
 관련 된 일반적인 문제에 설명 다중 스레딩 및 문제를 방지 하기 위한 전략입니다.  
  
 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)  
 비동기 및 다중 스레드.NET Framework 응용 프로그램을 만드는 작업을 크게 간소화 작업 병렬 라이브러리 및 PLINQ에 설명 합니다.
