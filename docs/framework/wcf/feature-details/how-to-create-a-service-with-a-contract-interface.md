---
title: '방법: 계약 인터페이스를 사용하여 서비스 만들기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4af593edd355ed89da8c5b2c79a4c029b966fe4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>방법: 계약 인터페이스를 사용하여 서비스 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 계약을 만드는 기본 방법은 인터페이스를 사용하는 것입니다. 이 계약은 서비스에서 제공하는 작업에 액세스하는 데 필요한 메시지 컬렉션과 구조를 지정합니다. 이 인터페이스는 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 인터페이스에 적용하고 <xref:System.ServiceModel.OperationContractAttribute> 클래스를 노출할 메서드에 적용하여 입력 및 출력 형식을 정의합니다.  
  
 서비스 계약에 대 한 자세한 내용은 참조 [서비스 계약 디자인](../../../../docs/framework/wcf/designing-service-contracts.md)합니다.  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>인터페이스로 WCF 계약 만들기  
  
1.  Visual Basic, C# 또는 기타 공용 언어 런타임 언어를 사용 하 여 새 인터페이스를 만듭니다.  
  
2.  인터페이스에 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 적용합니다.  
  
3.  인터페이스에 메서드를 정의합니다.  
  
4.  공용 <xref:System.ServiceModel.OperationContractAttribute> 계약의 일부로서 노출해야 하는 각 메서드에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클래스를 적용합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 서비스 계약을 정의하는 인터페이스를 보여 줍니다.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <xref:System.ServiceModel.OperationContractAttribute> 클래스가 적용된 메서드는 기본적으로 요청-회신 메시지 패턴을 사용합니다. 이 메시지 패턴에 대 한 자세한 내용은 참조 [하는 방법: 요청-회신 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)합니다. 특성의 속성을 설정하여 다른 메시지 패턴을 만들고 사용할 수도 있습니다. 더 많은 예제를 참조 하십시오. [하는 방법: 단방향 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) 및 [하는 방법: 이중 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
