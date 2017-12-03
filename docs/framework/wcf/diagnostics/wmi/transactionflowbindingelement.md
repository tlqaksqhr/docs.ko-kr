---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa5394e874e35b80b01796642e18d69c71e867dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>구문  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>메서드  
 TransactionFlowBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 TransactionFlowBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="issuedtokens"></a>IssuedTokens  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 발급된 보안 토큰 헤더(WS-Trust의 IssuedTokens)의 요구 사항을 지정합니다.  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스에서 트랜잭션을 이동하는 데 사용하는 트랜잭션 프로토콜입니다.  
  
### <a name="transactions"></a>트랜잭션  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 들어오는 트랜잭션이 지원되는지 여부를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
