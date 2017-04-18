---
title: "사용자 지정 TimeSpan 서식 문자열 | Microsoft Docs"
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
  - "사용자 지정 시간 간격 형식 문자열"
  - "사용자 지정 TimeSpan 형식 문자열"
  - "형식 지정자, 사용자 지정 시간 간격"
  - "형식 문자열"
  - "서식 지정[.NET Framework], 시간"
  - "서식 지정[.NET Framework], 시간 간격"
ms.assetid: a63ebf55-7269-416b-b4f5-286f6c03bf0e
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 사용자 지정 TimeSpan 서식 문자열
<xref:System.TimeSpan> 서식 문자열은 서식 지정 작업의 결과로 생성되는 <xref:System.TimeSpan> 값의 문자열 표현을 정의합니다.  사용자 지정 서식 문자열은 하나 이상의 사용자 지정 <xref:System.TimeSpan> 서식 지정자와 그 수에 상관이 없는 리터럴 문자로 이루어집니다.  [표준 TimeSpan 서식 문자열](../../../docs/standard/base-types/standard-timespan-format-strings.md)이 아닌 문자열은 사용자 지정 <xref:System.TimeSpan> 서식 문자열로 해석됩니다.  
  
> [!IMPORTANT]
>  사용자 지정 <xref:System.TimeSpan> 서식 지정자에는 일과 시, 시와 분, 초와 초의 소수 부분 등을 구분하는 데 사용되는 기호 같은 자리 표시자 구분 기호가 포함되지 않습니다.  대신 이러한 기호는 사용자 지정 서식 문자열에 문자열 리터럴로 포함해야 합니다.  예를 들어 `"dd\.hh\:mm"`에서는 마침표\(.\)를 일과 시 사이의 구분 기호로 정의하고 콜론\(:\)을 시와 분 사이의 구분 기호로 정의합니다.  
>   
>  사용자 지정 <xref:System.TimeSpan> 형식 지정자도 양수 및 음수 시간 간격을 구분할 수 있도록 하는 부호를 포함하지 않습니다.  부호를 포함 하려면 조건부 논리를 사용하여 서식 문자열을 생성해야 합니다.  [기타 문자](#Other) 섹션 예제를 포함 합니다.  
  
 <xref:System.TimeSpan> 값의 문자열 표현은 <xref:System.String.Format%2A?displayProperty=fullName>과 같이 합성 서식 지정을 지원하는 메서드를 통해 생성하거나 <xref:System.TimeSpan.ToString%2A?displayProperty=fullName> 메서드의 오버로드를 호출하여 생성할 수 있습니다.  자세한 내용은 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md) 및 [복합 형식 지정](../../../docs/standard/base-types/composite-formatting.md)를 참조하십시오.  다음 예제에서는 서식 지정 작업에 사용자 지정 서식 문자열을 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customformatexample1.cs#1)]
 [!code-vb[Conceptual.TimeSpan.Custom#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customformatexample1.vb#1)]  
  
 사용자 지정 <xref:System.TimeSpan> 서식 문자열은 <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 및 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드에서 구문 분석 작업을 위한 입력 문자열의 필수 서식을 정의하는 데도 사용됩니다. 구문 분석 과정에서 값의 문자열 표현이 해당 값으로 변환됩니다. 다음 예제에서는 구문 분석 작업에 표준 서식 문자열을 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customparseexample1.cs#2)]
 [!code-vb[Conceptual.TimeSpan.Custom#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customparseexample1.vb#2)]  
  
<a name="table"></a> 다음 표에서는 사용자 지정 날짜 및 시간 서식 지정자에 대해 설명합니다.  
  
|형식 지정자|설명|예제|  
|------------|--------|--------|  
|"d", "%d"|시간 간격의 일 수입니다.<br /><br /> 추가 정보: ["d" 사용자 지정 형식 지정자](#dSpecifier)|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%d` \-\-\> "6"<br /><br /> `d\.hh\:mm` \-\-\> "6.14:32"|  
|"dd"\-"dddddddd"|시간 간격의 일 수입니다. 필요한 경우 앞에 0을 채웁니다.<br /><br /> 추가 정보: ["dd"\-"dddddddd" 사용자 지정 서식 지정자](#ddSpecifier)|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `ddd` \-\-\> "006"<br /><br /> `dd\.hh\:mm` \-\-\> "06.14:32"|  
|"h", "%h"|시간 간격에서 일로 계산되지 않은 시간입니다.  한 자리로 된 시 앞에는 0이 오지 않습니다.<br /><br /> 추가 정보: ["h" 사용자 지정 형식 지정자](#hSpecifier)|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%h` \-\-\> "14"<br /><br /> `hh\:mm` \-\-\> "14:32"|  
|"hh"|시간 간격에서 일로 계산되지 않은 시간입니다.  한 자리로 된 시 앞에는 0이 옵니다.<br /><br /> 추가 정보: ["hh" 사용자 지정 형식 지정자](#hhSpecifier)|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `hh` \-\-\> "14"<br /><br /> `new TimeSpan(6, 8, 32, 17, 685):`<br /><br /> `hh` \-\-\> 08|  
|"m", "%m"|시간 간격에서 시간 또는 일로 계산되지 않은 분입니다.  한 자리로 된 분 앞에는 0이 오지 않습니다.<br /><br /> 추가 정보: ["m" 사용자 지정 형식 지정자](#mSpecifier)|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `%m` \-\-\> "8"<br /><br /> `h\:m` \-\-\> "14:8"|  
|"mm"|시간 간격에서 시간 또는 일로 계산되지 않은 분입니다.  한 자리로 된 분 앞에는 0이 옵니다.<br /><br /> 추가 정보: ["mm" 사용자 지정 형식 지정자](#mmSpecifier)|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `mm` \-\-\> "08"<br /><br /> `new TimeSpan(6, 8, 5, 17, 685):`<br /><br /> `d\.hh\:mm\:ss` \-\-\> 6.08:05:17|  
|"s", "%s"|시간 간격에서 시간, 일 또는 분으로 계산되지 않은 초입니다.  한 자리로 된 초 앞에는 0이 오지 않습니다.<br /><br /> 추가 정보: ["s" 사용자 지정 형식 지정자](#sSpecifier)|`TimeSpan.FromSeconds(12.965)`:<br /><br /> `%s` \-\-\> 12<br /><br /> `s\.fff` \-\-\> 12.965|  
|"ss"|시간 간격에서 시간, 일 또는 분으로 계산되지 않은 초입니다.  한 자리로 된 초 앞에는 0이 옵니다.<br /><br /> 추가 정보: ["ss" 사용자 지정 형식 지정자](#ssSpecifier)|`TimeSpan.FromSeconds(6.965)`:<br /><br /> `ss` \-\-\> 06<br /><br /> `ss\.fff` \-\-\> 06.965|  
|"f", "%f"|시간 간격의 1\/10초입니다.<br /><br /> 추가 정보: ["f" 사용자 지정 형식 지정자](#fSpecifier)|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `f` \-\-\> 8<br /><br /> `ss\.f` \-\-\> 06.8|  
|"ff"|시간 간격의 1\/100초입니다.<br /><br /> 추가 정보: ["ff" 사용자 지정 서식 지정자](#ffSpecifier)|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `ff` \-\-\> 89<br /><br /> `ss\.ff` \-\-\> 06.89|  
|"fff"|시간 간격의 밀리초입니다.<br /><br /> 추가 정보: ["fff" 사용자 지정 형식 지정자](#f3Specifier)|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `fff` \-\-\> 895<br /><br /> `ss\.fff` \-\-\> 06.895|  
|"ffff"|시간 간격의 1\/10000초입니다.<br /><br /> 추가 정보: ["ffff" 사용자 지정 형식 지정자](#f4Specifier)|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffff` \-\-\> 8954<br /><br /> `ss\.ffff` \-\-\> 06.8954|  
|"fffff"|시간 간격의 1\/100000초입니다.<br /><br /> 추가 정보: ["fffff" 사용자 지정 형식 지정자](#f5Specifier)|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffff` \-\-\> 89543<br /><br /> `ss\.fffff` \-\-\> 06.89543|  
|"ffffff"|시간 간격의 1\/1000000초입니다.<br /><br /> 추가 정보: ["ffffff" 사용자 지정 형식 지정자](#f6Specifier)|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffffff` \-\-\> 895432<br /><br /> `ss\.ffffff` \-\-\> 06.895432|  
|"fffffff"|시간 간격의 1\/10000000초\(또는 틱의 소수 부분\)입니다.<br /><br /> 추가 정보: ["fffffff" 사용자 지정 형식 지정자](#f7Specifier)|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffffff` \-\-\> 8954321<br /><br /> `ss\.fffffff` \-\-\> 06.8954321|  
|"F", "%F"|시간 간격의 1\/10초입니다.  이 자릿수가 0이면 아무 것도 표시되지 않습니다.<br /><br /> 추가 정보: ["F" 사용자 지정 형식 지정자](#F_Specifier)|`TimeSpan.Parse("00:00:06.32")`:<br /><br /> `%F`: 3<br /><br /> `TimeSpan.Parse("0:0:3.091")`:<br /><br /> `ss\.F`: 03.|  
|"FF"|시간 간격의 1\/100초입니다.  소수 부분의 뒤에 0이 오거나 두 숫자가 0이면 해당 0은 포함되지 않습니다.<br /><br /> 추가 정보: ["FF" 사용자 지정 형식 지정자](#FF_Specifier)|`TimeSpan.Parse("00:00:06.329")`:<br /><br /> `FF`: 32<br /><br /> `TimeSpan.Parse("0:0:3.101")`:<br /><br /> `ss\.FF`: 03.1|  
|"FFF"|시간 간격의 밀리초입니다.  소수 부분의 뒤에 오는 0은 포함되지 않습니다.<br /><br /> 추가 정보:|`TimeSpan.Parse("00:00:06.3291")`:<br /><br /> `FFF`: 329<br /><br /> `TimeSpan.Parse("0:0:3.1009")`:<br /><br /> `ss\.FFF`: 03.1|  
|"FFFF"|시간 간격의 1\/10000초입니다.  소수 부분의 뒤에 오는 0은 포함되지 않습니다.<br /><br /> 추가 정보: ["FFFF" 사용자 지정 형식 지정자](#F4_Specifier)|`TimeSpan.Parse("00:00:06.32917")`:<br /><br /> `FFFFF`: 3291<br /><br /> `TimeSpan.Parse("0:0:3.10009")`:<br /><br /> `ss\.FFFF`: 03.1|  
|"FFFFF"|시간 간격의 1\/100000초입니다.  소수 부분의 뒤에 오는 0은 포함되지 않습니다.<br /><br /> 추가 정보: ["FFFFF" 사용자 지정 형식 지정자](#F5_Specifier)|`TimeSpan.Parse("00:00:06.329179")`:<br /><br /> `FFFFF`: 32917<br /><br /> `TimeSpan.Parse("0:0:3.100009")`:<br /><br /> `ss\.FFFFF`: 03.1|  
|"FFFFFF"|시간 간격의 1\/1000000초입니다.  소수 부분의 뒤에 오는 0은 표시되지 않습니다.<br /><br /> 추가 정보: ["FFFFFF" 사용자 지정 형식 지정자](#F6_Specifier)|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 329179<br /><br /> `TimeSpan.Parse("0:0:3.1000009")`:<br /><br /> `ss\.FFFFFF`: 03.1|  
|"FFFFFFF"|시간 간격의 1\/10000000초입니다.  소수 부분의 뒤에 0이 오거나 일곱 숫자가 0이면 해당 0은 표시되지 않습니다.<br /><br /> 추가 정보: ["FFFFFFF" 사용자 지정 형식 지정자](#F7_Specifier)|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 3291791<br /><br /> `TimeSpan.Parse("0:0:3.1900000")`:<br /><br /> `ss\.FFFFFF`: 03.19|  
|*'string*'|리터럴 문자열 구분 기호입니다.<br /><br /> 추가 정보: [기타 문자](#Other)|`new TimeSpan(14, 32, 17):`<br /><br /> `hh':'mm':'ss` \-\-\> "14:32:17"|  
|\\|이스케이프 문자입니다.<br /><br /> 추가 정보: [기타 문자](#Other)|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` \-\-\> "14:32:17"|  
|기타 문자|이스케이프되지 않은 다른 모든 문자는 사용자 지정 서식 지정자로 해석됩니다.<br /><br /> 추가 정보: [기타 문자](#Other)|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` \-\-\> "14:32:17"|  
  
<a name="dSpecifier"></a>   
## "d" 사용자 지정 형식 지정자  
 "d" 사용자 지정 서식 지정자는 시간 간격의 일 수를 나타내는 <xref:System.TimeSpan.Days%2A?displayProperty=fullName> 속성의 값을 출력합니다.  이 서식 지정자는 값의 자릿수가 두 자리 이상이더라도 <xref:System.TimeSpan> 값의 전체 일 수를 출력합니다.  <xref:System.TimeSpan.Days%2A?displayProperty=fullName> 속성의 값이 0이면 이 지정자는 "0"을 출력합니다.  
  
 "d" 사용자 지정 서식 지정자만 단독으로 사용하는 경우 이 서식 지정자를 표준 서식 문자열로 잘못 해석하는 일이 없도록 "%d"를 지정해야 합니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#3)]
 [!code-vb[Conceptual.TimeSpan.Custom#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#3)]  
  
 다음 예제에서는 "d" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#4)]
 [!code-vb[Conceptual.TimeSpan.Custom#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#4)]  
  
 [표로 이동](#table)  
  
<a name="ddSpecifier"></a>   
## "dd"\-"dddddddd" 사용자 지정 서식 지정자  
 "dd", "ddd", "dddd", "ddddd", "dddddd", "ddddddd" 및 "dddddddd" 사용자 지정 서식 지정자는 시간 간격의 일 수를 나타내는 <xref:System.TimeSpan.Days%2A?displayProperty=fullName> 속성의 값을 출력합니다.  
  
 출력 문자열에는 서식 지정자에 사용한 "d" 문자의 개수에 해당하는 최소 자릿수가 포함되며 필요한 경우 앞에 0이 채워집니다.  일 수의 자릿수가 서식 지정자의 "d" 문자 수보다 많으면 전체 일 수가 결과 문자열에 출력됩니다.  
  
 다음 예제에서는 이러한 서식 지정자를 사용하여 <xref:System.TimeSpan> 값 두 개의 문자열 표현을 표시합니다.  첫째 시간 간격의 일 수 구성 요소 값은 0이고, 둘째 시간 간격의 일 수 구성 요소 값은 365입니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#5)]
 [!code-vb[Conceptual.TimeSpan.Custom#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#5)]  
  
 [표로 이동](#table)  
  
<a name="hSpecifier"></a>   
## "h" 사용자 지정 형식 지정자  
 "h" 사용자 지정 서식 지정자는 시간 간격에서 일 수 구성 요소를 계산하는 데 포함되지 않은 시간을 나타내는 <xref:System.TimeSpan.Hours%2A?displayProperty=fullName> 속성의 값을 출력합니다.  이 서식 지정자는 <xref:System.TimeSpan.Hours%2A?displayProperty=fullName> 속성의 값이 0부터 9 사이에 포함되면 한 자리 문자열 값을 반환하고, <xref:System.TimeSpan.Hours%2A?displayProperty=fullName> 속성의 값 범위가 10부터 23까지이면 두 자리 문자열 값을 반환합니다.  
  
 "h" 사용자 지정 서식 지정자만 단독으로 사용하는 경우 이 서식 지정자를 표준 서식 문자열로 잘못 해석하는 일이 없도록 "%h"를 지정해야 합니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
 [!code-vb[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]  
  
 일반적으로 구문 분석 작업에서 숫자 한 개만 포함한 입력 문자열은 일 수로 해석됩니다.  "%h" 사용자 지정 서식 지정자를 사용하면 숫자 문자열을 일 수가 아닌 시간 값으로 해석할 수 있습니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#8)]
 [!code-vb[Conceptual.TimeSpan.Custom#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#8)]  
  
 다음 예제에서는 "h" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#7)]
 [!code-vb[Conceptual.TimeSpan.Custom#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#7)]  
  
 [표로 이동](#table)  
  
<a name="hhSpecifier"></a>   
## "hh" 사용자 지정 형식 지정자  
 "hh" 사용자 지정 서식 지정자는 시간 간격에서 일 수 구성 요소를 계산하는 데 포함되지 않은 시간을 나타내는 <xref:System.TimeSpan.Hours%2A?displayProperty=fullName> 속성의 값을 출력합니다.  값이 0부터 9까지의 범위에 속하면 출력 문자열 앞에 0이 포함됩니다.  
  
 일반적으로 구문 분석 작업에서 숫자 한 개만 포함한 입력 문자열은 일 수로 해석됩니다.  "hh" 사용자 지정 서식 지정자를 사용하면 숫자 문자열을 일 수가 아닌 시간 값으로 해석할 수 있습니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#9)]
 [!code-vb[Conceptual.TimeSpan.Custom#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#9)]  
  
 다음 예제에서는 "hh" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#10)]
 [!code-vb[Conceptual.TimeSpan.Custom#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#10)]  
  
 [표로 이동](#table)  
  
<a name="mSpecifier"></a>   
## "m" 사용자 지정 형식 지정자  
 "m" 사용자 지정 서식 지정자는 시간 간격에서 일 수 구성 요소를 계산하는 데 포함되지 않은 분을 나타내는 <xref:System.TimeSpan.Minutes%2A?displayProperty=fullName> 속성의 값을 출력합니다.  이 서식 지정자는 <xref:System.TimeSpan.Minutes%2A?displayProperty=fullName> 속성의 값이 0부터 9 사이에 포함되면 한 자리 문자열 값을 반환하고, <xref:System.TimeSpan.Minutes%2A?displayProperty=fullName> 속성의 값 범위가 10부터 59까지이면 두 자리 문자열 값을 반환합니다.  
  
 "m" 사용자 지정 서식 지정자만 단독으로 사용하는 경우 이 서식 지정자를 표준 서식 문자열로 잘못 해석하는 일이 없도록 "%m"을 지정해야 합니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
 [!code-vb[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]  
  
 일반적으로 구문 분석 작업에서 숫자 한 개만 포함한 입력 문자열은 일 수로 해석됩니다.  "%m" 사용자 지정 서식 지정자를 사용하면 숫자 문자열을 일 수가 아닌 분 값으로 해석할 수 있습니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#11)]
 [!code-vb[Conceptual.TimeSpan.Custom#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#11)]  
  
 다음 예제에서는 "m" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#12)]
 [!code-vb[Conceptual.TimeSpan.Custom#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#12)]  
  
 [표로 이동](#table)  
  
<a name="mmSpecifier"></a>   
## "mm" 사용자 지정 형식 지정자  
 "mm" 사용자 지정 서식 지정자는 시간 간격에서 시간 또는 일 수 구성 요소를 계산하는 데 포함되지 않은 분을 나타내는 <xref:System.TimeSpan.Minutes%2A?displayProperty=fullName> 속성의 값을 출력합니다.  값이 0부터 9까지의 범위에 속하면 출력 문자열 앞에 0이 포함됩니다.  
  
 일반적으로 구문 분석 작업에서 숫자 한 개만 포함한 입력 문자열은 일 수로 해석됩니다.  "mm" 사용자 지정 서식 지정자를 사용하면 숫자 문자열을 일 수가 아닌 분 값으로 해석할 수 있습니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#13)]
 [!code-vb[Conceptual.TimeSpan.Custom#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#13)]  
  
 다음 예제에서는 "mm" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#14)]
 [!code-vb[Conceptual.TimeSpan.Custom#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#14)]  
  
 [표로 이동](#table)  
  
<a name="sSpecifier"></a>   
## "s" 사용자 지정 형식 지정자  
 "s" 사용자 지정 서식 지정자는 시간 간격에서 분, 시간 또는 일 수 구성 요소를 계산하는 데 포함되지 않은 초를 나타내는 <xref:System.TimeSpan.Seconds%2A?displayProperty=fullName> 속성의 값을 출력합니다.  이 서식 지정자는 <xref:System.TimeSpan.Seconds%2A?displayProperty=fullName> 속성의 값이 0부터 9 사이에 포함되면 한 자리 문자열 값을 반환하고, <xref:System.TimeSpan.Seconds%2A?displayProperty=fullName> 속성의 값 범위가 10부터 59까지이면 두 자리 문자열 값을 반환합니다.  
  
 "s" 사용자 지정 서식 지정자만 단독으로 사용하는 경우 이 서식 지정자를 표준 서식 문자열로 잘못 해석하는 일이 없도록 "%s"를 지정해야 합니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#15)]
 [!code-vb[Conceptual.TimeSpan.Custom#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#15)]  
  
 일반적으로 구문 분석 작업에서 숫자 한 개만 포함한 입력 문자열은 일 수로 해석됩니다.  "%s" 사용자 지정 서식 지정자를 사용하면 숫자 문자열을 일 수가 아닌 초 값으로 해석할 수 있습니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#17)]
 [!code-vb[Conceptual.TimeSpan.Custom#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#17)]  
  
 다음 예제에서는 "s" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#16)]
 [!code-vb[Conceptual.TimeSpan.Custom#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#16)]  
  
 [표로 이동](#table)  
  
<a name="ssSpecifier"></a>   
## "ss" 사용자 지정 형식 지정자  
 "ss" 사용자 지정 서식 지정자는 시간 간격에서 분, 시간 또는 일 수 구성 요소를 계산하는 데 포함되지 않은 초를 나타내는 <xref:System.TimeSpan.Seconds%2A?displayProperty=fullName> 속성의 값을 출력합니다.  값이 0부터 9까지의 범위에 속하면 출력 문자열 앞에 0이 포함됩니다.  
  
 일반적으로 구문 분석 작업에서 숫자 한 개만 포함한 입력 문자열은 일 수로 해석됩니다.  "ss" 사용자 지정 서식 지정자를 사용하면 숫자 문자열을 일 수가 아닌 초 값으로 해석할 수 있습니다.  다음 예제에서 이에 대해 설명합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#18)]
 [!code-vb[Conceptual.TimeSpan.Custom#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#18)]  
  
 다음 예제에서는 "ss" 사용자 지정 서식 지정자를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#19)]
 [!code-vb[Conceptual.TimeSpan.Custom#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#19)]  
  
 [표로 이동](#table)  
  
<a name="fSpecifier"></a>   
## "f" 사용자 지정 서식 지정자  
 "f" 사용자 지정 서식 지정자는 시간 간격의 1\/10초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 한 자리 포함되어야 합니다.  
  
 "f" 사용자 지정 서식 지정자만 단독으로 사용하는 경우 이 서식 지정자를 표준 서식 문자열로 잘못 해석하는 일이 없도록 "%f"를 지정해야 합니다.  
  
 다음 예제에서는 "f" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/10초를 표시합니다. "f"를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="ffSpecifier"></a>   
## "ff" 사용자 지정 형식 지정자  
 "ff" 사용자 지정 서식 지정자는 시간 간격의 1\/100초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 두 자리 포함되어야 합니다.  
  
 다음 예제에서는 "ff" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/100초를 표시합니다. "ff"를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="f3Specifier"></a>   
## "fff" 사용자 지정 형식 지정자  
 "f" 문자가 세 개인 "fff" 사용자 지정 서식 지정자는 시간 간격의 밀리초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 세 자리 포함되어야 합니다.  
  
 다음 예제에서는 "fff" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 밀리초를 표시합니다. "fff"를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="f4Specifier"></a>   
## "ffff" 사용자 지정 형식 지정자  
 "f" 문자가 네 개인 "ffff" 사용자 지정 서식 지정자는 시간 간격의 1\/10000초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 네 자리 포함되어야 합니다.  
  
 다음 예제에서는 "ffff" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/10000초를 표시합니다. "ffff"를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="f5Specifier"></a>   
## "fffff" 사용자 지정 형식 지정자  
 "f" 문자가 다섯 개인 "fffff" 사용자 지정 서식 지정자는 시간 간격의 1\/100000초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 다섯 자리 포함되어야 합니다.  
  
 다음 예제에서는 "fffff" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/100000초를 표시합니다. "fffff"를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="f6Specifier"></a>   
## "ffffff" 사용자 지정 형식 지정자  
 "f" 문자가 여섯 개인 "ffffff" 사용자 지정 서식 지정자는 시간 간격의 1\/1000000초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 여섯 자리 포함되어야 합니다.  
  
 다음 예제에서는 "ffffff" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/1000000초를 표시합니다.  이를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="f7Specifier"></a>   
## "fffffff" 사용자 지정 형식 지정자  
 "f" 문자가 일곱 개인 "fffffff" 사용자 지정 서식 지정자는 시간 간격의 1\/10000000초\(또는 틱의 소수 부분\)를 출력합니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에는 소수 자릿수가 정확히 일곱 자리 포함되어야 합니다.  
  
 다음 예제에서는 "fffffff" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 틱 소수 부분을 표시합니다.  이를 처음에는 유일한 서식 지정자로 사용하고, 둘째 예제에서는 사용자 지정 서식 문자열에 "s" 지정자와 함께 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [표로 이동](#table)  
  
<a name="F_Specifier"></a>   
## "F" 사용자 지정 형식 지정자  
 "F" 사용자 지정 서식 지정자는 시간 간격의 1\/10초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  시간 간격의 1\/10초 값이 0이면 해당 값이 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 1\/10초를 생략할 수 있습니다.  
  
 "F" 사용자 지정 서식 지정자만 단독으로 사용하는 경우 이 서식 지정자를 표준 서식 문자열로 잘못 해석하는 일이 없도록 "%F"를 지정해야 합니다.  
  
 다음 예제에서는 "F" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/10초를 표시합니다.  여기서는 구문 분석 작업에도 이 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#21)]
 [!code-vb[Conceptual.TimeSpan.Custom#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#21)]  
  
 [표로 이동](#table)  
  
<a name="FF_Specifier"></a>   
## "FF" 사용자 지정 형식 지정자  
 "FF" 사용자 지정 서식 지정자는 시간 간격의 1\/100초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  소수 부분의 뒤에 오는 0은 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 1\/10초 및 1\/100초를 생략할 수 있습니다.  
  
 다음 예제에서는 "FF" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/100초를 표시합니다.  여기서는 구문 분석 작업에도 이 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#22)]
 [!code-vb[Conceptual.TimeSpan.Custom#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#22)]  
  
 [표로 이동](#table)  
  
<a name="F3_Specifier"></a>   
## "FFF" 사용자 지정 형식 지정자  
 "F" 문자가 세 개인 "FFF" 사용자 지정 서식 지정자는 시간 간격의 밀리초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  소수 부분의 뒤에 오는 0은 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 1\/10초, 1\/100초 및 1\/1000초를 생략할 수 있습니다.  
  
 다음 예제에서는 "FFF" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/1000초를 표시합니다.  여기서는 구문 분석 작업에도 이 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#23)]
 [!code-vb[Conceptual.TimeSpan.Custom#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#23)]  
  
 [표로 이동](#table)  
  
<a name="F4_Specifier"></a>   
## "FFFF" 사용자 지정 형식 지정자  
 "F" 문자가 네 개인 "FFFF" 사용자 지정 서식 지정자는 시간 간격의 1\/10000초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  소수 부분의 뒤에 오는 0은 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 1\/10초, 1\/100초, 1\/1000초 및 1\/10000초를 생략할 수 있습니다.  
  
 다음 예제에서는 "FFFF" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/10000초를 표시합니다.  여기서는 구문 분석 작업에도 "FFFF" 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#24)]
 [!code-vb[Conceptual.TimeSpan.Custom#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#24)]  
  
 [표로 이동](#table)  
  
<a name="F5_Specifier"></a>   
## "FFFFF" 사용자 지정 형식 지정자  
 "F" 문자가 다섯 개인 "FFFFF" 사용자 지정 서식 지정자는 시간 간격의 1\/100000초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  소수 부분의 뒤에 오는 0은 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 1\/10초, 1\/100초, 1\/1000초, 1\/10000초 및 1\/100000초를 생략할 수 있습니다.  
  
 다음 예제에서는 "FFFFF" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/100000초를 표시합니다.  여기서는 구문 분석 작업에도 "FFFFF" 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#25)]
 [!code-vb[Conceptual.TimeSpan.Custom#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#25)]  
  
 [표로 이동](#table)  
  
<a name="F6_Specifier"></a>   
## "FFFFFF" 사용자 지정 형식 지정자  
 "F" 문자가 여섯 개인 "FFFFFF" 사용자 지정 서식 지정자는 시간 간격의 1\/1000000초를 출력합니다.  서식 지정 작업에서 소수 부분의 나머지 자릿수는 모두 잘립니다.  소수 부분의 뒤에 오는 0은 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 1\/10초, 1\/100초, 1\/1000초, 1\/10000초, 1\/100000초 및 1\/1000000초를 생략할 수 있습니다.  
  
 다음 예제에서는 "FFFFFF" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값의 1\/1000000초를 표시합니다.  여기서는 구문 분석 작업에도 이 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#26](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#26)]
 [!code-vb[Conceptual.TimeSpan.Custom#26](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#26)]  
  
 [표로 이동](#table)  
  
<a name="F7_Specifier"></a>   
## "FFFFFFF" 사용자 지정 형식 지정자  
 "F" 문자가 일곱 개인 "FFFFFFF" 사용자 지정 서식 지정자는 시간 간격의 1\/10000000초\(또는 틱의 소수 부분\)를 출력합니다.  소수 부분의 뒤에 오는 0은 결과 문자열에 포함되지 않습니다.  <xref:System.TimeSpan.ParseExact%2A?displayProperty=fullName> 또는 <xref:System.TimeSpan.TryParseExact%2A?displayProperty=fullName> 메서드를 호출하는 구문 분석 작업에서 입력 문자열에 소수 자릿수 일곱 자리를 생략할 수 있습니다.  
  
 다음 예제에서는 "FFFFFFF" 사용자 지정 서식 지정자를 사용하여 <xref:System.TimeSpan> 값에 포함된 초의 소수 부분을 표시합니다.  여기서는 구문 분석 작업에도 이 사용자 지정 서식 지정자를 사용합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#27](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#27)]
 [!code-vb[Conceptual.TimeSpan.Custom#27](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#27)]  
  
 [표로 이동](#table)  
  
<a name="Other"></a>   
## 기타 문자  
 공백 문자를 포함하여 서식 문자열에서 이스케이프되지 않은 다른 모든 문자는 사용자 지정 서식 지정자로 해석됩니다.  대부분의 경우 이스케이프되지 않은 다른 문자가 있으면 <xref:System.FormatException>이 발생합니다.  
  
 서식 문자열에 리터럴 문자를 포함하는 데는 두 가지 방법이 있습니다.  
  
-   리터럴 문자열 구분 기호인 작은따옴표로 리터럴 문자를 묶습니다.  
  
-   리터럴 문자 앞에 백슬래시\("\\"\)를 추가합니다. 이렇게 하면 해당 문자가 이스케이프 문자로 해석됩니다.  즉, C\#에서 서식 문자열은 @으로 묶거나 리터럴 문자 앞에 백슬래시를 추가해야 합니다.  
  
     어떤 경우에서는 조건부 논리를 사용하여 서식 문자열에서 리터럴의 이스케이프 포함할 수도 있습니다.  다음 예제에서는 음수 시간 간격에 대한 부호를 포함하기 위해 조건부 논리를 사용합니다.  
  
     [!code-csharp[Conceptual.TimeSpan.Custom#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/negativevalues1.cs#29)]
     [!code-vb[Conceptual.TimeSpan.Custom#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/negativevalues1.vb#29)]  
  
 .NET Framework에는 시간 간격의 구분 기호를 위한 문법이 정의되어 있지 않습니다.  즉, 일과 시, 시와 분, 분과 초, 초와 초의 소수 부분 사이에 사용되는 모든 구분 기호는 서식 문자열의 문자 리터럴처럼 처리해야 합니다.  
  
 다음 예제에서는 이스케이프 문자와 작은따옴표를 둘 다 사용하여 출력 문자열에 "minutes"라는 단어가 포함되는 사용자 지정 서식 문자열을 정의합니다.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/literal1.cs#28)]
 [!code-vb[Conceptual.TimeSpan.Custom#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/literal1.vb#28)]  
  
 [표로 이동](#table)  
  
## 참고 항목  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)   
 [표준 TimeSpan 서식 문자열](../../../docs/standard/base-types/standard-timespan-format-strings.md)