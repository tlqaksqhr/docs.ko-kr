---
title: "WCF 확장 | Microsoft Docs"
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
  - "확장성 [WCF]"
  - "WCF, 확장성"
  - "Windows Communication Foundation, 확장성"
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# WCF 확장
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 런타임 구성 요소를 수정하고 확장하여 서비스 기반 응용 프로그램을 정확하게 제어하고 확장할 수 있습니다.  이 섹션의 항목에서는 확장성 아키텍처에 대해 자세히 설명합니다.  기본 프로그래밍에 대한 자세한 내용은 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)을 참조하세요.  
  
## 단원 내용  
 [ServiceHost 및 서비스 모델 계층 확장](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 서비스 모델 계층은 기본 채널에서 들어오는 메시지를 가져와서 응용 프로그램 코드에서 이를 메서드 호출로 변환하여 결과를 다시 호출자에게 보내는 역할을 합니다.  서비스 모델 확장은 디스패처 기능, 사용자 지정 동작, 메시지 및 매개 변수 가로채기 그리고 다른 확장 기능이 포함된 통신 동작 및 기능 또는 실행을 수정하거나 구현합니다.  
  
 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 바인딩은 끝점에 연결하는 데 필요한 통신 세부 사항을 설명하는 개체입니다.  바인딩 확장이나 사용자 지정 바인딩은 응용 프로그램 기능을 지원하는 데 필요한 사용자 지정 통신 기능을 구현합니다.  
  
 [채널 계층 확장](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 채널 계층은 서비스 모델 계층 아래에 있고 클라이언트와 서비스 간의 메시지 교환을 담당합니다.  채널 확장은 보안 등의 새 프로토콜 기능을 구현할 수 있습니다.  또한 채널 확장은 SOAP 메시지를 전달할 새 네트워크 전송 구현 같은 전송 기능을 구현합니다.  
  
 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 보안은 전송 보안\(무결성, 기밀성 및 인증\), 액세스 제어\(권한 부여\) 및 감사로 구성됩니다.  `IdentityModel` 네임스페이스에 있는 클래스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 액세스 제어에 사용합니다.  보안 아키텍처를 이해하면 사용자 지정 액세스 제어 시스템을 수용할 사용자 지정 클레임 형식을 만들 수 있습니다.  
  
 [메타데이터 시스템 확장](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메타데이터 시스템은 서비스 기반 응용 프로그램 구현에 필요한 메타데이터를 나타내는 클래스 및 인터페이스 그룹입니다.  클래스를 수정 또는 확장하거나 인터페이스를 구현 및 구성하여 WSDL\(웹 서비스 기술 언어\) 확장이나 사용자 지정 WS\-PolicyAttachments 어설션 같은 사용자 지정 메타데이터를 내보내고 가져옵니다.  
  
 [인코더 및 Serializer 확장](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 인코더 및 serializer는 데이터를 다른 형식으로 변환합니다.  이 섹션의 항목에서는 제공된 클래스를 특별한 요구 사항에 맞게 확장하는 방법에 대해 설명합니다.  
  
## 참조  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## 관련 단원  
 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [WCF 기능 정보](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [지침 및 최선의 방법](../../../../docs/framework/wcf/guidelines-and-best-practices.md)