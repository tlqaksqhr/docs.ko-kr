---
title: "계약 및 서비스에서 오류 지정 및 처리 | Microsoft Docs"
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
  - "오류 처리 [WCF]"
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# 계약 및 서비스에서 오류 지정 및 처리
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램은 관리되는 예외 개체를 SOAP 오류 개체에 매핑하고 SOAP 오류 개체를 관리되는 예외 개체에 매핑하여 오류 상황을 처리합니다.이 단원의 항목에서는 사용자 지정 SOAP 오류와 같은 오류 조건을 노출하도록 계약을 디자인하는 방법, 이러한 오류를 서비스 구현의 일부로 반환하는 방법 및 클라이언트가 이러한 오류를 catch하는 방법에 대해 설명합니다.  
  
## 오류 처리 개요  
 관리되는 모든 응용 프로그램에서 처리 오류는 <xref:System.Exception> 개체로 표시됩니다.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램 같은 SOAP 기반 응용 프로그램의 경우 서비스 메서드는 SOAP 오류 메시지를 사용하여 처리 오류 정보와 통신합니다.SOAP 오류는 서비스 작업의 메타데이터에 포함된 메시지 유형이므로 클라이언트가 작업을 더욱 견고하게 만들거나 대화형으로 만드는 데 사용할 수 있는 오류 계약을 만듭니다.또한 SOAP 오류가 클라이언트에 XML 형식으로 표시되기 때문에 SOAP 플랫폼의 클라이언트가 사용할 수 있는 상호 운용성이 높은 형식의 시스템으로서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램으로의 연결이 쉬워집니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램은 두 가지 유형의 오류 시스템 모두에서 실행되기 때문에 클라이언트로 보내진 관리되는 예외 정보를 예외에서 서비스의 SOAP 오류로 변환하고, 보내며, SOAP 오류에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트의 오류 예외로 변환해야 합니다.또한 이중 클라이언트의 경우 클라이언트 계약에서 SOAP 오류를 서비스로 다시 보낼 수 있습니다.이러한 경우 기본 서비스 예외 동작을 사용하거나, 오류 메시지에 예외 매핑 여부 및 방법을 명시적으로 제어할 수 있습니다.  
  
 두 가지 유형의 SOAP 오류를 *선언된* 및 *선언되지 않은* 상태로 보낼 수 있습니다.선언된 SOAP 오류는 작업에 사용자 지정 SOAP 오류 유형을 지정하는 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName> 특성이 있는 오류입니다.*선언되지 않은* SOAP 오류는 작업 계약에 지정되지 않은 오류입니다.  
  
 서비스 작업에서 <xref:System.ServiceModel.FaultContractAttribute> 특성을 사용하여 클라이언트가 정상적인 작업 과정에서 받을 수 있는 모든 SOAP 오류를 공식적으로 지정하여 해당 오류를 선언하는 것이 좋습니다.또한 클라이언트가 알아야 하는 정보만 SOAP 오류에 반환하여 정보 공개를 최소화하는 것이 좋습니다.  
  
 일반적으로 서비스 및 이중 클라이언트는 다음 단계를 수행하여 오류 처리를 해당 응용 프로그램에 통합합니다.  
  
-   예외 조건을 사용자 지정 SOAP 오류에 매핑합니다.  
  
-   클라이언트 및 서비스가 SOAP 오류를 예외로 보내고 받습니다.  
  
 또한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 및 서비스는 디버깅을 위해 선언되지 않은 SOAP 오류를 사용하고 기본 오류 동작을 확장할 수 있습니다.다음 단원에서는 이러한 작업 및 개념에 대해 설명합니다.  
  
## SOAP 오류에 예외 매핑  
 오류 조건을 처리하는 작업을 만들기 위한 첫 번째 단계는 클라이언트 응용 프로그램이 오류에 대한 정보를 받아야 하는 조건을 결정하는 것입니다.일부 작업에는 해당 기능 관련 오류 조건이 포함되어 있습니다.예를 들어 `PurchaseOrder` 작업에서는 더 이상 구매 주문을 시작하는 것이 허용되지 않는 고객에게 특정 정보가 반환될 수 있습니다.다른 경우에는 `Calculator` 서비스와 같이 매우 일반적인 `MathFault` SOAP 오류가 전체 서비스에 대한 모든 오류 조건을 설명할 수 있습니다.서비스의 클라이언트가 오류 조건을 식별하면 사용자 지정 SOAP 오류를 생성할 수 있으며 해당 오류 조건이 발생할 때 사용자 지정 SOAP 오류를 반환하도록 작업을 표시할 수 있습니다.  
  
 서비스 또는 클라이언트를 개발하는 이 단계[!INCLUDE[crabout](../../../includes/crabout-md.md)][오류 정의 및 지정](../../../docs/framework/wcf/defining-and-specifying-faults.md)을 참조하십시오.  
  
