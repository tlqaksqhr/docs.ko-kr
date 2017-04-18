---
title: "문화권을 구분하지 않는 문자열 작업 | Microsoft Docs"
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
  - "대/소문자 구분 비교"
  - "culture, 문화권 비구분 문자열 연산"
  - "문화권 비구분 문자열 연산"
  - "문화권 구분 문자열 연산"
  - "전역화[.NET Framework], 문화권 비구분 문자열 연산"
  - "지역화[.NET Framework], 문화권 비구분 문자열 연산"
  - "문자열[.NET Framework], 문화권 비구분 문자열 연산"
  - "지역화 대비 응용 프로그램, 문화권 비구분 문자열 연산"
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 문화권을 구분하지 않는 문자열 작업
문화권 구분 문자열 작업은 문화권별로 사용자에게 결과를 표시하도록 디자인된 응용 프로그램을 만드는 경우에 유용할 수 있습니다.  기본적으로 문화권 구분 메서드는 사용할 문화권을 현재 스레드의 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 속성에서 가져옵니다.  
  
 문화권 구분 문자열 작업이 항상 필요한 것은 아닙니다.  결과가 문화권의 영향을 받지 않아야 하는 경우 문화권 구분 작업을 사용하면, 사용자 지정 연결과 정렬 규칙을 포함한 지정된 문화권에서의 응용 프로그램 코드가 제대로 실행되지 않을 수 있습니다.  예제는 [문자열 사용에 대한 유용한 정보](../../../docs/standard/base-types/best-practices-strings.md) 문서에서 "현재 문화권을 이용하는 문자열 비교" 섹션을 참조하십시오.  
  
 문자열 작업의 문화권 구분 여부는 응용 프로그램에서 작업 결과를 사용하는 방식에 따라 결정됩니다.  사용자에게 결과를 표시하는 문자열 작업은 일반적으로 문화권을 구분해야 합니다.  예를 들어 응용 프로그램에서 지역화된 문자열 목록을 정렬하여 목록 상자에 표시하는 경우 응용 프로그램에서 문화권 구분 정렬을 수행해야 합니다.  
  
 내부적으로 사용되는 문자열 작업의 결과는 일반적으로 문화권을 구분하지 않아야 합니다.  일반적으로 응용 프로그램에서 사용자에게 표시되지 않는 파일 이름, 지속성 형식 또는 기호화된 정보로 작업하는 경우 문자열 작업의 결과가 문화권의 영향을 받지 않아야 합니다.  예를 들어, 응용 프로그램이 문자열을 비교하여 인식되는 XML 태그인지 여부를 결정하는 경우 비교 작업은 문화권을 구분하지 않아야 합니다.  또한 문자열 비교 또는 대\/소문자 변경 작업의 결과에 따라 보안 결정을 수행하는 경우 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 값의 영향을 받지 않는 결과를 얻기 위해 문화권을 구분하지 않고 작업을 수행해야 합니다.  
  
 지역화 및 전역화 문제를 처리하는 코드가 포함된 응용 프로그램을 개발하는지 여부에 관계없이 기본적으로 문화권 구분 결과를 검색하는 .NET Framework 메서드를 알고 있어야 합니다.  이 항목의 목표는 응용 프로그램에서 이러한 메서드를 사용하여 문화권을 구분하지 않는 결과를 얻는 올바른 방법을 보여 주기 위한 것입니다.  
  
## 참고 항목  
 [전역화 및 지역화](../../../docs/standard/globalization-localization/index.md)