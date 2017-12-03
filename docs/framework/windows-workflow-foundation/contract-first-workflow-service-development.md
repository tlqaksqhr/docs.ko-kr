---
title: "계약 중심 워크플로 서비스 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5dbaa7b-005f-4330-848d-58ac4f42f093
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c3d22c83f5fbc1144d139c9e7ba6a43137f6d144
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="contract-first-workflow-service-development"></a>계약 중심 워크플로 서비스 개발
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 [!INCLUDE[wf](../../../includes/wf-md.md)]는 계약 중심 워크플로 개발의 형태로 웹 서비스와 워크플로 간에 보다 우수한 통합 성능을 제공합니다. 계약 중심 워크플로 개발 도구를 사용하면 코드에서 계약을 먼저 디자인할 수 있습니다. 그러면 이 도구는 계약의 작업을 위해 도구 상자에 활동 템플릿을 자동으로 생성합니다. 이 항목에서는 워크플로 서비스 맵의 활동 및 속성을 서비스 계약의 특성에 매핑하는 방법을 간략하게 설명합니다. 계약 중심 워크플로 서비스를 만드는 단계별 예제를 보려면 [하는 방법: 기존 서비스 계약을 사용 하는 워크플로 서비스 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)합니다.  
  
## <a name="in-this-topic"></a>항목 내용  
  
