---
title: "네임 스페이스의 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "이름 [.NET Framework] 충돌"
  - "네임 스페이스 이름 [.NET Framework]"
  - "형식 이름 충돌"
  - "네임 스페이스 [.NET Framework] 이름"
  - "이름 [.NET Framework] 형식 이름"
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 네임 스페이스의 이름
으로 다른 명명 지침과 네임 스페이스의 이름을 지정할 때 목표 만들어지고 충분 한 명확성 즉시 네임 스페이스의 콘텐츠는 알고 일 수를 프레임 워크를 사용 하 여 프로그래머에 있습니다. 다음 템플릿 네임 스페이스 명명에 대 한 일반적인 규칙을 지정 합니다.  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 다음은 예입니다.  
  
 `Fabrikam.Math`   
 `Litware.Security`  
  
 **✓ 수행** 네임 스페이스 이름에는 동일한 이름의 다른 회사의 네임 스페이스를 방지 하기 위해 회사 이름 접두사입니다.  
  
 **✓ 수행** 네임 스페이스 이름의 두 번째 수준에서 안정적인 버전에 관계 없이 제품 이름을 사용 합니다.  
  
 **X 하지 않으려면** 단기에 끝나는 경향이 기업의 그룹 이름은 때문에 조직 계층 구조를 기반으로 네임 스페이스 계층 구조에서 이름에 대 한 사용 합니다. 관련된 기술의 그룹 주위 네임 스페이스의 계층 구조를 구성 합니다.  
  
 **✓ 수행** 작업량이 PascalCasing, 및 별도 네임 스페이스 구성 요소를 사용 하 여 \(예: `Microsoft.Office.PowerPoint`\). 브랜드에서 않던 대\/소문자를 사용 하는 경우 규칙 대\/소문자 기본 네임 스페이스에서에서 파생 하는 경우에 사용자 브랜드에 정의 된 대\/소문자를 따라야 합니다.  
  
 **✓ 고려** 적절 한 복수형 네임 스페이스 이름을 사용 합니다.  
  
 사용 예를 들어 `System.Collections` 대신 `System.Collection`합니다. 그러나 브랜드 이름 및 머리글자어이 규칙에 대 한 예외는 있습니다. 사용 예를 들어 `System.IO` 대신 `System.IOs`합니다.  
  
 **X 하지 않으려면** 해당 네임 스페이스의 네임 스페이스 및 형식에 대 한 동일한 이름을 사용 합니다.  
  
 예를 들어, 사용 하지 마십시오 `Debug` 네임 스페이스와 이름을 지정 하 고 다음 라는 클래스도 제공 `Debug` 동일한 네임 스페이스에 있습니다. 여러 컴파일러에서는 해당 형식을 정규화 되어야 합니다.  
  
### 네임 스페이스 및 형식 이름 충돌  
 **X 하지 않으려면** 와 같은 제네릭 형식 이름을 소개 `Element`, `Node`, `Log`, 및 `Message`합니다.  
  
 그러면 이름을 입력 하 게 될 시나리오에 공통 충돌 가능성이 매우 높습니다 있습니다. 제네릭 형식 이름을 정규화 해야 \(`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`\).  
  
 네임 스페이스의 다른 범주에 대 한 형식 이름 충돌을 방지 하는 것에 대 한 지침이 있습니다.  
  
-   **응용 프로그램 모델 네임 스페이스**  
  
     단일 응용 프로그램 모델에 속한 네임 스페이스는 종종 매우 함께 사용 하지만 다른 응용 프로그램 모델의 네임 스페이스로 사용 거의 되지 않기. 예를 들어는 <xref:System.Windows.Forms?displayProperty=fullName> 네임 스페이스와 함께 사용 되는 매우 드물게는 <xref:System.Web.UI?displayProperty=fullName> 네임 스페이스입니다. 다음은 잘 알려진 응용 프로그램 모델 네임 스페이스 그룹의 목록입니다.  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X 하지 않으려면** 단일 응용 프로그램 모델 내에서 네임 스페이스의 형식에 같은 이름을 지정 합니다.  
  
     예를 들어 이라는 형식을 추가 하지 마십시오 `Page` 에 <xref:System.Web.UI.Adapters?displayProperty=fullName> 네임 스페이스 때문에 <xref:System.Web.UI?displayProperty=fullName> 이라는 형식을 네임 스페이스에 이미 포함 되어 `Page`합니다.  
  
-   **인프라 네임 스페이스**  
  
     이 그룹에는 일반적인 응용 프로그램을 개발 하는 동안 거의 가져온 네임 스페이스 포함 되어 있습니다. 예를 들어 `.Design` 네임 스페이스는 프로그래밍 개발 도구 때 주로 사용 됩니다. 이러한 네임 스페이스의 형식과 충돌을 방지 중요 하지 않습니다.  
  
-   **핵심 네임 스페이스**  
  
     모든 핵심 네임 스페이스 포함 `System` 네임 스페이스를 응용 프로그램 모델의 네임 스페이스 및 인프라 네임 스페이스를 제외 합니다. 맺음 코어 네임 스페이스에 포함 `System`, 를`System.IO`, 를`System.Xml`, 를 및 `System.Net`합니다.  
  
     **X 하지 않으려면** 지정 합니다. 핵심 네임 스페이스의 형식과 충돌 하는 이름을 입력 합니다.  
  
     예를 들어, 사용 하지 마십시오 `Stream` 형식 이름으로 합니다. 와 충돌 하 게 <xref:System.IO.Stream?displayProperty=fullName>, 는, 형식이 매우 일반적으로 사용 합니다.  
  
-   **기술 네임 스페이스 그룹**  
  
     이 범주는 동일한 처음 두 개의 네임 스페이스 노드가 포함 된 모든 네임 스페이스를 포함 `(<Company>.<Technology>*`\), 예: `Microsoft.Build.Utilities` 및 `Microsoft.Build.Tasks`. 한 가지 기술에 속하는 형식 서로 충돌 하지 않아야 합니다.  
  
     **X 하지 않으려면** 단일 기술의 다른 형식과 충돌 하는 형식 이름을 할당 합니다.  
  
     **X 하지 않으려면** \(있는 경우 제외 기술은 응용 프로그램 모델에 사용할 수 없습니다\) 기술 네임 스페이스의 형식와 응용 프로그램 모델 네임 스페이스 간의 형식 이름 충돌을 소개 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)