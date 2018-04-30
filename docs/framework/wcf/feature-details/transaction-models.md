---
title: 트랜잭션 모델
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c68a23e9ee86050a9db4c63c8c97d017794bce8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="transaction-models"></a>트랜잭션 모델
이 항목에서는 트랜잭션 프로그래밍 모델 및 Microsoft가 제공하는 인프라 구성 요소 간의 관계에 대해 설명합니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 트랜잭션을 사용하는 경우 서로 다른 트랜잭션 모델 사이에서 선택하지 않고 통합되고 일관된 모델의 다른 계층에서 작업하는 것임을 이해하는 것이 중요합니다.  
  
 다음 단원에서는 세 가지 기본 트랜잭션 구성 요소에 대해 설명합니다.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation 트랜잭션  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 트랜잭션 지원을 사용하여 트랜잭션 서비스를 작성할 수 있습니다. 또한 WS-AT(WS-AtomicTransaction) 프로토콜에 대한 지원을 통해 응용 프로그램은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 또는 타사 기술 중 하나를 사용하여 빌드된 웹 서비스에 트랜잭션을 전달할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 또는 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 트랜잭션 기능은 인프라가 트랜잭션을 생성, 전달 및 동기화 하는 방법 및 시점을 선언적으로 지정하기 위한 특성 및 구성을 제공합니다.  
  
## <a name="systemtransactions-transactions"></a>System.Transactions 트랜잭션  
 <xref:System.Transactions> 네임스페이스는 <xref:System.Transactions.Transaction> 클래스 기반의 명시적 프로그래밍 모델과 <xref:System.Transactions.TransactionScope> 클래스를 사용하는 암시적 프로그래밍 모델을 모두 제공합니다. 후자의 경우 인프라에서 자동으로 트랜잭션을 관리합니다.  
  
 이러한 두 가지 모델을 사용 하 여 트랜잭션 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 [트랜잭션 응용 프로그램을 작성](http://go.microsoft.com/fwlink/?LinkId=94947)합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 또는 응용 프로그램의 경우 <xref:System.Transactions>은 클라이언트 응용 프로그램 내에서 트랜잭션을 만들고 필요한 경우 서비스 내에서 트랜잭션과 명시적으로 상호 작용하기 위한 프로그래밍 모델을 제공합니다.  
  
## <a name="msdtc-transactions"></a>MSDTC 트랜잭션  
 MSDTC(Microsoft Distributed Transaction Coordinator)는 분산 트랜잭션을 지원하는 트랜잭션 관리자입니다.  
  
 자세한 내용은 참조는 [DTC 프로그래머 참조](http://go.microsoft.com/fwlink/?LinkId=94948)합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 또는 응용 프로그램의 경우 MSDTC는 클라이언트 또는 서비스 내에서 만든 트랜잭션의 코디네이션을 위한 인프라를 제공합니다.
