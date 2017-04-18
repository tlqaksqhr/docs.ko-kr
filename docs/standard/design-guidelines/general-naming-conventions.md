---
title: "일반 명명 규칙 | Microsoft Docs"
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
  - "이름 [.NET Framework] 충돌"
  - "형식 이름 충돌"
  - "특정 언어 관련 형식 이름"
  - "명명 지침에 대 한 이름 [.NET Framework]"
  - "이름 [.NET Framework] 약어"
  - "약어 명명 지침"
  - "머리글자어 명명 지침"
  - "헝가리 식 표기법"
  - "이름 [.NET Framework] 형식 이름"
  - "이름 [.NET Framework] 머리 글자어는"
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# 일반 명명 규칙
이 섹션에서는 일반 명명 규칙 단어 선택와 관련 된 약어 및 머리글자어 및 권장 사항을 사용 하 여 언어별 이름을 사용 하지 않도록 하는 방법에 대 한 지침을 설명 합니다.  
  
## 단어 선택  
 **✓ 수행** 쉽게 읽을 수 있는 식별자 이름을 선택 합니다.  
  
 예를 들어 라는 속성이 `HorizontalAlignment` 는 영어\-보다 더 가독성이 `AlignmentHorizontal`합니다.  
  
 **✓ 수행** 간단 하 게 보다 가독성을 우선시 합니다.  
  
 속성 이름을 `CanScrollHorizontally` 보다 나은 `ScrollableX` \(x 축에는 모호한 참조\).  
  
 **X 하지 않으려면** 밑줄, 하이픈, 또는 기타 영숫자가 아닌 문자를 사용 합니다.  
  
 **X 하지 않으려면** 헝가리 식 표기법을 사용 합니다.  
  
 **X 방지** 널리의 키워드와 충돌 하는 식별자를 사용 하 여 프로그래밍 언어를 사용 합니다.  
  
 규칙 4의는 사양 CLS \(공용 언어\)에 따라 모든 호환 언어는 해당 언어의 키워드를 식별자로 사용 하는 명명 된 항목에 대 한 액세스를 허용 하는 메커니즘을 제공 해야 합니다. C\#의 경우, 예를 들어 사용 하는 @ 기호가 경우에서 이스케이프 메커니즘으로 합니다. 그러나 메서드를 사용 하는 이스케이프 시퀀스로 매개 변수가 없으면 1 보다 훨씬 더 어렵기 때문에 일반적인 키워드를 방지 하는 것은 여전히 있습니다.  
  
## 약어 및 머리글자어를 사용 하 여  
 **X 하지 않으려면** 약어 또는 축약 식별자 이름의 일부로 사용 합니다.  
  
 사용 예를 들어 `GetWindow` 대신 `GetWin`합니다.  
  
 **X 하지 않으려면** 널리 인정 하 고 필요한 경우에가 하는 경우에 하지 않은 머리글자어를 사용 합니다.  
  
## 언어별 이름을 사용 하지 않으면  
 **✓ 수행** 형식 이름에 대 한 언어별 키워드 보다는 특별 한 의미가 있는 이름을 사용 합니다.  
  
 예를 들어 `GetLength` 보다 더 나은 이름인 `GetInt`합니다.  
  
 **✓ 수행** 식별자 의미가 없는 해당 형식 이상의 경우에 드문 경우에서는 언어별 이름 대신 제네릭 CLR 형식 이름을 사용 합니다.  
  
 변환 하는 방법 예를 들어 <xref:System.Int64> 명명할 `ToInt64`, 이 아니라 `ToLong` \(때문에 <xref:System.Int64> 은 C\#에 대 한 CLR 이름\-특정 별칭 `long`\). 다음 표에서 CLR 형식 이름 \(뿐만 아니라 C\#, Visual Basic 및 c \+ \+에 대 한 해당 형식 이름\)을 사용 하 여 몇 가지 기본 데이터 형식을 표시 합니다.  
  
|C\#|Visual Basic|C\+\+|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**짧게**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**\_\_int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned \_\_int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Double**|**double**|**Double**|  
|**bool**|**부울**|**bool**|**부울**|  
|**char**|**Char**|**wchar\_t**|**Char**|  
|**string**|**문자열**|**문자열**|**문자열**|  
|**object**|**개체**|**개체**|**개체**|  
  
 **✓ 수행**  와 같은 일반 이름을 사용 하 여 `value` 또는 `item`, 형식 이름, 식별자 의미가 없는 및 매개 변수의 형식이 중요 하지 않은 경우 드문 경우에서를 반복 하는 대신 합니다.  
  
## 기존 Api의 새 버전 이름 지정  
 **✓ 수행** 기존 API의 새 버전을 만들 때 기존 API와 유사한 이름을 사용 합니다.  
  
 Api 간의 관계를 강조 표시할 수 있습니다.  
  
 **✓ 수행** 원하는 기존 API의 새 버전을 표시 하는 접두사도 보다는 접미사를 추가 합니다.  
  
 이 설명서를 검색할 때 검색 한 장의 주요 내용은 또는 Intellisense를 사용 하 여 합니다. 대부분의 브라우저와 Intellisense 알파벳 순서로 식별자를 표시 하기 때문에 이전 버전의 API 새로운 Api와 가까운 기준 구성 됩니다.  
  
 **✓ 고려** 접두사 또는 접미사를 추가 하지 않고 새로운, 하지만 의미 있는 식별자를 사용 하 여 합니다.  
  
 **✓ 수행** 특히 API의 기존 이름이 것이 좋습니다 \(예: 경우 업계 표준\)을 추가 하는 의미 있는 경우 접미사 \(또는 이름 변경\) 되지 않은 경우 적절 한 옵션에는 기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다.  
  
 **X 하지 않으려면** "예" \(또는 유사한\)를 사용 하 여 이전 버전의 동일한 API와 구분 식별자에 대 한 접미사입니다.  
  
 **✓ 수행** 32 비트 정수 하는 대신 64 비트 정수 \(long 정수\)에서 작동 하는 Api의 버전을 도입할 때 "64" 접미사를 사용 합니다. 기존 32 비트 API 있으면;이 방법을 사용 하면 64 비트 버전에 완전히 새로운 Api에 대 한 수행 되지 마십시오.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)