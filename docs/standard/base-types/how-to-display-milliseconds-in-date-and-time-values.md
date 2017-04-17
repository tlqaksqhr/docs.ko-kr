---
title: "방법: 날짜 및 시간 값의 밀리초 표시 | Microsoft Docs"
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
  - "날짜[.NET Framework], 밀리초"
  - "DateTime.ToString 메서드"
  - "날짜 및 시간 데이터 표시"
  - "밀리초[.NET Framework]"
  - "시간[.NET Framework], 밀리초"
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 날짜 및 시간 값의 밀리초 표시
<xref:System.DateTime.ToString?displayProperty=fullName> 등의 기본 날짜 및 시간 서식 지정 메서드에는 시간 값의 시간, 분 및 초는 포함되지만 밀리초 구성 요소는 제외됩니다.  이 항목에서는 서식이 지정된 날짜 및 시간 문자열에 날짜 및 시간의 밀리초 구성 요소를 포함하는 방법에 대해 설명합니다.  
  
### DateTime 값의 밀리초 구성 요소를 표시하려면  
  
1.  날짜의 문자열 표현을 사용하는 경우 정적 <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName> 또는 <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=fullName> 메서드를 사용하여 해당 표현을 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 값으로 변환합니다.  
  
2.  시간의 밀리초 구성 요소에서 문자열 표현을 추출하려면 날짜 및 시간 값의 <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> 또는 <xref:System.DateTimeOffset.ToString%2A> 메서드를 호출하고 `fff` 또는 `FFF` 사용자 지정 형식 패턴을 단독으로 또는 다른 사용자 지정 서식 지정자와 함께 `format` 매개 변수로 전달합니다.  
  
## 예제  
 이 예제에서는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값의 밀리초 구성 요소를 단독으로는 물론 더 긴 날짜 및 시간 문자열에 포함하여 콘솔에 표시합니다.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 `fff` 형식 패턴에는 밀리초 값의 모든 후행 0이 포함됩니다.  그리고 `FFF` 형식 패턴에서는 후행 0이 표시되지 않습니다.  다음 예제에서는 이러한 차이를 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 날짜 및 시간의 밀리초 구성 요소를 포함하는 전체 사용자 지정 서식 지정자를 정의하는 경우, 응용 프로그램의 현재 문화권에 포함되는 시간 요소의 정렬에 해당하지 않는 하드 코드된 형식이 정의되는 문제가 발생합니다.  이러한 문제가 발생하지 않도록 하려면 현재 문화권의 <xref:System.Globalization.DateTimeFormatInfo> 개체에서 정의하는 날짜 및 시간 표시 패턴 중 하나를 검색하여 밀리초를 포함하도록 수정할 수 있습니다.  다음 예제에서는 이러한 방식을 보여 줍니다.  여기서는 <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=fullName> 속성에서 현재 문화권의 전체 날짜 및 시간 패턴을 검색한 다음 해당 초 패턴 뒤에 사용자 지정 패턴인 `.ffff`를 삽입합니다.  이 예제에서는 정규식을 사용하여 단일 메서드 호출에서 이 작업을 수행합니다.  
  
 사용자 지정 서식 지정자를 사용하여 밀리초가 아닌 초의 소수 부분을 표시할 수도 있습니다.  예를 들어 `f` 또는 `F` 사용자 지정 서식 지정자는 1\/10초 단위를 표시하고, `ff` 또는 `FF` 사용자 지정 서식 지정자는 1\/100초 단위를 표시하며, `ffff` 또는 `FFFF` 사용자 지정 서식 지정자는 1\/10,000초 단위를 표시합니다.  밀리초의 소수 부분은 반환되는 문자열에서 반올림되지 않고 잘립니다.  다음 예제에서는 이러한 서식 지정자가 사용됩니다.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  1\/10,000초 또는 1\/100,000초 등 초 단위의 매우 미세한 소수까지 표시할 수 있습니다.  그러나 이러한 값은 의미가 없을 수 있습니다.  날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.  Windows NT 3.5 이상 버전과 [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] 운영 체제의 경우 시계의 정밀도는 약 10\-15밀리초입니다.  
  
## 코드 컴파일  
 csc.exe 또는 vb.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [사용자 지정 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)