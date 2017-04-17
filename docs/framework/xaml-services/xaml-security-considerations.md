---
title: "XAML Security Considerations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "security [XAML Services], .NET XAML services"
  - "XAML security [XAML Services]"
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# XAML Security Considerations
이 항목에서는 XAML 및 .NET Framework XAML 서비스 API를 사용할 때 응용 프로그램의 보안에 대한 최선의 구현 방법에 대해 설명합니다.  
  
## 응용 프로그램의 신뢰할 수 없는 XAML  
 가장 일반적인 측면에서 보면 신뢰할 수 없는 XAML은 응용 프로그램에서 특별히 포함하거나 내보내지 않은 임의의 XAML 소스입니다.  
  
 신뢰할 수 있는 서명된 어셈블리 내의 `resx` 형식 리소스로 컴파일 또는 저장되는 XAML은 기본적으로 신뢰할 수 있습니다.  어셈블리를 전체적으로 신뢰할 수 있는 만큼 XAML을 신뢰할 수 있습니다.  대개의 경우 스트림 또는 다른 IO에서 로드한 XAML 소스인 느슨한 XAML의 신뢰 여부만 고려하면 됩니다.  느슨한 XAML은 배포 및 패키징 인프라가 있는 응용 프로그램 모델의 특정 구성 요소 또는 기능이 아닙니다.  그러나 어셈블리에서는 느슨한 XAML 로드를 수반하는 동작을 구현할 수도 있습니다.  
  
 신뢰할 수 없는 XAML의 경우 일반적으로 신뢰할 수 없는 코드의 경우와 동일하게 처리해야 합니다.  잠재적으로 신뢰할 수 없는 XAML이 신뢰할 수 있는 코드에 액세스하는 것을 방지하기 위해 샌드박스를 적용하거나 비유를 사용합니다.  
  
 기본적으로 XAML 기능은 개체를 생성하고 해당 속성을 설정할 수 있는 권한을 XAML에 제공합니다.  또한 이러한 기능에는 형식 변환기에 액세스하거나 응용 프로그램 도메인에서 어셈블리를 매핑 및 액세스하거나 태그 확장, `x:Code` 블록 등을 사용하는 것이 포함됩니다.  
  
 언어 수준 기능 외에도 XAML은 대부분의 기술에서 UI 정의에 사용됩니다.  신뢰할 수 없는 XAML을 로드하면 악의적인 스푸핑 UI가 로드될 수도 있습니다.  
  
## 판독기 및 작성기 간에 컨텍스트 공유  
 XAML 판독기 및 XAML 작성기에 대한 .NET Framework XAML 서비스 아키텍처에서는 대개 XAML 작성기에 대한 XAML 판독기 공유나 공유된 XAML 스키마 컨텍스트가 필요합니다.  XAML 노드 루프 논리를 기록하거나 사용자 지정 저장 경로를 제공할 경우 개체 또는 컨텍스트 공유가 필요할 수 있습니다.  신뢰할 수 있는 코드와 신뢰할 수 없는 코드 간에 XAML 판독기 인스턴스, 기본값이 아닌 XAML 스키마 컨텍스트 또는 XAML 판독기\/작성기 클래스에 대한 설정을 공유하면 안 됩니다.  
  
 CLR 기반 형식 지원에 대한 XAML 개체 쓰기를 포함하는 대부분의 시나리오 및 작업은 기본 XAML 스키마 컨텍스트만 사용할 수 있습니다.  기본 XAML 스키마 컨텍스트는 완전 신뢰를 손상시킬 수 있는 설정을 명시적으로 포함하지 않습니다.  따라서 신뢰할 수 있는 XAML 판독기\/작성기 구성 요소와 신뢰할 수 없는 XAML 판독기\/작성기 구성 요소 간에 컨텍스트를 공유하는 것이 안전합니다.  그러나 이렇게 할 경우 이러한 판독기 및 작성기를 별개의 <xref:System.AppDomain> 범위에 유지하면서 이 중 하나를 특히 부분 신뢰를 위해 사용\/샌드박스를 적용하는 것이 여전히 최선의 구현 방법입니다.  
  
## XAML 네임스페이스 및 어셈블리 신뢰  
 어셈블리에 대한 사용자 지정 XAML 네임스페이스 매핑을 XAML에서 해석하는 방법에 대한 비정규화된 기본 구문 및 정의에서는 응용 프로그램 도메인에 로드될 때 신뢰할 수 있는 어셈블리와 신뢰할 수 없는 어셈블리를 구별하지 않습니다.  따라서 신뢰할 수 없는 어셈블리가 신뢰할 수 있는 어셈블리의 원하는 XAML 네임스페이스 매핑을 스푸핑하고 XAML 소스의 선언된 개체 및 속성 정보를 캡처하는 것이 기술적으로 가능합니다.  이 상황을 방지해야 하는 보안 요구 사항이 있는 경우 다음 기술 중 하나를 사용하여 필요한 XAML 네임스페이스 매핑을 만들어야 합니다.  
  
-   응용 프로그램의 XAML에 의해 작성된 모든 XAML 네임스페이스 매핑에서 강력한 이름과 함께 정규화된 어셈블리 이름을 사용합니다.  
  
-   XAML 판독기 및 XAML 개체 작성기에 대한 특정 <xref:System.Xaml.XamlSchemaContext>를 생성하여 어셈블리 매핑을 고정된 참조 어셈블리 집합으로 제한합니다.  <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>를 참조하십시오.  
  
## XAML 형식 매핑 및 형식 시스템 액세스  
 XAML은 고유한 형식 시스템을 지원하며 이는 여러 측면에서 CLR이 기본 CLR 형식 시스템을 구현하는 방법과 유사합니다.  하지만 형식 정보에 기초하여 형식에 대한 신뢰를 결정하는 형식 인식의 특정 측면에서는 CLR 지원 형식의 형식 정보를 따라야 합니다.  이는 XAML 형식 시스템의 특정 보고 기능 중 일부가 가상 메서드로 열려 있어서 원래 .NET Framework XAML 서비스 구현에 의해 완전히 제어되지 않기 때문입니다.  이러한 확장성 지점은 XAML 형식 시스템이 확장 가능하기 때문에 존재하며, XAML 자체의 확장성 및 XAML의 가능한 대체 형식 매핑 전략을 기본 CLR 기반 구현 및 기본 XAML 스키마 컨텍스트와 조화시키기 위한 것입니다.  자세한 내용은 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember>의 여러 속성에 대한 구체적인 설명을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Xaml.Permissions.XamlAccessLevel>