---
title: "서비스 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "구성 [WCF]"
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# 서비스 구성
서비스 계약을 디자인하고 구현했으면 서비스를 구성할 준비가 되었습니다.  여기서 서비스를 찾을 수 있는 주소, 메시지를 보내고 받는 데 사용하는 전송 및 메시지 인코딩, 서비스에 필요한 보안 형식 지정 등 서비스가 클라이언트에 노출되는 방법을 정의하고 사용자 지정할 수 있습니다.  
  
 여기서 사용되는 구성은 코드에서 명령적으로 또는 구성 파일을 사용하여 끝점 주소, 사용된 전송 및 보안 체계 지정 같은 서비스의 다양한 측면을 정의하고 사용자 지정할 수 있는 모든 방식이 포함됩니다.  실제로 구성 작성은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램을 프로그래밍하는 과정의 주요 부분입니다.  
  
## 단원 내용  
 [단순화된 구성](../../../docs/framework/wcf/simplified-configuration.md)  
 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]부터 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 구성 요구 사항을 간소화하는 새로운 기본 구성 모델이 함께 제공됩니다.  특정 서비스에 대해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 구성을 제공하지 않으면 런타임이 기본 끝점, 바인딩 및 동작을 사용해 서비스를 자동으로 구성합니다.  
  
 [구성 파일을 사용하여 서비스 구성](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 구성 기술을 사용하여 구성할 수 있습니다.  가장 일반적으로 XML 요소는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스트하는 IIS\(인터넷 정보 서비스\) 사이트의 Web.config 파일에 추가됩니다.  이 요소를 사용하여 끝점 주소\(서비스와의 통신에 사용되는 실제 주소\) 등의 세부 사항을 컴퓨터별로 변경할 수 있습니다.  
  
 [바인딩](../../../docs/framework/wcf/bindings.md)  
 또한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에는 사용된 전송, 보안, 메시지 인코딩 등 클라이언트와 서비스가 통신하는 방법에 대한 가장 기본적인 기능을 신속하게 선택할 수 있도록 하는 바인딩 형태로 시스템에서 제공하는 여러 개의 일반 구성이 포함되어 있습니다.  
  
 [끝점](../../../docs/framework/wcf/endpoints.md)  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와의 모든 통신은 서비스의 *끝점*을 통해 수행됩니다.  끝점에는 계약, 바인딩에 지정된 구성 정보 및 서비스를 찾을 위치나 서비스 정보를 얻을 수 있는 위치를 나타내는 주소가 포함되어 있습니다.  
  
 [서비스에 보안 설정](../../../docs/framework/wcf/securing-services.md)  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 및 기존 보안 메커니즘을 사용하여 기밀성, 무결성, 인증 및 권한 부여를 서비스에 구현할 수 있습니다.  보안 성공 및 실패를 감사할 수도 있습니다.  
  
 [WS\-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 다른 플랫폼 또는 운영 체제의 서비스 및 클라이언트와 상호 운용될 수 있는 서비스를 배포하기 위한 요구 사항은 WS\-I Basic Profile 1.1 사양에 간략하게 설명되어 있습니다.  
  
## 참조  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## 관련 단원  
 [기본 프로그래밍 수명 주기](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [서비스 디자인 및 구현](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [서비스 호스팅](../../../docs/framework/wcf/hosting-services.md)  
  
 [클라이언트 빌드](../../../docs/framework/wcf/building-clients.md)  
  
 [확장성 소개](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [관리 및 진단](../../../docs/framework/wcf/diagnostics/index.md)  
  
## 참고 항목  
 [기본 WCF 프로그래밍](../../../docs/framework/wcf/basic-wcf-programming.md)   
 [개념적 개요](../../../docs/framework/wcf/conceptual-overview.md)   
 [WCF 기능 정보](../../../docs/framework/wcf/feature-details/index.md)