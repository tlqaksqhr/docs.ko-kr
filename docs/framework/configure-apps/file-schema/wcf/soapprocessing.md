---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1aeb100e1b8e160d30566cd43d67cbf49c6b5c4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsoapprocessinggt"></a>&lt;soapProcessing&gt;

서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 끝점 동작을 정의합니다.

**\<시스템입니다. ServiceModel >**   
&nbsp;&nbsp;**\<동작 >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<동작 >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing >**

## <a name="syntax"></a>구문

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|                   | 설명 |
| ----------------- | ----------- |
| `processMessages` | SOAP 메시지 버전 간에 메시지가 마샬링되어야 하는지 여부를 지정하는 부울 값입니다. |

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<동작 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | 끝점 동작을 지정합니다. |

## <a name="remarks"></a>설명

SOAP 처리는 메시지 버전 간에 메시지를 변환하는 프로세스입니다.

[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 라우팅 서비스는 한 프로토콜에서 다른 프로토콜로 메시지를 변환할 수 있습니다. 들어오는 메시지 버전과 나가는 메시지 버전이 다른 경우 올바른 버전의 새로운 메시지가 만들어집니다. 메시지 하나를 처리 <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` 다른 새 구성 하 여 수행 됩니다 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 본문 부분과 관련 헤더는 들어오는를 포함 하는 메시지 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 메시지입니다. 주소 지정에만 사용되는 헤더나 라우터 수준에서 인식되는 헤더는 새 WCF 메시지 생성 중에 사용되지 않습니다. 이러한 헤더는 서로 다른 버전(주소 지정 헤더인 경우)이거나 클라이언트와 라우터 간의 통신의 일부로 처리되었기 때문입니다.

헤더가 아웃바운드 메시지에 배치되는지 여부는 들어오는 채널 계층을 통해 전달될 때 해당 헤더가 인식된 것으로 표시되었는지 여부에 따라 결정됩니다. 사용자 지정 헤더 등과 같이 인식되지 않는 헤더는 제거되지 않고 아웃바운드 메시지에 복사되어 라우팅 서비스를 통해 전달됩니다. 메시지의 본문은 아웃바운드 메시지에 복사됩니다. 그런 다음 메시지가 아웃바운드 채널로 전송되며 이때 해당 통신 프로토콜/전송에 대한 모든 헤더와 기타 봉투 데이터가 만들어지고 추가됩니다.

이러한 처리 단계는 SOAP 처리 동작이 지정될 때 수행됩니다. 이 [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) 동작은 라우팅 서비스가 시작 될 때 모든 클라이언트 (보내는) 끝점에 적용 되는 끝점 동작. 기본적으로는 [ \<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) 동작을 만들고 새 연결 [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) 동작 `processMessages` 로 설정 `true` 각각에 대해 클라이언트 끝점입니다. 라우팅 서비스에서 인식하지 못하는 프로토콜을 사용하거나 기본 처리 동작을 재지정하려는 경우 전체 라우팅 서비스 또는 특정 끝점에 대해 SOAP 처리를 사용하지 않을 수 있습니다.  모든 끝점에서 전체 라우팅 서비스에 대해 SOAP 처리를 사용 하지 않으려면 설정는 `soapProcessing` 특성에는 [ \<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) 동작을 `false`합니다. 특정 끝점에 대해 SOAP 처리를 해제하려면 이 동작을 사용하여 `processMessages` 특성을 `false`로 설정한 다음 이 동작을 기본 처리 코드가 실행되지 않도록 할 끝점에 연결합니다.  경우는 [ \<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) 라우팅 서비스를 설정 하는 동작, 끝점 동작을 이미 존재 하므로 다시 적용는 건너뜁니다.
