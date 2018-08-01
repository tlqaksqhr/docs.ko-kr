---
title: 리소스 이름 지정
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7cfda4e6a340d040de02903b9b64f0339751c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571188"
---
# <a name="naming-resources"></a>리소스 이름 지정
큐브인 것 처럼 속성에 특정 개체를 통해 지역화 가능한 리소스를 참조할 수 있습니다, 때문에 리소스에 대 한 이름 지정 지침 속성 지침 비슷합니다.  
  
 **✓ DO** PascalCasing 리소스 키에 사용 합니다.  
  
 **✓ DO** 설명 하는 대신 짧은 식별자를 제공 합니다.  
  
 **X DO NOT** 주 CLR 언어의 언어 관련 키워드를 사용 합니다.  
  
 **✓ DO** 영숫자 문자와 밑줄 리소스 이름 지정 시에 사용 합니다.  
  
 **✓ DO** 예외 메시지 리소스에 대 한 다음과 같은 명명 규칙을 사용 합니다.  
  
 예외 형식 이름과 예외 짧은 식별자 리소스 식별자 여야 합니다.  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
