---
title: "데이터 계약 이름 | Microsoft Docs"
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
  - "데이터 계약 [WCF], 이름 지정"
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# 데이터 계약 이름
때때로 클라이언트와 서비스는 동일한 형식을 공유하지 않습니다.그래도 양쪽의 데이터 계약이 동일하면 서로 데이터를 전달할 수 있습니다.[데이터 계약 동등성](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)은 데이터 계약 및 데이터 멤버 이름을 기반으로 하며, 따라서 이러한 이름에 대해 형식 및 멤버를 매핑하도록 메커니즘이 제공됩니다.이 항목에서는 이름을 만들 때 데이터 계약의 이름 지정 규칙 및 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 인프라의 기본 동작 규칙에 대해 설명합니다.  
  
## 기본 규칙  
 데이터 계약 이름 지정과 관련된 기본 규칙에는 다음이 포함됩니다.  
  
-   정규화된 데이터 계약 이름은 네임스페이스와 이름으로 구성됩니다.  
  
-   데이터 멤버에는 이름만 있으며, 네임스페이스는 없습니다.  
  
-   데이터 계약을 처리할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라는 데이터 계약 및 데이터 멤버의 네임스페이스와 이름 모두에 대해 대\/소문자를 구분합니다.  
  
## 데이터 계약 네임스페이스  
 데이터 계약 네임스페이스는 URI\(Uniform Resource Identifier\)의 형식을 사용합니다.절대 URI나 상대 URI일 수 있습니다.기본적으로 특정 형식에 대한 데이터 계약은 해당 형식의 CLR\(공용 언어 런타임\) 네임스페이스로부터 가져오는 네임스페이스에 할당됩니다.  
  
 기본적으로, 주어진 CLR 네임스페이스\(*Clr.Namespace* 형식\)는 네임스페이스 "http:\/\/schemas.datacontract.org\/2004\/07\/Clr.Namespace"로 매핑됩니다.이 기본값을 재정의하려면 전체 모듈 또는 어셈블리에 <xref:System.Runtime.Serialization.ContractNamespaceAttribute> 특성을 적용합니다.또는 각 형식에 대해 데이터 계약 네임스페이스를 제어하려면 <xref:System.Runtime.Serialization.DataContractAttribute>의 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> 속성을 설정합니다.  
  
> [!NOTE]
>  "http:\/\/schemas.microsoft.com\/2003\/10\/Serialization" 네임스페이스가 예약되며, 데이터 계약 네임스페이스로 사용될 수 없습니다.  
  
> [!NOTE]
>  `delegate` 선언을 포함하는 데이터 계약 형식에서 기본 네임스페이스를 재정의할 수 없습니다.  
  
## 데이터 계약 이름  
 주어진 형식에 대한 데이터 계약의 기본 이름은 해당 형식의 이름입니다.기본값을 재정의하려면 <xref:System.Runtime.Serialization.DataContractAttribute>의 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 속성을 대체 이름으로 설정합니다.제네릭 형식에 대한 특정 규칙은 이 항목의 뒷부분에 있는 "제네릭 형식에 대한 데이터 계약 이름"에서 설명합니다.  
  
## 데이터 멤버 이름  
 주어진 필드 또는 속성에 대한 데이터 멤버의 기본 이름은 해당 필드 또는 속성의 이름입니다.기본값을 재정의하려면 <xref:System.Runtime.Serialization.DataMemberAttribute>의 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> 속성을 대체 값으로 설정합니다.  
  
### 예제  
 다음 예제에서는 데이터 계약 및 데이터 멤버의 기본 이름 지정 동작을 재정의할 수 있는 방법을 보여 줍니다.  
  
 [!code-csharp[C_DataContractNames#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
 [!code-vb[C_DataContractNames#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]  
  
## 제네릭 형식에 대한 데이터 계약 이름  
 제네릭 형식에 대한 데이터 계약 이름을 결정하는 데 특별한 규칙이 있습니다.이러한 규칙은 동일한 제네릭 형식의 폐쇄형 두 개의 제네릭 형식 간에 데이터 계약 이름이 충돌하는 것을 막도록 도와줍니다.  
  
 기본적으로 제네릭 형식에 대한 데이터 계약 이름은 형식 이름이며, 이 이름 다음에는 문자열 "Of", 제네릭 매개 변수의 데이터 계약 이름, 제네릭 매개 변수의 데이터 계약 네임스페이스를 사용하여 계산된 *해시*가 차례로 나옵니다.해시는 데이터 조각을 고유하게 식별하는 "지문"의 역할을 하는 수학 함수의 결과입니다.모든 제네릭 매개 변수가 기본 형식인 경우 해시는 생략됩니다.  
  
 예를 들어 다음 예제의 형식을 참조하십시오.  
  
 [!code-csharp[C_DataContractNames#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
 [!code-vb[C_DataContractNames#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]  
  
 이 예제에서 `Drawing<Square,RegularRedBrush>` 형식의 데이터 계약 이름은 "DrawingOfSquareRedBrush5HWGAU6h"이며, 여기서 "5HWGAU6h"는 "urn:shapes" 및 "urn:default" 네임스페이스의 해시입니다.`Drawing<Square,SpecialRedBrush>` 형식의 데이터 계약 이름은 "DrawingOfSquareRedBrushjpB5LgQ\_S"이며, 여기서 "jpB5LgQ\_S"는 "urn:shapes" 및 "urn:special" 네임스페이스의 해시입니다.해시를 사용하지 않으면 두 이름이 동일하므로 이름이 충돌합니다.  
  
## 제네릭 형식에 대해 데이터 계약 이름 사용자 지정  
 위에서 설명한 것과 같이 제네릭 형식에 대해 생성된 데이터 계약 이름이 허용되지 않는 경우도 있습니다.예를 들어 이름 충돌이 발생하지 않도록 하려면 해시를 제거해야 할 수 있습니다.이 경우에는 `DataContractAttribute` 특성의 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 속성을 사용하여 이름을 생성하는 여러 가지 방법을 지정할 수 있습니다.제네릭 매개 변수의 데이터 계약 이름을 참조하기 위해 `Name` 속성 내에서 중괄호 안에 숫자를 사용할 수 있습니다.예를 들어 0은 첫 번째 매개 변수를 참조하고, 1은 두 번째 매개 변수를 참조합니다. 해시를 참조하기 위해 중괄호 안에 숫자\(\#\) 기호를 사용할 수 있습니다.이러한 각각의 참조를 여러 번 사용하거나 전혀 사용하지 않을 수 있습니다.  
  
 예를 들어 이전 제네릭 `Drawing` 형식은 다음 예제와 같이 선언되었을 수 있습니다.  
  
 [!code-csharp[c_DataContractNames#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
 [!code-vb[c_DataContractNames#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]  
  
 이 경우에는 `Drawing<Square,RegularRedBrush>` 형식의 데이터 계약 이름이 "Drawing\_using\_RedBrush\_brush\_and\_Square\_shape"입니다.<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 속성에 "{\#}"이 있으면 해시가 이름의 일부가 아니므로 형식의 이름을 지정할 때 충돌이 발생하기 쉽습니다. 예를 들어 `Drawing<Square,SpecialRedBrush>` 형식의 데이터 계약 이름이 동일할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 <xref:System.Runtime.Serialization.ContractNamespaceAttribute>   
 [데이터 계약 사용](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [데이터 계약 동등성](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)   
 [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md)   
 [데이터 계약 버전 관리](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)