---
title: "트랜잭션 기본 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 353f4ee2-e6bf-4b1c-b1c8-385fc8a486c0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa26531b1d2573b4bef49ec93f4205716227e25b
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="transaction-fundamentals"></a>트랜잭션 기본 사항
트랜잭션은 여러 작업을 함께 바인딩합니다. 예를 들어 응용 프로그램이 두 가지 작업을 수행한다고 가정합니다. 먼저 데이터베이스에 새 테이블을 만듭니다. 그런 다음 특수 개체를 호출하여 데이터를 수집하고 형식을 지정하여 새 테이블에 삽입합니다. 데이터를 채울 수 없는 경우 새 테이블을 만들지 않으려고 한다는 점에서 두 작업은 서로 관련이 있고 상호 종속적입니다. 단일 트랜잭션 범위 내에서 두 작업을 실행하면 두 작업 간의 연결이 적용됩니다. 두 번째 작업이 실패하면 첫 번째 작업이 새 테이블을 만들기 전의 지점으로 롤백됩니다.  
  
 예측 가능한 동작을 유지하려면 모든 트랜잭션이 기본 ACID 속성(원자성, 일관성, 격리성 및 지속성)을 보유해야 합니다. 이러한 속성은 전체가 아니면 하나도 아님(all-or-none) 명제로 업무상 중요한 트랜잭션의 역할을 강조합니다. ACID에 대 한 자세한 내용은 참조 하십시오 [ACID 속성](http://go.microsoft.com/fwlink/?LinkId=98791)합니다. 요약하면 ACID는 관련된 작업 집합이 하나의 단위로 성공하거나 실패하도록 합니다. 트랜잭션 처리 용어로는 트랜잭션이 커밋되거나 중단됩니다. 트랜잭션이 커밋되려면 모든 참가자가 데이터 변경 내용이 영구적임을 보장해야 합니다. 시스템 작동이 중단되거나 다른 예측할 수 없는 이벤트가 발생해도 변경 내용이 지속되어야 합니다. 이를 보장하지 않는 참가자가 하나라도 있으면 전체 트랜잭션이 실패합니다. 트랜잭션 범위 내의 모든 데이터 변경 내용이 설정된 특정 지점으로 롤백됩니다.  
  
 트랜잭션을 데이터베이스 또는 메시지 큐 같은 하나의 데이터 리소스로 제한할 수 있습니다. 이 시나리오에서는 <xref:System.Transactions>에서 제공하는 트랜잭션 관리자가 로컬 트랜잭션을 관리하므로 성능이 향상됩니다. 데이터 리소스에 의해 제어되는 이러한 트랜잭션은 쉽고 효율적으로 관리할 수 있습니다.  
  
 트랜잭션이 여러 데이터 리소스에 걸쳐 있을 수도 있습니다. 분산 트랜잭션은 여러 시스템에서 발생하는 여러 개의 고유한 작업을 하나의 성공 또는 실패 작업으로 통합하는 기능을 제공합니다. 이 시나리오에서는 각 시스템에 있는 MSDTC(Microsoft Distributed Transaction Coordinator)가 트랜잭션을 조정합니다.  
  
 <xref:System.Transactions>에서 제공하는 클래스를 사용하여 트랜잭션 응용 프로그램을 개발하는 경우 필요한 트랜잭션 종류나 관련된 트랜잭션 관리자에 대해 염려할 필요가 없습니다. <xref:System.Transactions> 인프라가 자동으로 이를 관리합니다.  
  
 트랜잭션을 만들 때 트랜잭션에 적용되는 격리 수준을 지정할 수 있습니다. 에 정의 된 격리 수준인은 <xref:System.Transactions.IsolationLevel> 열거형 다른 트랜잭션에서 데이터에 영향을 주었을 사용자의 트랜잭션에서 액세스 수준을 결정 합니다.  
  
 ADO.NET을 사용 하 여 트랜잭션을 만들 수 있습니다 <xref:System.EnterpriseServices>, 또는에서 제공 하는 트랜잭션 프로그래밍 모델은 <xref:System.Transactions> 네임 스페이스입니다. [System.Transactions에 의해 제공 하는 기능](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md) 사용 하 여 트랜잭션 응용 프로그램을 작성 하는 데 사용할 수 있는 기능을 알아봅니다는 <xref:System.Transactions> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [System.Transactions에서 제공하는 기능](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)
