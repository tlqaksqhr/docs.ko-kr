---
title: WS-MetadataExchange 바인딩
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ws-metadataexchange-bindings"></a>WS-MetadataExchange 바인딩
이 항목에서는 여러 가지 전송에 대해 기본 메타데이터 교환 바인딩을 생성하는 방법을 설명합니다.  
  
## <a name="the-default-bindings"></a>기본 바인딩  
  
|기본 바인딩 이름|바인딩 생성 방법|  
|--------------------------|------------------------------------|  
|MexHttpBinding|전송 수준 보안이 비활성화된 <xref:System.ServiceModel.WSHttpBinding>입니다.|  
|MexHttpsBinding|전송 수준 보안을 지원하는 <xref:System.ServiceModel.WSHttpBinding>입니다.|  
|MexNamedPipeBinding|기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 있는 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>입니다.|  
|MexTcpBinding|기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>입니다.|
