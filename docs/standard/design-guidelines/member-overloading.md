---
title: "멤버 오버 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "기본 인수"
  - "오버 로드 된 멤버 [.NET Framework]"
  - "오버 로드 멤버 디자인 지침 [.NET Framework]"
  - "멤버 오버로드"
  - "서명, 멤버"
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 멤버 오버 로드
멤버 오버 로드을 같은 형식의 매개 변수 형식이 나 개수 에서만 차이가 있지만 이름이 같은 둘 이상의 멤버를 만드는 것을 의미 합니다. 예를 들어, 다음에에서는 `WriteLine` 메서드가 오버 로드 됩니다.  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
  
```  
  
 메서드, 생성자 및 인덱싱된 속성 매개 변수를 가질 수 있으므로 멤버를 오버 로드할 수 있습니다.  
  
 오버 로드 사용 편의성, 생산성 및 재사용 가능한 라이브러리의 가독성을 향상 시키기 위한 가장 중요 한 기술 중 하나입니다. 매개 변수 개수에 오버 로드 하는 메서드와 생성자의 간단한 버전을 제공할 수 있습니다. 매개 변수 형식에 오버 로드 다양 한 종류의 선택한 집합에 동일한 작업을 수행 하는 멤버에 대 한 동일한 멤버 이름을 사용할 수 있습니다.  
  
 **✓ 수행** 짧은 오버 로드에 의해 사용 되는 기본값을 나타내기 위해 설명적인 매개 변수 이름을 사용 하려고 합니다.  
  
 **X 방지** 임의의 여러 오버 로드에 매개 변수 이름입니다. 하나의 오버 로드에 대 한 매개 변수 같은 다른 오버 로드의 매개 변수 입력을 나타내는 경우 이름이 같은 매개 변수가 있어야 합니다.  
  
 **X 방지** 오버 로드 된 멤버의 매개 변수 순서에 일관 되지 않은 것입니다. 같은 이름의 매개 변수는 모든 오버 로드에 동일한 위치에 표시 됩니다.  
  
 **✓ 수행** \(확장성이 필요한 경우\) 하는 경우 가상 가장 긴 오버 로드를 확인 합니다. 짧은 오버 로드는 긴 오버 로드를 통해 호출 해야 합니다.  
  
 **X 하지 않으려면** 사용 `ref` 또는 `out` 멤버를 오버 로드에 대 한 한정자입니다.  
  
 일부 언어는 다음과 같은 오버 로드에 대 한 호출을 확인할 수 없습니다. 또한 이러한 오버 로드 일반적으로 의미 체계가 완전히 다릅니다 이며 아마도 되어서는 안 오버 로드가 있지만 별도 두 가지 방법 대신 합니다.  
  
 **X 하지 않으려면** 이와 유사한 종류와 같은 위치에 대 한 매개 변수를 사용 하지만 구문이 다른 오버 로드를 갖고 있습니다.  
  
 **✓ 수행**  허용 `null` 선택적 인수를 전달할 수 있습니다.  
  
 **✓ 수행** 멤버 기본 인수를 사용 하 여 멤버를 정의 하기 보다는 오버 로드를 사용 합니다.  
  
 기본 인수는 CLS 규격 없습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)