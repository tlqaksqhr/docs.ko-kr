---
title: XAML 보안 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: ef47e7e370082a2050406710edcb62d0967df8ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562364"
---
# <a name="xaml-security-considerations"></a>XAML 보안 고려 사항
이 항목에서는 XAML 및.NET Framework XAML 서비스 API를 사용 하는 경우 응용 프로그램의 보안에 대 한 모범 사례를 설명 합니다.  
  
## <a name="untrusted-xaml-in-applications"></a>응용 프로그램에서 신뢰할 수 없는 XAML  
 가장 일반적인 의미에서 신뢰할 수 없는 XAML은 응용 프로그램 포함 또는 생성 되지 않은 모든 XAML 소스입니다.  
  
 컴파일 또는으로 저장 하는 XAML을 `resx`-신뢰할 수 있는 서명된 된 어셈블리 내의 형식 리소스를 기본적으로 신뢰할 수 없습니다. 어셈블리를 전체적으로 신뢰할 수 만큼 XAML 신뢰할 수 있습니다. 대부분의 경우에서 관심이 스트림 또는 기타 I/O에서 로드 하는 XAML 소스는 느슨한 XAML의 신뢰 측면에. 느슨한 XAML는 특정 구성 요소 또는 응용 프로그램 모델을 배포 및 패키징 인프라의 기능 않습니다. 그러나 어셈블리는 느슨한 XAML을 로드 하는 동작을 구현할 수 있습니다.  
  
 신뢰할 수 없는 XAML에 대 한 이지만 간주 해야 일반적으로 동일한을 마치 신뢰할 수 없는 코드입니다. 샌드박스를 적용 하거나 다른 기능을 사용 하 여 신뢰할 수 없는 XAML 신뢰할 수 있는 코드에 액세스 하지 않도록 설정 합니다.  
  
 XAML 개체를 생성 하 고 해당 속성을 설정 하는 권한을 부여 하는 XAML 기능의 특성입니다. 이러한 기능에도 형식 변환기, 매핑 및 태그 확장을 사용 하 여 응용 프로그램 도메인에서 어셈블리를 액세스 하거나 액세스 하는 `x:Code` 블록 및 등입니다.  
  
 해당 언어 수준 기능 외에 XAML에서 많은 기술 UI 정의에 사용 됩니다. 신뢰할 수 없는 xaml 악의적인 스푸핑 UI를 로드 될 수도 있습니다.  
  
## <a name="sharing-context-between-readers-and-writers"></a>판독기 및 작성기 간에 컨텍스트를 공유합니다.  
 XAML 판독기 및 XAML 작성기에 대 한.NET Framework XAML 서비스 아키텍처 종종 공유 해야 하는 XAML 판독기는 XAML 작성기 또는 XAML 스키마 컨텍스트를 공유 합니다. XAML 노드 루프 논리를 작성 하는 또는 경로 저장 하는 사용자 지정을 제공 하는 경우 개체 또는 컨텍스트를 공유 해야 할 수 있습니다. XAML 판독기 인스턴스, 기본이 아닌 XAML 스키마 컨텍스트 또는 신뢰할 수 있는 항목과 신뢰할 수 없는 코드 사이의 XAML 판독기/작성기 클래스에 대 한 설정을 공유 하지 해야 합니다.  
  
 대부분의 시나리오 및 XAML 개체는 CLR 기반 형식 지원에 대 한 쓰기와 관련 된 작업에는 기본 XAML 스키마 컨텍스트를 사용할 것 수입니다. 기본 XAML 스키마 컨텍스트 완전 신뢰를 손상 시킬 수 있는 설정이 명시적으로 포함 되지 않습니다. 따라서 신뢰할 수 있는 항목과 신뢰할 수 없는 XAML 판독기/기록기 구성 요소 간에 컨텍스트를 공유 하 안전 합니다. 그러나이 작업을 수행 하는 경우이 여전히 별도의 이러한 판독기와 작성기를 유지 하는 것이 좋습니다 <xref:System.AppDomain> 특히/샌드박스를 적용 부분 신뢰에 대 한 그 중 하나가 지정 된 범위입니다.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>XAML 네임 스페이스 및 어셈블리 신뢰  
 기본 정규화 되지 않은 구문 및 XAML에서 어셈블리에는 사용자 지정 XAML 네임 스페이스 매핑을 해석 하는 방법에 대 한 정의로 응용 프로그램 도메인에 로드 된 신뢰할 수 있는 항목과 신뢰할 수 없는 어셈블리를 구분 하지 않습니다. 따라서는 신뢰할 수 있는 어셈블리의 의도 된 XAML 네임 스페이스 매핑을 스푸핑 및 XAML 소스의 선언 된 개체 및 속성 정보를 캡처하기 위해 신뢰할 수 없는 어셈블리에 대 한 기술적으로 가능 합니다. 이 상황을 방지 하려면 보안 요구 사항을 설정한 경우 의도 한 XAML 네임 스페이스 매핑을 만들어야 다음 방법 중 하나를 사용 하 여:  
  
-   응용 프로그램의 XAML 수행한 모든 XAML 네임 스페이스 매핑에 대 한 강력한 이름으로 정규화 된 어셈블리 이름을 사용 합니다.  
  
-   어셈블리의 참조 어셈블리가 고정된 된 집합으로 특정 구성 하 여 매핑을 제한 <xref:System.Xaml.XamlSchemaContext> XAML 판독기 및 XAML 개체 작성기입니다. <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>을 참조하세요.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>XAML 형식 매핑 및 형식 시스템 액세스  
 XAML은 CLR 기본 CLR 형식 시스템을 구현 하는 방법의 피어 여러 가지 방법으로 자체 형식 시스템을 지원 합니다. 그러나 특정 측면의 형식 정보에 따라 형식에 대 한 신뢰 결정을 내려야 할 위치 형식 인식의 지원 형식을 CLR 형식 정보를 연기 해야 있습니다. 이 XAML 형식 시스템의 특정 기능 중 일부 가상 메서드로 열린 채로 남아 있는 고 없기 때문에 따라서 완전히 원래.NET Framework XAML 서비스 구현에서 제어 합니다. 이러한 확장 지점을 XAML 형식 시스템은 해당 가능한 대체 형식 매핑 전략과 기본 CLR 기반 구현 및 기본 XAML 스키마 컨텍스트 및 XAML 자체의 확장성에 맞게 확장 가능 하기 때문에 존재 합니다. 자세한 내용은 특정 정보를 여러의 속성에 참조 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xaml.Permissions.XamlAccessLevel>
