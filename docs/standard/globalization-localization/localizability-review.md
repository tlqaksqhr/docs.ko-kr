---
title: "지역화 가능성 검토 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "지역화 대비 응용 프로그램, 지역화 가능성"
  - "응용 프로그램 개발[.NET Framework], 지역화"
  - "지역화 가능성[.NET Framework]"
  - "국가별 응용 프로그램[.NET Framework], 지역화 가능성"
  - "전역화[.NET Framework], 지역화 가능성"
  - "문화권, 지역화 가능성"
  - "지역화[.NET Framework], 지역화 가능성"
  - "전역 응용 프로그램, 지역화 가능성"
  - "리소스 지역화"
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 지역화 가능성 검토
지역화 가능성 검토는 지역화 대비 응용 프로그램 개발의 중간 단계입니다.  전역화 된 응용 프로그램이 지역화 될 준비가 되고 특별한 처리를 필요로 하는 사용자 인터페이스의 모든 측면 또는 모든 코드를 확인 합니다.  이 단계는 또한 지역화 과정이 응용 프로그램에 기능적 결함이 발생되지 않게 소개합니다  지역화 가능성 검토에 의해 발생한 모든 문제를 해결 하는 경우, 응용 프로그램은 지역화 될 준비가 됩니다.  지역화 가능성 검토가 철저하다면, 지역화 과정 동안 소스 코드를 수정할 필요가 없습니다.  
  
 지역화 가능성 검토는 다음 세 가지 검사로 이루어져 있습니다.  
  
-   [세계화 권장 사항이 구현되었습니까?](#global)  
  
-   [문화권 구분 기능이 올바르게 처리되었습니까?](#culture)  
  
-   [국가별 데이터를 사용하여 응용 프로그램을 테스트 했습니까?](#test)  
  
<a name="global"></a>   
## 전역화 권장 사항 구현  
 지역화를 염두에 두고 응용 프로그램을 디자인하고 개발한 경우, [전역화](../../../docs/standard/globalization-localization/globalization.md) 에서 설명 된 권장 사항을 따른 경우, 지역화 가능성 검토는 주로 품질 보증 단계일 것입니다.  그렇지 않으면, 이 단계에서 [globalization](../../../docs/standard/globalization-localization/globalization.md) 를 위한 권장 사항을 검토하고 구현하고, 지역화를 방해하는 소스 코드의 오류를 수정 합니다.  
  
<a name="culture"></a>   
## 문화권 구분 기능 처리  
 .NET Framework는 다양한 문화권에서 광범위 하게 변화하는 영역에서 프로그래밍 방식을 지원 하지 않습니다.  대부분의 경우, 다음과 같은 기능 영역을 처리 하기 위해 사용자 지정 코드를 작성할 수 있습니다.  
  
-   주소  
  
-   전화 번호.  
  
-   용지 크기.  
  
-   길이, 무게, 영역, 볼륨 및 온도에 사용 되는 측정 단위.  .NET Framework가 측정 단위 간의 변환에 대해 기본 제공을 지원하지 않지만, <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=fullName> 속성을 다음 예제와 같이 특정 국가 또는 지역에서 미터법을 사용 하는지 여부를 확인 합니다.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## 응용 프로그램 테스트  
 응용 프로그램을 지역화 하기 전에, 운영 체제의 국가별 버전에서 국가별 데이터를 사용하여 테스트 해야 합니다.  대부분의 사용자 인터페이스는 이 시점에서 지역화 되지 않지만, 다음과 같은 문제를 발견할 수 있습니다.  
  
-   운영 체제 버전에서 올바르게 역직렬화 되지 않은 데이터를 직렬화합니다.  
  
-   현재 문화권의 규칙에 반영 되지 않는 숫자 데이터입니다.  예를 들어, 숫자가 정확 하지 않은 그룹 구분 기호, 소수 구분 기호 또는 통화 기호를 사용하여 표시 될 수 있습니다.  
  
-   현재 문화권의 규칙에 반영 되지 않는 날짜 및 시간 데이터입니다.  예를 들어, 달과 날짜를 나타내는 숫자를 잘못된 순서로 나타날 수 있습니다, 날짜 구분 기호가 올바르지 않을 수 있거나 영역 시간대 정보가 잘못 될 수 있습니다.  
  
-   응용 프로그램을 위한 기본 culture를 확인 하지 못했기 때문에 찾을 수 없는 리소스입니다.  
  
-   특정 문화권에 대해 특별한 순서 대로 표시 되는 문자열입니다.  
  
-   문자열 비교 또는 예기치 않은 결과를 반환 하는 비교입니다.  
  
 응용 프로그램, 올바르게 처리된 문화에 민감한 기능, 테스트 동안 발생한 지역화 이슈의 확인과 호출을 개발할 때 세계화 추천을 따른 경우, 다음 단계인 [지역화](../../../docs/standard/globalization-localization/localization.md)로 진행할 수 있습니다.  
  
## 참고 항목  
 [전역화 및 지역화](../../../docs/standard/globalization-localization/index.md)   
 [지역화](../../../docs/standard/globalization-localization/localization.md)   
 [전역화](../../../docs/standard/globalization-localization/globalization.md)   
 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)