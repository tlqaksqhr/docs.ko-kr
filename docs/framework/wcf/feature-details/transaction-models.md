---
title: 트랜잭션 모델
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-models"></a>트랜잭션 모델
이 항목에서는 트랜잭션 프로그래밍 모델 및 Microsoft가 제공하는 인프라 구성 요소 간의 관계에 대해 설명합니다.  
  
 Windows Communication Foundation (WCF)에서 트랜잭션을 사용 하 여에 이해는 서로 다른 트랜잭션 모델 사이 선택 하지 않고 통합 되 고 일관 된 모델의 다른 계층에서 작동 해야 합니다.  
  
 다음 단원에서는 세 가지 기본 트랜잭션 구성 요소에 대해 설명합니다.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation 트랜잭션  
 WCF에서 트랜잭션 지원 트랜잭션 서비스를 작성할 수 있습니다. 또한에 Ws-atomictransaction (WS-AT) 프로토콜에 대 한 지원을 통해 응용 프로그램에는 WCF 또는 타사 기술 중 하나를 사용 하 여 빌드된 웹 서비스에 트랜잭션을 전달할 수 있습니다.  
  
 WCF 서비스 또는 응용 프로그램에서 WCF 트랜잭션 기능은 특성 및 방법 및 시기는 인프라, 흐름를 만들고 트랜잭션을 동기화을 선언적으로 지정 하는 것에 대 한 구성을 제공 합니다.  
  
## <a name="systemtransactions-transactions"></a>System.Transactions 트랜잭션  
 <xref:System.Transactions> 네임스페이스는 <xref:System.Transactions.Transaction> 클래스 기반의 명시적 프로그래밍 모델과 <xref:System.Transactions.TransactionScope> 클래스를 사용하는 암시적 프로그래밍 모델을 모두 제공합니다. 후자의 경우 인프라에서 자동으로 트랜잭션을 관리합니다.  
  
 이러한 두 가지 모델을 사용 하 여 트랜잭션 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 [트랜잭션 응용 프로그램을 작성](http://go.microsoft.com/fwlink/?LinkId=94947)합니다.  
  
 WCF 서비스 또는 응용 프로그램, <xref:System.Transactions> 클라이언트 응용 프로그램 내에서 트랜잭션을 만들고 하 고 명시적으로 필요한 경우 서비스 내에서 트랜잭션 상호 작용 하기 위한 프로그래밍 모델을 제공 합니다.  
  
## <a name="msdtc-transactions"></a>MSDTC 트랜잭션  
 MSDTC(Microsoft Distributed Transaction Coordinator)는 분산 트랜잭션을 지원하는 트랜잭션 관리자입니다.  
  
 자세한 내용은 참조는 [DTC 프로그래머 참조](http://go.microsoft.com/fwlink/?LinkId=94948)합니다.  
  
 WCF 서비스 또는 응용 프로그램에 MSDTC는 클라이언트 또는 서비스 내에서 만든 트랜잭션의 코디네이션을 위한 인프라를 제공 합니다.
