---
title: "일반 명명 규칙"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dde3adbb7640978829dea4b977ed14eec38a9077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="general-naming-conventions"></a>일반 명명 규칙
이 섹션에서는 일반 명명 규칙 단어 선택 관련 된 약어 및 머리글자어 및 권장 사항을 사용 하 여 언어별 이름을 사용 하지 않도록 하는 방법에 대 한 지침을 설명 합니다.  
  
## <a name="word-choice"></a>단어 선택  
 **✓ 않습니다** 쉽게 읽을 수 있는 식별자 이름을 선택 합니다.  
  
 예를 들어 라는 속성이 `HorizontalAlignment` 는 영어-읽기 쉬운 `AlignmentHorizontal`합니다.  
  
 **✓ 않습니다** 가독성 간결한 설명을 위해 보다 우선 합니다.  
  
 속성 이름 `CanScrollHorizontally` 더 좋은 것은 `ScrollableX` (x 축에는 그 보다 모호해 참조).  
  
 **X 하지 않으면** 밑줄, 하이픈 또는 기타 영숫자가 아닌 문자를 사용 합니다.  
  
 **X 하지 않으면** 헝가리 식 표기법을 사용 합니다.  
  
 **하지 말고 X** 널리의 키워드와 충돌 하는 식별자를 사용 하 여 프로그래밍 언어를 사용 합니다.  
  
 규칙 4의는 CLS 공용 언어 사양 ()에 따라 규정을 준수 하는 모든 언어는 해당 언어의 키워드를 식별자로 사용 하는 명명 된 항목에 액세스할 수 있는 메커니즘을 제공 해야 합니다. C#, 예를 들어, 사용 하는 @ 기호가 경우에서 이스케이프 메커니즘으로 합니다. 그러나 메서드를 사용 하는 이스케이프 시퀀스 없이 1 보다 훨씬 더 어렵기 때문에 일반적인 키워드를 방지 하는 여전히 합니다.  
  
## <a name="using-abbreviations-and-acronyms"></a>머리 글자어와 약어를 사용 하 여  
 **X 하지 않으면** 식별자 이름의 일부로 약어 또는 축약을 사용 합니다.  
  
 사용 예를 들어 `GetWindow` 대신 `GetWin`합니다.  
  
 **X 하지 않으면** 폭넓게 활용 되 고 필요한 경우에 있는 경우에 하지 않은 머리글자어를 사용 합니다.  
  
## <a name="avoiding-language-specific-names"></a>언어 관련 이름 방지  
 **✓ 않습니다** 형식 이름에 대 한 언어별 키워드 보다는 특별 한 의미가 있는 이름을 사용 합니다.  
  
 예를 들어 `GetLength` 보다 더 나은 이름인 `GetInt`합니다.  
  
 **✓ 않습니다** 드문 경우 식별자 의미가 없는 해당 형식 이상의 때의 언어 관련 이름 대신 일반 CLR 형식 이름을 사용 합니다.  
  
 예를 들어를 변환 하는 메서드 <xref:System.Int64> 명명할 `ToInt64`이 아니라 `ToLong` (때문에 <xref:System.Int64> C#에 대 한 CLR 이름이-특정 별칭 `long`). 다음 표에서 CLR 형식 이름 (뿐만 아니라 해당 하는 유형 이름을 C#, Visual Basic 및 c + +)를 사용 하 여 몇 가지 기본 데이터 형식을 표시 합니다.  
  
|C#|Visual Basic|C++|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Short**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**__int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Double**|**double**|**Double**|  
|**bool**|**Boolean**|**bool**|**Boolean**|  
|**char**|**Char**|**wchar_t**|**Char**|  
|**string**|**String**|**String**|**String**|  
|**object**|**개체**|**개체**|**개체**|  
  
 **✓ 않습니다** 와 같은 일반 이름을 사용 하 여 `value` 또는 `item`, 형식 이름 식별자 의미가 없는 및 매개 변수의 형식이 중요 하지 않은 경우 드문 경우에서를 반복할 필요 없이 합니다.  
  
## <a name="naming-new-versions-of-existing-apis"></a>새 버전 기존 Api의 이름 지정  
 **✓ 않습니다** 기존 API의 새 버전을 만들 때 기존 API와 유사한 이름을 사용 합니다.  
  
 이렇게 하면 Api 간의 관계를 강조 표시 합니다.  
  
 **✓ 않습니다** 선호 기존 API의 새 버전을 나타내는 접두사 보다는 접미사를 추가 합니다.  
  
 이 설명서를 검색할 때 검색 도움이 또는 Intellisense를 사용 하 여 합니다. 대부분의 브라우저와 Intellisense 식별자 사전순으로 표시 되므로 새로운 Api에 가까운 이전 버전의 API 구성할 수 됩니다.  
  
 **✓ 고려** 접두사 또는 접미사를 추가 하는 대신 새로운, 하지만 의미 있는 식별자를 사용 하 여 합니다.  
  
 **✓ 않습니다** 특히 API의 기존 이름이 경우 (즉,이 산업 표준) 쉽게 알아볼 수 있는 유일한 이름이 어떤 의미 있는 추가 하는 경우 접미사 (또는 이름을 변경) 되지 않은 경우 응용 프로그램에 기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다. ropriate 옵션입니다.  
  
 **X 하지 않으면** "Ex" (또는 유사한)를 사용 하 여 이전 버전의 동일한 API와 구분 식별자에 대 한 접미사입니다.  
  
 **✓ 않습니다** 32 비트 정수 대신 64 비트 정수 (long 정수)에서 작동 하는 Api의 버전을 도입할 때 "64" 접미사를 사용 합니다. 기존 32 비트 API 있으면;이 접근 해야 64 비트 버전을 사용 하 여 새 Api에 대 한 수행 하지 마십시오.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
