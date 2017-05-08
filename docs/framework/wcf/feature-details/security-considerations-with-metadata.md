---
title: "메타데이터 관련 보안 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# 메타데이터 관련 보안 고려 사항
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 메타데이터 기능을 사용하는 경우 서비스 메타데이터를 게시, 검색 및 사용하면 보안에 어떠한 영향이 있는지 검토합니다.  
  
## 메타데이터 게시 시기  
 기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 메타데이터를 게시하지 않습니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 메타데이터를 게시하려면 서비스에 메타데이터 끝점을 추가하여 메타데이터 게시를 사용하도록 명시적으로 설정해야 합니다\([메타데이터 게시](../../../../docs/framework/wcf/feature-details/publishing-metadata.md) 참조\).  메타데이터 게시를 사용하지 않으면 서비스에서 공격 받을 수 있는 부분이 줄어들고 실수로 정보가 공개될 위험이 감소합니다.  모든 서비스에서 메타데이터를 게시해야 하는 것은 아닙니다.  메타데이터를 게시할 필요가 없는 경우 해제된 상태로 두세요.  [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 어셈블리에서 직접 메타데이터와 클라이언트 코드를 생성할 수 있습니다.  Svcutil.exe 사용[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드에서 메타데이터 내보내기](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)를 참조하세요.  
  
## 보안 바인딩을 사용하여 메타데이터 게시  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 기본 메타데이터 바인딩은 보안이 설정되어 있지 않으며 메타데이터에 대한 익명 액세스를 허용합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 게시하는 서비스 메타데이터는 서비스에 대한 자세한 설명을 포함하며 의도적으로 또는 실수로 중요한 정보를 포함할 수 있습니다.  예를 들어 서비스 메타데이터에 공개적으로 브로드캐스팅하지 않으려는 인프라 작업 정보가 포함될 수 있습니다.  무단 액세스로부터 서비스 메타데이터를 보호하려면 메타데이터 끝점에 보안 바인딩을 사용합니다.  메타데이터 끝점은 SSL\(Secure Sockets Layer\)을 사용하여 메타데이터 보안을 유지할 수 있는 HTTP\/GET 요청에 응답합니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [방법: 메타데이터 끝점 보안 설정](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).  
  
 또한 메타데이터 끝점에 보안을 설정하면 변조나 스푸핑의 위험 없이 안전하게 서비스 메타데이터를 검색하는 방법이 제공됩니다.  
  
## 신뢰할 수 있는 메타데이터만 사용  
 서비스 메타데이터를 사용하여 서비스를 호출하는 데 필요한 런타임 구성 요소를 자동으로 생성할 수 있습니다.  디자인 타임에 메타데이터를 사용하여 클라이언트 응용 프로그램을 개발하거나 런타임에 클라이언트가 서비스 호출에 사용하는 바인딩을 동적으로 업데이트할 수도 있습니다.  
  
 서비스 메타데이터를 보안되지 않은 방식으로 검색하면 해당 서비스 메타데이터가 변조되거나 스푸핑될 수 있습니다.  조작된 메타데이터는 클라이언트를 악의적인 서비스로 리디렉션하거나, 손상된 보안 설정을 포함하거나, 악의적인 XML 구조를 포함할 수 있습니다.  메타데이터 문서는 클 수 있으며 자주 파일 시스템에 저장됩니다.  변조 및 스푸핑으로부터 보호하려면 가능한 경우 보안 바인딩을 사용하여 서비스 메타데이터를 요청합니다.  
  
## 안전한 메타데이터 처리 기술 사용  
 서비스 메타데이터는 WS\-MEX\(MetadataExchange\) 등의 표준화된 프로토콜을 사용하여 네트워크를 통해 서비스에서 자주 검색됩니다.  많은 메타데이터 형식에는 추가 메타데이터를 가리키는 참조 메커니즘이 있습니다.  <xref:System.ServiceModel.Description.MetadataExchangeClient> 형식은 WSDL\(웹 서비스 기술 언어\) 문서, XML 스키마 및 MEX 문서의 참조를 자동으로 처리합니다.  검색된 메타데이터로 만든 <xref:System.ServiceModel.Description.MetadataSet> 개체의 크기는 사용된 <xref:System.ServiceModel.Description.MetadataExchangeClient> 인스턴스의 <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> 값과 해당 <xref:System.ServiceModel.Description.MetadataExchangeClient> 인스턴스에서 사용하는 바인딩의 `MaxReceivedMessageSize` 값에 정비례합니다.  이 할당량을 시나리오에 적합한 값으로 설정합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 서비스 메타데이터는 XML로 처리됩니다.  응용 프로그램이 XML 문서를 처리할 때 악의적인 XML 구조로부터 보호되어야 합니다.  XML을 처리할 때 적절한 할당량으로 `XmlDictionaryReader`를 사용하고 <xref:System.Xml.XmlReader> 인스턴스에 대한 <xref:System.Xml.XmlReaderSettings> 개체의 <xref:System.XML.XmlReaderSettings.ProhibitDtd%2A> 속성을 `true`로 설정합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 메타데이터 시스템은 확장 가능하며 메타데이터 확장을 응용 프로그램 구성 파일에 등록할 수 있습니다\([메타데이터 시스템 확장](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md) 참조\).  메타데이터 확장에서 임의 코드를 실행할 수 있으므로 적절한 ACL\(액세스 제어 목록\)로 응용 프로그램 구성 파일을 보호하고 신뢰할 수 있는 메타데이터 확장 구현만 등록해야 합니다.  
  
## 생성된 클라이언트의 유효성 검사  
 신뢰할 수 없는 소스에서 검색된 메타데이터로 클라이언트 코드를 생성하는 경우 해당 클라이언트 코드의 유효성을 검사하여 생성된 클라이언트가 클라이언트 응용 프로그램 보안 정책을 준수하는지 확인합니다.  유효성 검사 동작을 사용하여 클라이언트 바인딩의 설정을 확인하거나 도구에서 생성된 코드를 눈으로 보면서 검사할 수 있습니다.  동작의 유효성을 검사하는 클라이언트 구현 방법의 예제는 [Client Validation](../../../../docs/framework/wcf/samples/client-validation.md)를 참조하세요.  
  
## 응용 프로그램 구성 파일 보호  
 서비스의 응용 프로그램 구성 파일은 메타데이터 게시 방법과 게시 여부를 제어할 수 있습니다.  적절한 ACL로 응용 프로그램 구성 파일을 보호하여 공격자가 이러한 설정을 수정할 수 없도록 하는 것이 좋습니다.  
  
## 참고 항목  
 [방법: 메타데이터 끝점 보안 설정](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)   
 [보안](../../../../docs/framework/wcf/feature-details/security.md)