-   [워크플로 특성에 서비스 계약 특성 매핑](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MappingAttributes)  
  
    -   [서비스 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
    -   [작업 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
    -   [메시지 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
    -   [데이터 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
    -   [오류 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
-   [추가 지원 및 구현 정보](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#AdditionalSupport)  
  
    -   [지원 되지 않는 서비스 계약 기능](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
    -   [구성 된 메시징 활동 생성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
##  <a name="MappingAttributes"></a>워크플로 특성에 서비스 계약 특성 매핑  
 다음 단원의 표에는 여러 WCF 특성 및 속성과 해당 WCF 특성 및 속성을 계약 중심 워크플로의 메시징 활동 및 속성에 매핑하는 방법이 나와 있습니다.  
  
-   [서비스 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
-   [작업 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
-   [메시지 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
-   [데이터 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
-   [오류 계약 특성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
###  <a name="ServiceContract"></a>서비스 계약 특성  
  
|속성 이름|지원함|설명|WF 유효성 검사|  
|-------------------|---------------|-----------------|-------------------|  
|CallbackContract|아니요|계약이 이중 계약인 경우 콜백 계약의 형식을 가져오거나 설정합니다.|(N/A)|  
|ConfigurationName|아니요|응용 프로그램 구성 파일에서 서비스를 찾는 데 사용되는 이름을 가져오거나 설정합니다.|(N/A)|  
|HasProtectionLevel|예|멤버에 보호 수준이 할당되어 있는지 여부를 나타내는 값을 가져옵니다.|Receive.ProtectionLevel이 null이 아니어야 합니다.|  
|이름|예|에 대 한 이름을 가져오거나 설정 합니다.는 \<y p e > 요소에 WSDL 웹 서비스 설명 언어 ().|Receive.ServiceContractName.LocalName이 일치해야 합니다.|  
|네임스페이스|예|네임 스페이스를 가져오거나 설정 합니다.는 \<y p e > 요소에 WSDL 웹 서비스 설명 언어 ().|Receive.ServiceContractName.NameSpace가 일치해야 합니다.|  
|ProtectionLevel|예|계약에 대한 바인딩이 ProtectionLevel 속성 값을 지원해야 하는지 여부를 지정합니다.|Receive.ProtectionLevel이 일치해야 합니다.|  
|SessionMode|아니요|세션이 허용되는지, 허용되지 않는지 또는 필요한지를 가져오거나 설정합니다.|(N/A)|  
|TypeId|아니요|파생 클래스에서 구현된 경우 이 특성의 고유 식별자를 가져옵니다. 특성에서 상속됩니다.|(N/A)|  
  
 여기에 하위 단원 본문을 삽입합니다.  
  
###  <a name="OperationContract"></a>작업 계약 특성  
  
|속성 이름|지원함|설명|WF 유효성 검사|  
|-------------------|---------------|-----------------|-------------------|  
|동작|예|요청 메시지의 WS-Addressing 동작을 가져오거나 설정합니다.|Receive.Action이 일치해야 합니다.|  
|AsyncPattern|아니요|작업은 Begin를 사용 하 여 비동기적으로 구현 됨을 나타냅니다\<n a m e > 및 끝\<n a m e > 서비스 계약에서 메서드 쌍입니다.|(N/A)|  
|HasProtectionLevel|예|이 작업의 메시지에 대해 암호화, 서명 또는 둘 모두를 수행해야 할지 나타내는 값을 가져옵니다.|Receive.ProtectionLevel이 null이 아니어야 합니다.|  
|IsInitiating|아니요|메서드가 서버의 세션(있는 경우)을 시작할 수 있는 작업을 구현할지 여부를 나타내는 값을 가져오거나 설정합니다.|(N/A)|  
|IsOneWay|예|작업이 회신 메시지를 반환할지 여부를 나타내는 값을 가져오거나 설정합니다.|(이 Receive에 대한 SendReply가 없거나 이 Send에 대한 ReceiveReply가 없음)|  
|IsTerminating|아니요|회신 메시지(있는 경우)를 보낸 후 서비스 작업의 결과로 서버에서 세션을 종료할지 여부를 나타내는 값을 가져오거나 설정합니다.|(N/A)|  
|이름|예|작업의 이름을 가져오거나 설정합니다.|Receive.OperationName이 일치해야 합니다.|  
|ProtectionLevel|예|작업의 메시지에 대해 암호화, 서명 또는 둘 모두를 수행해야 할지 지정하는 값을 가져오거나 설정합니다.|Receive.ProtectionLevel이 일치해야 합니다.|  
|ReplyAction|예|작업의 회신 메시지에 대한 SOAP 동작 값을 가져오거나 설정합니다.|SendReply.Action이 일치해야 합니다.|  
|TypeId|아니요|파생 클래스에서 구현된 경우 이 특성의 고유 식별자를 가져옵니다. 특성에서 상속됩니다.|(N/A)|  
  
###  <a name="MessageContract"></a>메시지 계약 특성  
  
|속성 이름|지원함|설명|WF 유효성 검사|  
|-------------------|---------------|-----------------|-------------------|  
|HasProtectionLevel|예|메시지에 보호 수준이 있는지 여부를 나타내는 값을 가져옵니다.|유효성 검사가 수행되지 않습니다. Receive.Content 및 SendReply.Content가 메시지 계약 형식과 일치해야 합니다.|  
|IsWrapped|예|메시지 본문에 래퍼 요소가 있는지 여부를 지정하는 값을 가져오거나 설정합니다.|유효성 검사가 수행되지 않습니다. Receive.Content 및 Sendreply.Content가 메시지 계약 형식과 일치해야 합니다.|  
|ProtectionLevel|아니요|메시지 암호화, 서명 또는 두 가지 모두가 필요한지 여부를 지정하는 값을 가져오거나 설정합니다.|(N/A)|  
|TypeId|예|파생 클래스에서 구현된 경우 이 특성의 고유 식별자를 가져옵니다. 특성에서 상속됩니다.|유효성 검사가 수행되지 않습니다. Receive.Content 및 SendReply.Content가 메시지 계약 형식과 일치해야 합니다.|  
|WrapperName|예|메시지 본문의 래퍼 요소 이름을 가져오거나 설정합니다.|유효성 검사가 수행되지 않습니다. Receive.Content 및 SendReply.Content가 메시지 계약 형식과 일치해야 합니다.|  
|WrapperNamespace|아니요|메시지 본문 래퍼 요소의 네임스페이스를 가져오거나 설정합니다.|(N/A)|  
  
###  <a name="DataContract"></a>데이터 계약 특성  
  
|속성 이름|지원함|설명|WF 유효성 검사|  
|-------------------|---------------|-----------------|-------------------|  
|IsReference|아니요|개체 참조 데이터를 유지할지 여부를 나타내는 값을 가져오거나 설정합니다.|(N/A)|  
|이름|예|형식의 데이터 계약 이름을 가져오거나 설정합니다.|유효성 검사가 수행되지 않습니다. Receive.Content 및 SendReply.Content가 메시지 계약 형식과 일치해야 합니다.|  
|네임스페이스|예|형식에 대한 데이터 계약의 네임스페이스를 가져오거나 설정합니다.|유효성 검사가 수행되지 않습니다. Receive.Content 및 SendReply.Content가 메시지 계약 형식과 일치해야 합니다.|  
|TypeId|아니요|파생 클래스에서 구현된 경우 이 특성의 고유 식별자를 가져옵니다. 특성에서 상속됩니다.|(N/A)|  
  
###  <a name="FaultContract"></a>오류 계약 특성  
  
|속성 이름|지원함|설명|WF 유효성 검사|  
|-------------------|---------------|-----------------|-------------------|  
|동작|예|작업 계약의 일부로 지정된 SOAP 오류 메시지의 동작을 가져오거나 설정합니다.|SendReply.Action이 일치해야 합니다.|  
|DetailType|예|오류 정보가 포함된 serialize할 수 있는 개체의 형식을 가져옵니다.|SendReply.Content가 형식과 일치해야 합니다.|  
|HasProtectionLevel|아니요|SOAP 오류 메시지에 보호 수준이 할당되어 있는지 여부를 나타내는 값을 가져옵니다.|(N/A)|  
|이름|아니요|WSDL(웹 서비스 기술 언어)에서 오류 메시지의 이름을 가져오거나 설정합니다.|(N/A)|  
|네임스페이스|아니요|SOAP 오류의 네임스페이스를 가져오거나 설정합니다.|(N/A)|  
|ProtectionLevel|아니요|바인딩에서 SOAP 오류에 필요한 보호 수준을 지정합니다.|(N/A)|  
|TypeId|아니요|파생 클래스에서 구현된 경우 이 특성의 고유 식별자를 가져옵니다. 특성에서 상속됩니다.|(N/A)|  
  
##  <a name="AdditionalSupport"></a>추가 지원 및 구현 정보  
  
-   [지원 되지 않는 서비스 계약 기능](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
-   [구성 된 메시징 활동 생성](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
###  <a name="UnsupportedFeatures"></a>지원 되지 않는 서비스 계약 기능  
  
-   계약에서 TPL(작업 병렬 라이브러리) 작업을 사용할 수 없습니다.  
  
-   서비스 계약에서 상속이 지원되지 않습니다.  
  
###  <a name="ActivityGeneration"></a>구성 된 메시징 활동 생성  
 계약 중심 워크플로 서비스를 사용할 때는 미리 구성된 메시지 활동의 생성을 지원하기 위해 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동에 두 개의 공용 정적 메서드가 추가됩니다.  
  
-   <xref:System.ServiceModel.Activities.Receive.FromOperationDescription%2A?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Activities.SendReply.FromOperationDescription%2A?displayProperty=nameWithType>  
  
 이러한 메서드에서 생성된 활동은 계약 유효성 검사를 거쳐야 하므로 이러한 메서드는 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply>에 대한 유효성 검사 논리의 일부로 내부적으로 사용됩니다. <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>, <xref:System.ServiceModel.Activities.Receive.Action%2A>, <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> 및 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>는 모두 가져온 계약과 일치하도록 미리 구성되어 있습니다. 워크플로 디자이너에서 활동에 대 한 콘텐츠 속성 페이지에는 **메시지** 또는 **매개 변수** 섹션은 또한 계약과 일치 하도록 미리 구성 합니다.  
  
 WCF 오류 계약 별도의 집합을 반환 하 여 처리 됩니다 구성 <xref:System.ServiceModel.Activities.SendReply> 각에 표시 되는 오류에 대 한 활동의 <xref:System.ServiceModel.Description.OperationDescription.Faults%2A> <xref:System.ServiceModel.Description.FaultDescriptionCollection>합니다.  
  
 다른 부분에 대 한 <xref:System.ServiceModel.Description.OperationDescription> WF 서비스 오늘 (예: WebGet/WebInvoke 동작 또는 사용자 지정 작업 동작)에서 지원 되지 않는, API 생성 및 구성의 일부분으로 해당 값을 무시 합니다. 예외가 throw되지는 않습니다.