## 클라이언트 및 서비스가 SOAP 오류를 예외로 처리  
 작업 오류 조건 식별, 사용자 지정 SOAP 오류 정의 및 이러한 오류를 반환하는 것으로 해당 작업을 표시하는 것은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램에서 오류를 처리하기 위한 첫 번째 단계입니다.다음 단계는 이러한 오류를 보내고 받는 것을 제대로 구현하는 것입니다.일반적으로 서비스는 클라이언트 응용 프로그램에게 오류 조건에 대한 정보를 알리기 위해 오류를 보내지만 이중 클라이언트도 SOAP 오류를 서비스에 보낼 수 있습니다.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [오류 보내기 및 받기](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## 선언되지 않은 SOAP 오류 및 디버깅  
 선언된 SOAP 오류는 강력하고 상호 운용 가능한 분산 응용 프로그램을 빌드하는 데 특히 유용합니다.그러나 일부 경우에서는 서비스 또는 이중 클라이언트가 해당 작업에 대해 WSDL\(웹 서비스 기술 언어\)에서 언급되지 않은 오류인 선언되지 않은 SOAP 오류를 보내는 데 유용합니다.예를 들어 서비스를 개발할 때 클라이언트에게 정보를 다시 보내기 위해 디버깅에 유용하지만 예기치 않은 상황이 발생할 수 있습니다.또한 <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> 속성 또는 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> 속성을 `true`로 설정하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트가 내부 서비스 작업 예외에 대한 정보를 가져올 수 있습니다.개별 오류를 보내고 디버깅 동작 속성을 설정하는 작업에 대해서는 [오류 보내기 및 받기](../../../docs/framework/wcf/sending-and-receiving-faults.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  관리되는 예외는 내부 응용 프로그램 정보를 노출할 수 있으므로 <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> 또는 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>를 `true`로 설정하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트에서는 개인적으로 식별할 수 있는 정보나 기타 중요한 정보를 비롯하여 내부 서비스 작업 예외에 대한 정보를 얻을 수 있습니다.  
>   
>  그러므로 임시로 서비스 응용 프로그램을 디버깅하려는 경우 <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> 또는 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>를 `true`로 설정하는 것이 유일한 좋은 방법입니다.또한 이 방법으로 처리되지 않은 관리되는 예외를 반환하는 메서드의 WSDL에는 <xref:System.ServiceModel.ExceptionDetail> 형식의 <xref:System.ServiceModel.FaultException%601>에 대한 계약이 포함되지 않습니다.디버깅 정보를 제대로 얻으려면 클라이언트는 <xref:System.ServiceModel.FaultException?displayProperty=fullName> 개체로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트에 반환되는 알 수 없는 SOAP 오류의 가능성을 예상해야 합니다.  
  
## IErrorHandler를 사용하여 오류 처리 사용자 지정  
 응용 프로그램 수준 예외가 발생하는 경우 클라이언트에 대한 응답 메시지를 사용자 지정하거나 응답 메시지를 반환한 후 일부 사용자 지정 처리 작업을 수행하기 위한 특수 요구 사항이 있는 경우 <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=fullName> 인터페이스를 구현합니다.  
  
## 오류 Serialization 문제  
 오류 계약을 deserialize할 때 WCF에서는 먼저 SOAP 메시지의 오류 계약 이름과 일치하는 오류 계약 형식을 찾으려고 시도합니다.정확히 일치하는 것을 찾을 수 없으면 알파벳 순서로 정렬된 사용 가능한 오류 계약 목록에서 호환되는 형식을 검색합니다.두 오류 계약이 호환되는 형식인 경우\(예: 한 계약이 다른 계약의 서브클래스인 경우\) 잘못된 형식이 오류를 deserialize하는 데 사용될 수 있습니다.이 문제는 오류 계약이 이름, 네임스페이스 및 동작을 지정하지 않은 경우에만 발생합니다.이 문제가 발생하지 않도록 하려면 항상 이름, 네임스페이스 및 동작 특성을 지정하여 오류 계약을 정규화합니다.또한 공유 기본 클래스에서 파생되는 많은 관련 오류 계약을 정의한 경우 `[DataMember(IsRequired=true)]`를 사용하여 모든 새 멤버를 표시해야 합니다.이 `IsRequired` 특성에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataMemberAttribute>를 참조하십시오.이렇게 하면 기본 클래스가 호환되는 형식이 될 수 없으며 오류가 올바른 파생 형식으로 deserialize됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.FaultException>   
 <xref:System.ServiceModel.FaultContractAttribute>   
 <xref:System.ServiceModel.FaultException>   
 <xref:System.Xml.Serialization.XmlSerializer>   
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>   
 <xref:System.ServiceModel.FaultContractAttribute>   
 <xref:System.ServiceModel.CommunicationException>   
 <xref:System.ServiceModel.FaultContractAttribute.Action%2A>   
 <xref:System.ServiceModel.FaultException.Code%2A>   
 <xref:System.ServiceModel.FaultException.Reason%2A>   
 <xref:System.ServiceModel.FaultCode.SubCode%2A>   
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>   
 [오류 정의 및 지정](../../../docs/framework/wcf/defining-and-specifying-faults.md)