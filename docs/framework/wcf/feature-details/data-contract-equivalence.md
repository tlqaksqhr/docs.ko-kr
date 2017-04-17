---
title: "데이터 계약 동등성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "데이터 계약 [WCF], 동등성"
ms.assetid: f06f3c7e-c235-4ec1-b200-68142edf1ed1
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# 데이터 계약 동등성
클라이언트가 서비스에 특정 형식의 데이터를 성공적으로 보내거나, 서비스에서 클라이언트에 데이터를 성공적으로 보내기 위해, 보낸 형식이 받는 측에 반드시 있어야 하는 것은 아닙니다.  두 형식의 데이터 계약이 일치하기만 하면 됩니다.  [데이터 계약 버전 관리](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)에 설명한 것처럼 엄격한 대응이 필요하지 않은 경우도 있습니다.  
  
 데이터 계약이 서로 같으려면 네임스페이스와 이름이 같아야 합니다.  또한 한 쪽의 각 데이터 멤버에 해당하는 데이터 멤버가 다른 쪽에 있어야 합니다.  
  
 데이터 멤버가 같으려면 이름이 같아야 합니다.  또한 데이터 멤버가 동일한 형식의 데이터를 나타내야 합니다. 즉, 해당 데이터 계약이 일치해야 합니다.  
  
> [!NOTE]
>  데이터 계약 이름 및 네임스페이스와 데이터 멤버 이름은 대\/소문자를 구분합니다.  
  
 데이터 계약 이름과 네임스페이스 및 데이터 멤버 이름[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [데이터 계약 이름](../../../../docs/framework/wcf/feature-details/data-contract-names.md)을 참조하세요.  
  
 같은 쪽\(발신자 또는 수신자\)에 두 가지 형식이 있고 해당 데이터 계약이 다른 경우\(예: 데이터 멤버가 서로 다른 경우\) 동일한 이름과 네임스페이스를 지정하지 않아야 합니다.  그렇게 하면 예외가 throw될 수 있습니다.  
  
 다음 형식에 대한 데이터 계약은 서로 동등합니다.  
  
 [!code-csharp[C_DataContractNames#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#5)]
 [!code-vb[C_DataContractNames#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#5)]  
  
## 데이터 멤버 주문 및 데이터 계약 동등성  
 <xref:System.Runtime.Serialization.DataMemberAttribute> 클래스의 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> 속성을 사용하여 데이터 계약 동등성에 영향을 줄 수 있습니다.  데이터 계약이 서로 동등하려면 멤버가 동일한 순서로 표시되어야 합니다.  기본 순서는 사전순입니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [데이터 멤버 순서](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 예를 들어, 다음 코드는 동등한 데이터 계약을 생성합니다.  
  
 [!code-csharp[C_DataContractNames#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#6)]
 [!code-vb[C_DataContractNames#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#6)]  
  
 다음 코드는 동등한 데이터 계약을 생성하지 않습니다.  
  
 [!code-csharp[C_DataContractNames#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#7)]
 [!code-vb[C_DataContractNames#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#7)]  
  
## 상속, 인터페이스 및 데이터 계약 동등성  
 동등성을 결정할 때 다른 데이터 계약으로부터 상속되는 데이터 계약은 기본 형식의 모든 데이터 멤버를 포함하는 데이터 계약처럼 처리됩니다.  데이터 멤버의 순서가 일치해야 하고, 기본 형식 멤버가 파생된 형식 멤버보다 앞에 와야 합니다.  또한 다음 코드 예제에서처럼 두 데이터 멤버의 순서 값이 동일한 경우 해당 데이터 멤버의 순서는 사전순으로 지정됩니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [데이터 멤버 순서](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 다음 예제에서 `Employee` 형식 데이터 계약은 `Worker` 형식 데이터 계약과 동등합니다.  
  
 [!code-csharp[C_DataContractNames#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#8)]
 [!code-vb[C_DataContractNames#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#8)]  
  
 클라이언트와 서비스 간에 매개 변수 및 반환 값을 전달할 때 수신하는 끝점에 파생된 클래스의 데이터 계약이 필요한 경우 기본 클래스의 데이터 계약을 보낼 수 없습니다.  이는 개체 지향 프로그래밍 개념을 따릅니다.  이전 예제에서 `Employee`가 필요한 경우 `Person` 형식 개체를 보낼 수 없습니다.  
  
 기본 클래스의 데이터 계약이 필요한 경우에 파생 클래스의 데이터 계약을 보낼 수 있지만, 수신하는 끝점이 <xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하여 파생 형식에 대해 "알고 있는" 경우에만 해당됩니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [데이터 계약 알려진 형식](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  이전 예제에서 `Person`이 필요할 때 `Employee` 형식 개체를 보낼 수 있지만, 수신기 코드에서 <xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하여 알려진 형식 목록에 포함시키는 경우에만 해당됩니다.  
  
 응용 프로그램 간에 매개 변수 및 반환 값을 전달할 때 필요한 형식이 인터페이스이면 <xref:System.Object> 형식의 예상 형식과 동등합니다.  모든 형식이 궁극적으로 <xref:System.Object>에서 파생되기 때문에 모든 데이터 계약은 궁극적으로 <xref:System.Object>에 대한 데이터 계약에서 파생됩니다.  따라서 인터페이스가 필요할 때 모든 데이터 계약 형식을 전달할 수 있습니다.  인터페이스로 성공적으로 작업하려면 추가 단계를 수행해야 합니다. 자세한 내용은 [데이터 계약 알려진 형식](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [데이터 멤버 순서](../../../../docs/framework/wcf/feature-details/data-member-order.md)   
 [데이터 계약 알려진 형식](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [데이터 계약 이름](../../../../docs/framework/wcf/feature-details/data-contract-names.md)