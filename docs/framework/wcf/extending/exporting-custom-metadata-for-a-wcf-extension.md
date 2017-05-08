---
title: "WCF 확장에 대한 사용자 지정 메타데이터 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 53c93882-f8ba-4192-965b-787b5e3f09c0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# WCF 확장에 대한 사용자 지정 메타데이터 내보내기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 메타데이터 내보내기는 서비스 끝점을 설명하여 클라이언트에서 서비스 사용 방법을 이해할 수 있도록 병렬의 표준화된 표현으로 나타내는 프로세스입니다.사용자 지정 메타데이터는 시스템에서 제공한 메타데이터 내보내기에서 내보낼 수 없는 XML 요소로 구성됩니다.일반적으로 여기에는 사용자 정의 동작 및 바인딩 요소에 대한 사용자 지정 WSDL 요소를 비롯하여 바인딩 및 계약의 기능과 요구 사항에 대한 정책 어설션이 포함됩니다.  
  
 이 단원에서는 사용자 지정 WSDL 또는 정책 어설션 내보내기에 대해 설명하지만 내보내기 프로세스 자체를 중점적으로 설명하지는 않습니다.메타데이터가 사용자 지정이든 시스템에서 구성되었든 관계없이 메타데이터를 내보내고 가져오는 형식을 사용하는 방법에 대한 자세한 내용은 [메타데이터 내보내기 및 가져오기](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)를 참조하십시오.  
  
## 개요  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName>를 사용하여 메타데이터를 게시할 경우 <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=fullName>을 검사하고 시스템에 제공된 특성과 바인딩을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원 가능한 모든 계약 및 바인딩에 대한 XSD 및 WSDL\(정책 어설션 포함\)을 생성합니다.그러나 메타데이터를 올바르게 내보내려면 먼저 사용자 지정 동작 특성 또는 바인딩 요소가 지원되어야 합니다.  
  
 이 단원의 내용은 다음과 같습니다.  
  
1.  WSDL을 게시하기 전에 WSDL 생성 데이터를 공개하는 <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=fullName> 인터페이스를 구현하고 사용하는 방법  
  
2.  WSDL 데이터에서 정책 어설션을 내보내기 전에 정책 데이터를 공개하는 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> 인터페이스를 구현하고 사용하는 방법  
  
 사용자 지정 WSDL 및 정책 어설션을 가져오는 방법에 대한 자세한 내용은 [WCF 확장에 대한 사용자 지정 메타데이터 가져오기](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)를 참조하십시오.  
  
## 사용자 지정 WSDL 요소 내보내기  
 작업 동작, 계약 동작, 끝점 동작 또는 바인딩 요소\(각각 <xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior>, <xref:System.ServiceModel.Description.IEndpointBehavior>, <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>\)에서 <xref:System.ServiceModel.Description.IWsdlExportExtension>을 구현하고, 내보낼 서비스에 대한 설명에 동작 또는 바인딩 요소를 삽입합니다.동작 삽입에 대한 자세한 내용은 [동작을 사용하여 런타임 구성 및 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)을 참조하십시오.각 끝점에 대해 <xref:System.ServiceModel.Description.IWsdlExportExtension>이 호출되고 각 끝점에서 계약을 먼저 내보냅니다\(아직 내보내지 않은 경우\).필요에 따라 내보내기 프로세스에 참여할 수 있습니다.  
  
-   <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> 메서드에서 내보낸 메타데이터를 수정하려면 <xref:System.ServiceModel.Description.WsdlContractConversionContext>를 사용합니다.  
  
-   <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> 메서드에서 끝점에 대해 내보낸 메타데이터를 수정하려면 <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>를 사용합니다.  
  
 <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> 메서드는 내보낼 <xref:System.ServiceModel.Description.ContractDescription?displayProperty=fullName> 인스턴스 내의 모든 <xref:System.ServiceModel.Description.IWsdlExportExtension> 구현에 대해 호출됩니다.<xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> 메서드는 내보낼 <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=fullName> 인스턴스가 있는 모든 <xref:System.ServiceModel.Description.IWsdlExportExtension> 구현에 대해 호출됩니다.  
  
 자세한 내용은 [방법: 사용자 지정 WSDL 내보내기](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md) 및 예제 [사용자 지정 WSDL 게시](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)을\(를\) 참조하십시오.  
  
## 사용자 지정 정책 어설션 내보내기  
 <xref:System.ServiceModel.Channels.BindingElement>에서 <xref:System.ServiceModel.Description.IPolicyExportExtension>을 구현하고 바인딩에 바인딩 요소를 추가하여 바인딩 지원 및 계약 기능에 대한 사용자 지정 정책 어설션을 WSDL로 작성합니다.<xref:System.ServiceModel.Description.IPolicyExportExtension>은 바인딩에서 구현된 바인딩 요소를 내보낼 때 호출되어 <xref:System.ServiceModel.Description.PolicyConversionContext>를 <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> 메서드에 전달합니다.<xref:System.ServiceModel.Description.PolicyConversionContext> 인스턴스의 메서드를 사용하여 메시지, 작업 또는 끝점 주체에서 WSDL 바인딩에 연결된 정책 어설션에 추가할 수 있습니다.  
  
 자세한 내용은 [방법: 사용자 지정 정책 어설션 내보내기](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md)를 참조하십시오.  
  
## 참고 항목  
 [방법: 사용자 지정 WSDL 내보내기](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)   
 [방법: 사용자 지정 정책 어설션 내보내기](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md)   
 [WCF 확장에 대한 사용자 지정 메타데이터 가져오기](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)