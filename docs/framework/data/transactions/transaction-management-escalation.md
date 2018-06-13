---
title: 트랜잭션 관리 에스컬레이션
ms.date: 03/30/2017
ms.assetid: 1e96331e-31b6-4272-bbbd-29ed1e110460
ms.openlocfilehash: 2a5592cc9ebf0ddfc49f38da9404c81d11a29cf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356861"
---
# <a name="transaction-management-escalation"></a>트랜잭션 관리 에스컬레이션
Windows는 트랜잭션 관리자를 구성하는 서비스 및 모듈 집합을 호스팅합니다. 트랜잭션 관리 에스컬레이션은 트랜잭션 관리자의 구성 요소 중 하나에서 다른 구성 요소로 트랜잭션을 마이그레이션하는 프로세스에 대해 설명합니다.  
  
 <xref:System.Transactions>에는 하나 이하의 지속적인 리소스나 여러 개의 일시적인 리소스와 관련된 트랜잭션을 조정하는 트랜잭션 관리자 구성 요소가 있습니다. 트랜잭션 관리자는 워크플로 인스턴스 간 도메인 호출만 사용하므로 최상의 성능을 제공합니다. 개발자가 직접 트랜잭션 관리자와 상호 작용할 필요는 없습니다. 대신 인터페이스, 일반 동작 및 도우미 클래스를 정의하는 공통 인프라가 <xref:System.Transactions> 네임스페이스에 의해 제공됩니다.  
  
 동일한 컴퓨터에서 트랜잭션 (프로세스 및 컴퓨터 경계를 넘어 포함) 다른 응용 프로그램 도메인에 있는 개체를 제공 하려는 경우는 <xref:System.Transactions> 인프라에는 자동으로 Microsoft에서 관리 되는 트랜잭션 에스컬레이션 Distributed Transaction Coordinator (MSDTC). 다른 지속적인 리소스 관리자를 참여시키는 경우에도 에스컬레이션이 발생합니다. 에스컬레이션되면 트랜잭션이 완료될 때까지 높은 권한 상태에서 관리됩니다.  
  
 <xref:System.Transactions> 트랜잭션과 MSDTC 트랜잭션 사이에는 PSPE(승격 가능한 단일 단계 인리스트먼트)를 통해 사용할 수 있는 중간 형식의 트랜잭션이 있습니다. PSPE는 성능을 최적화하기 위한 <xref:System.Transactions>의 다른 중요한 메커니즘입니다. PSPE를 사용하면 다른 응용 프로그램 도메인, 프로세스 또는 컴퓨터에 있는 지속적인 원격 리소스가 MSDTC 트랜잭션으로 에스컬레이션되지 않고도 <xref:System.Transactions> 트랜잭션에 참여할 수 있습니다. PSPE에 대 한 자세한 내용은 참조 [트랜잭션에서 참가자 인 리스트 먼 트 리소스](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)합니다.  
  
## <a name="how-escalation-is-initiated"></a>에스컬레이션 시작 방법  
 MSDTC는 별도 프로세스에 있고 트랜잭션을 MSDTC로 에스컬레이션하는 경우 메시지가 프로세스 간에 전송되므로 트랜잭션 에스컬레이션을 사용하면 성능이 저하됩니다. 성능을 개선 하기 위해 지연 하거나 에스컬레이션 MSDTC;을 방지 해야 따라서 에스컬레이션 시작 되는 방법과 시기에 대해 알아야 할 수도 있습니다.  
  
 <xref:System.Transactions> 인프라에서 임시적인 리소스와 단일 단계 알림을 지원하는 하나 이하의 지속적인 리소스를 처리하는 한 트랜잭션은 <xref:System.Transactions> 인프라의 소유로 유지됩니다. 트랜잭션 관리자는 동일한 응용 프로그램 도메인에 있고 로깅(트랜잭션 출력을 디스크에 쓰는 작업)이 필요하지 않은 리소스에만 사용할 수 있습니다. <xref:System.Transactions> 인프라가 트랜잭션 소유권을 MSDTC로 넘기게 되는 에스컬레이션은 다음과 같은 경우에 발생합니다.  
  
-   단일 단계 알림을 지원하지 않는 지속적인 리소스가 하나 이상 트랜잭션에 참여하는 경우  
  
-   단일 단계 알림을 지원하는 지속적인 리소스가 두 개 이상 트랜잭션에 참여하는 경우. 예를 들어 [!INCLUDE[sqprsqlong](../../../../includes/sqprsqlong-md.md)]와의 단일 연결을 참여시키면 트랜잭션이 승격되지 않습니다. 그러나 [!INCLUDE[sqprsqlong](../../../../includes/sqprsqlong-md.md)] 데이터베이스에 대한 두 번째 연결을 열어 데이터베이스에서 참여시킬 때마다 <xref:System.Transactions> 인프라는 이를 트랜잭션의 두 번째 지속적인 리소스로 감지하고 MSDTC 트랜잭션으로 에스컬레이션합니다.  
  
-   트랜잭션을 다른 응용 프로그램 도메인이나 다른 프로세스로 "마샬링"하는 요청이 호출됩니다. 예를 들어 응용 프로그램 도메인 경계를 넘어 트랜잭션 개체가 serialize됩니다. 트랜잭션 개체는 값으로 마샬링되므로 동일한 프로세스인 경우에도 응용 프로그램 도메인 경계를 넘어 전달하려고 하면 트랜잭션 개체의 serialization이 발생합니다. <xref:System.Transactions.Transaction>을 매개 변수로 사용하는 원격 메서드를 호출하여 트랜잭션 개체를 전달하거나 트랜잭션에서 처리된 구성 요소에 액세스할 수 있습니다. 이 경우 트랜잭션 개체가 serialize되어 트랜잭션이 응용 프로그램 도메인에서 serialize될 때와 마찬가지로 에스컬레이션이 발생합니다. 트랜잭션 개체가 분산되어 로컬 트랜잭션 관리자가 더 이상 적합하지 않습니다.  
  
 다음 표에서는 에스컬레이션 중에 throw될 수 있는 모든 가능한 예외를 보여 줍니다.  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Transactions.IsolationLevel.Snapshot>과 동일한 격리 수준으로 트랜잭션을 에스컬레이션하려는 경우입니다.|  
|<xref:System.Transactions.TransactionAbortedException>|트랜잭션 관리자가 다운된 경우입니다.|  
|<xref:System.Transactions.TransactionException>|에스컬레이션이 실패하고 응용 프로그램이 중단된 경우입니다.|
