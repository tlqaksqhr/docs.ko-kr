---
title: "사용자 지정 날짜 및 시간 서식 문자열"
description: "사용자 지정 날짜 및 시간 서식 문자열"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 45f286f5-92c9-4150-957c-fa6d394bc29b
translationtype: Human Translation
ms.sourcegitcommit: 28625def4199a660fe0ea04ab75f4f65d2e0c9c4
ms.openlocfilehash: 285e4bfd6a53d576ce4538b09a2561065c93e399
ms.lasthandoff: 02/23/2017

---

# <a name="custom-date-and-time-format-strings"></a>사용자 지정 날짜 및 시간 서식 문자열

날짜 및 시간 형식 문자열은 형식 지정 작업에서 생성되는 [DateTime](xref:System.DateTime) 또는 [DateTimeOffset](xref:System.DateTimeOffset) 값의 텍스트 표현을 정의합니다. 또한 문자열을 날짜 및 시간으로 성공적으로 변환하기 위해 구문 분석 작업에 필요한 날짜 및 시간 값의 표현을 정의할 수 있습니다. 사용자 지정 형식 문자열은 하나 이상의 사용자 지정 날짜 및 시간 형식 지정자로 구성됩니다. [표준 날짜 및 시간 형식 문자열](standard-datetime.md)이 아닌 문자열은 사용자 지정 날짜 및 시간 형식 문자열로 해석됩니다. 

사용자 지정 날짜 및 시간 형식 문자열은 [DateTime](xref:System.DateTime) 및 [DateTimeOffset](xref:System.DateTimeOffset) 값 둘 다에서 사용할 수 있습니다.

형식 작업에서 사용자 지정 날짜 및 시간 형식 문자열은 날짜 및 시간 인스턴스의 `ToString` 메서드 또는 복합 형식을 지원하는 메서드에서 사용할 수 있습니다. 다음 예제에서는 두 가지 사용 방법을 모두 보여 줍니다. 

```csharp
DateTime thisDate1 = new DateTime(2011, 6, 10);
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".");

DateTimeOffset thisDate2 = new DateTimeOffset(2011, 6, 10, 15, 24, 16, 
                                              TimeSpan.Zero);
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2); 
// The example displays the following output:
//    Today is June 10, 2011.
//    The current date and time: 06/10/11 15:24:16 +00:00
```

```vb
Dim thisDate1 As Date = #6/10/2011#
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".")

Dim thisDate2 As New DateTimeOffset(2011, 6, 10, 15, 24, 16, TimeSpan.Zero)
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2) 
' The example displays the following output:
'    Today is June 10, 2011.
'    The current date and time: 06/10/11 15:24:16 +00:00
```

구문 분석 작업에서 사용자 지정 날짜 및 시간 형식 문자열은 [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) 및 [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) 메서드에서 사용할 수 있습니다. 이러한 메서드를 사용하려면 구문 분석 작업을 성공하기 위해 입력 문자열이 특정 패턴을 정확하게 따라야 합니다. 다음 예제에서는 [DateTimeOffset.ParseExact(String, String, IFormatProvider)](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) 메서드를 호출하여 일, 월 및 두 자리 연도를 포함해야 하는 날짜를 구문 분석하는 방법을 보여 줍니다.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] dateValues = { "30-12-2011", "12-30-2011", 
                              "30-12-11", "12-30-11" };
      string pattern = "MM-dd-yy";
      DateTime parsedDate;

      foreach (var dateValue in dateValues) {
         if (DateTime.TryParseExact(dateValue, pattern, null, 
                                   DateTimeStyles.None, out parsedDate))
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate);
         else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue);
      }
   }
}
// The example displays the following output:
//    Unable to convert '30-12-2011' to a date and time.
//    Unable to convert '12-30-2011' to a date and time.
//    Unable to convert '30-12-11' to a date and time.
//    Converted '12-30-11' to 12/30/2011.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValues() As String = { "30-12-2011", "12-30-2011", 
                                      "30-12-11", "12-30-11" }
      Dim pattern As String = "MM-dd-yy"
      Dim parsedDate As Date

      For Each dateValue As String In dateValues
         If DateTime.TryParseExact(dateValue, pattern, Nothing, 
                                   DateTimeStyles.None, parsedDate) Then
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate)
         Else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue)
         End If                                                         
      Next
   End Sub
End Module
' The example displays the following output:
'    Unable to convert '30-12-2011' to a date and time.
'    Unable to convert '12-30-2011' to a date and time.
'    Unable to convert '30-12-11' to a date and time.
'    Converted '12-30-11' to 12/30/2011.
```

다음 표에서는 사용자 지정 날짜 및 시간 형식 지정자 및 각 형식 지정자에 따라 생성되는 결과 문자열을 보여 줍니다. 기본적으로 결과 문자열은 en-US 문화권의 형식 규칙을 반영합니다. 특정 형식 지정자가 지역화된 결과 문자열을 생성하는 경우 결과 문자열에 적용되는 문화권의 예도 보여 줍니다. 사용자 지정 날짜 및 시간 형식 문자열을 사용하는 방법에 대한 자세한 내용은 참고 단원을 참조하세요.

형식 지정자 | 설명 | 예제
---------------- | ----------- | --------
"d" | 1부터 31까지의 일(월 기준)입니다. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"dd" | 01부터 31까지의 일(월 기준)입니다. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"ddd" | 요일의 약식 이름입니다. | `2019-06-15T13:45:30 -> Mon (en-US)`; `2019-06-15T13:45:30 -> Пн (ru-RU)`; `2019-06-15T13:45:30 -> lun. (fr-FR)`
"dddd" | 요일의 전체 이름입니다. | `2019-06-15T13:45:30 -> Monday (en-US)`; `2019-06-15T13:45:30 -> понедельник (ru-RU)`; `2019-06-15T13:45:30 -> lundi (fr-FR)`
"f" | 날짜 및 시간 값에서&1;/10초입니다. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.05 -> 0` 
"ff" | 날짜 및 시간 값의&1;/100초입니다. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> 00`
"fff" | 날짜 및 시간 값의&1;/1000초입니다. | `6/15/2019 13:45:30.617 -> 617`; `6/15/2019 13:45:30.0005 -> 000`
"ffff" | 날짜 및 시간 값의&1;/10000초입니다. | `2019-06-15T13:45:30.6175000 -> 6175`; `2019-06-15T13:45:30.0000500 -> 0000`
"fffff" | 날짜 및 시간 값의&1;/100000초입니다. | `2019-06-15T13:45:30.6175400 -> 61754`; `6/15/2019 13:45:30.000005 -> 00000`
"ffffff" | 날짜 및 시간 값의&1;/1000000초입니다. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> 000000`
"fffffff" | 날짜 및 시간 값의&1;/10000000초입니다. | `2019-06-15T13:45:30.6175425 -> 6175425`;`2019-06-15T13:45:30.0001150 -> 0001150`
"F" | 0이 아닌 경우 날짜 및 시간 값의&1;/10초입니다. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.0500000 -> (no output)`
"FF" | 0이 아닌 경우 날짜 및 시간 값의&1;/100초입니다. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> (no output)`
"FFF" | 0이 아닌 경우 날짜 및 시간 값의&1;/1000초입니다. | `2019-06-15T13:45:30.6170000 -> 617`; `2019-06-15T13:45:30.0005000 -> (no output)`
"FFFF" | 0이 아닌 경우 날짜 및 시간 값의&1;/10000초입니다. | `2019-06-15T13:45:30.5275000 -> 5275`; `2019-06-15T13:45:30.0000500 -> (no output)`
"FFFFF" | 0이 아닌 경우 날짜 및 시간 값의&1;/100000초입니다. | `2019-06-15T13:45:30.6175400 -> 61754`; `2019-06-15T13:45:30.0000050 -> (no output)`
"FFFFFF" | 0이 아닌 경우 날짜 및 시간 값의&1;/1000000초입니다. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> (no output)`
"FFFFFFF" | 0이 아닌 경우 날짜 및 시간 값의&1;/10000000초입니다. | `2019-06-15T13:45:30.6175425 -> 6175425`; `2019-06-15T13:45:30.0001150 -> 000115`
"g", "gg" | 서기 또는 연대입니다. | `2019-06-15T13:45:30.6170000 -> A.D.`
"h" | 12시간 형식을 사용하는 1부터 12까지의 시간입니다. | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 1`
"hh" | 12시간 형식을 사용하는 01부터 12까지의 시간입니다. | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 01`
"H" | 24시간 형식을 사용하는 0부터 23까지의 시간입니다. | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 13`
"HH" | 24시간 형식을 사용하는 00부터 23까지의 시간입니다. | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 13`
"K" | 표준 시간대 정보입니다. | [DateTime](xref:System.DateTime) 값 사용: `2019-06-15T13:45:30, Kind Unspecified ->`; `2019-06-15T13:45:30, Kind Utc -> Z`; `2019-06-15T13:45:30, Kind Local -> -07:00 (depends on local computer settings)`; [DateTimeOffset](xref:System.DateTimeOffset) 값 사용: `2019-06-15T01:45:30-07:00 --> -07:00`; `2019-06-15T08:45:30+00:00 --> +00:00`
"m" | 0부터 59까지의 분입니다. | `2019-06-15T01:09:30 -> 9`; `2019-06-15T13:29:30 -> 29`
"mm" | 00부터 59까지의 분입니다. | `2019-06-15T01:09:30 -> 09`; `2019-06-15T01:45:30 -> 45`
"M" | 1부터 12까지의 월입니다. | `2019-06-15T13:45:30 -> 6`
"MM" | 01부터 12까지의 월입니다. | `2019-06-15T13:45:30 -> 06`
"MMM" | 월의 약식 이름입니다. | `2019-06-15T13:45:30 -> Jun (en-US)`; `2019-06-15T13:45:30 -> juin (fr-FR)`; `2019-06-15T13:45:30 -> Jun (zu-ZA)`
"MMMM" | 월의 전체 이름입니다. | `2019-06-15T13:45:30 -> June (en-US)`; `2019-06-15T13:45:30 -> juni (da-DK)`; `2019-06-15T13:45:30 -> uJuni (zu-ZA)`
"s" | 0부터 59까지의 초입니다. | `2019-06-15T13:45:09 -> 9`
"ss" | 00부터 59까지의 초입니다. | `2019-06-15T13:45:09 -> 09`
"t" | AM/PM 지정자의 첫 문자입니다. | `2019-06-15T13:45:30 -> P (en-US)`; `2019-06-15T13:45:30 -> 午 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"tt" | AM/PM 지정자입니다. | `2019-06-15T13:45:30 -> PM (en-US)`; `2019-06-15T13:45:30 -> 午後 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"y" | 0부터 99까지의 연도입니다. | `0001-01-01T00:00:00 -> 1`; `0900-01-01T00:00:00 -> 0`; `1900-01-01T00:00:00 -> 0`; `2019-06-15T13:45:30 -> 9`; `2019-06-15T13:45:30 -> 19`
"yy" | 00부터 99까지의 연도입니다. | `0001-01-01T00:00:00 -> 01`; `0900-01-01T00:00:00 -> 00`; `1900-01-01T00:00:00 -> 00`; `2019-06-15T13:45:30 -> 19`
"yyy" | 최소 세 자리 숫자로 된 연도입니다. | `0001-01-01T00:00:00 -> 001`; `0900-01-01T00:00:00 -> 900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyy" | 네 자리 숫자로 된 연도입니다. | `0001-01-01T00:00:00 -> 0001`; `0900-01-01T00:00:00 -> 0900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyyy" | 다섯 자리 숫자로 된 연도입니다. | `0001-01-01T00:00:00 -> 00001`; `2019-06-15T13:45:30 -> 02019`
"z" | 앞에&0;이 표시되지 않는 UTC에서의 시간 오프셋입니다. | `2019-06-15T13:45:30-07:00 -> -7`
"zz" | 한 자리 값의 경우 앞에&0;이 표시되는 UTC에서의 시간 오프셋입니다. | `2019-06-15T13:45:30-07:00 -> -07`
"zzz" | UTC에서의 시간 및 분 오프셋입니다. | `2019-06-15T13:45:30-07:00 -> -07:00`
":" | 시간 구분 기호입니다. | `2019-06-15T13:45:30 -> : (en-US)`; `2019-06-15T13:45:30 -> . (it-IT)`; `2019-06-15T13:45:30 -> : (ja-JP)`
"/" | 날짜 구분 기호입니다. | `2019-06-15T13:45:30 -> / (en-US)`; `2019-06-15T13:45:30 -> - (ar-DZ)`; `2019-06-15T13:45:30 -> . (tr-TR)`
"string", 'string' | 리터럴 문자열 구분 기호입니다. | `2019-06-15T13:45:30 ("arr:" h:m t) -> arr: 1:45 P`; `2019-06-15T13:45:30 ('arr:' h:m t) -> arr: 1:45 P`
% | 뒤에 오는 문자를 사용자 지정 형식 지정자로 정의합니다. | `2019-06-15T13:45:30 (%h) -> 1`
\ | 이스케이프 문자입니다. | `2019-06-15T13:45:30 (h \h) -> 1 h`
기타 문자 | 문자가 변경되지 않은 상태로 결과 문자열에 복사됩니다. | `2019-06-15T01:45:30 (arr hh:mm t) -> arr 01:45 A`

다음 단원에서는 각 사용자 지정 날짜 및 시간 형식 지정자에 대한 추가 정보를 제공합니다. 다른 설명이 없는 한, 각 지정자는 [DateTime](xref:System.DateTime) 값에 사용하든, [DateTimeOffset](xref:System.DateTimeOffset) 값에 사용하든 관계없이 동일한 문자열을 생성합니다. 

## <a name="the-d-custom-format-specifier"></a>"d" 사용자 지정 형식 지정자

"d" 사용자 지정 형식 지정자는 일(월 기준)을 1부터 31까지의 숫자로 나타냅니다. 한 자리 일의 경우 앞에&0;이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "d" 형식 지정자만 사용되면 "d" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 여러 개의 형식 문자열에 "d" 사용자 지정 형식 지정자를 포함합니다. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15); 

Console.WriteLine(date1.ToString("d, M", 
                  CultureInfo.InvariantCulture)); 
// Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays 29 agosto  
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("d, M", _
                  CultureInfo.InvariantCulture)) 
' Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays 29 agosto 
```

## <a name="the-dd-custom-format-specifier"></a>"dd" 사용자 지정 형식 지정자

"dd" 사용자 지정 형식 문자열은 일(월 기준)을 01부터 31까지의 숫자로 나타냅니다. 한 자리 일의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "dd" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-ddd-custom-format-specifier"></a>"ddd" 사용자 지정 형식 지정자

"ddd" 사용자 지정 형식 지정자는 요일의 약식 이름을 나타냅니다. 지역화된 약식 요일 이름은 현재 또는 지정된 문화권의 [DateTimeFormatInfo.AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) 속성에서 검색됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "ddd" 사용자 지정 형식 지정자를 포함합니다. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-dddd-custom-format-specifier"></a>"dddd" 사용자 지정 형식 지정자

"dddd" 사용자 지정 형식 지정자는 임의 개수의 추가 "d" 지정자와 함께 요일의 전체 이름을 나타냅니다. 지역화된 요일 이름은 현재 또는 지정된 문화권의 [DateTimeFormatInfo.DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) 속성에서 검색됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "dddd" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto                                          
```

## <a name="the-f-custom-format-specifier"></a>"f" 사용자 지정 형식 지정자

"f" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/10초까지 표시합니다.

다른 형식 지정자 없이 "f" 형식 지정자만 사용되면 "f" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

[DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) 또는 [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) 메서드에 제공되는 형식 문자열의 일부로 "f" 형식 지정자를 사용하는 경우 "f" 형식 지정자 수는 문자열을 구문 분석하는 데 필요한 초의 소수 부분에 대한 최대 유효 자릿수를 나타냅니다.

다음 예제에서는 사용자 지정 형식 문자열에 "f" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>"ff" 사용자 지정 형식 지정자

"ff" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&2;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/100초까지 표시합니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "ff" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>"fff" 사용자 지정 형식 지정자

"fff" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&3;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/1000초까지 표시합니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "fff" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>"ffff" 사용자 지정 형식 지정자

"ffff" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&4;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/10000초까지 표시합니다.

1/10000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.

## <a name="the-fffff-custom-format-specifier"></a>"fffff" 사용자 지정 형식 지정자

"fffff" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수 다섯 개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/100000초까지 표시합니다.

1/100000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다. 

## <a name="the-ffffff-custom-format-specifier"></a>"ffffff" 사용자 지정 형식 지정자

"ffffff" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&6;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/1000000초까지 표시합니다.

1/1000000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다. 

## <a name="the-fffffff-custom-format-specifier"></a>"fffffff" 사용자 지정 형식 지정자

"fffffff" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&7;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/10000000초까지 표시합니다.

1/10000000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다. 

## <a name="the-f-custom-format-specifier"></a>"F" 사용자 지정 형식 지정자

"F" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/10초까지 표시합니다. 이 자릿수가&0;이면 아무 것도 표시되지 않습니다. 

다른 형식 지정자 없이 "F" 형식 지정자만 사용되면 "F" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

[DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) 또는 [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) 메서드와 함께 사용된 "F" 형식 지정자 수는 문자열을 구문 분석하는 데 사용할 수 있는 초의 소수 부분에 대한 최대 유효 자릿수를 나타냅니다.

다음 예제에서는 사용자 지정 형식 문자열에 "F" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>"FF" 사용자 지정 형식 지정자

"FF" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&2;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/100초까지 표시합니다. 그러나 뒤에&0;이 오거나 두 숫자가&0;이면 표시되지 않습니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "FF" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>"FFF" 사용자 지정 형식 지정자

"FFF" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&3;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/1000초까지 표시합니다. 그러나 뒤에&0;이 오거나 세 숫자가&0;이면 표시되지 않습니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "FFF" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
````

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>"FFFF" 사용자 지정 형식 지정자

"FFFF" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&4;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/10000초까지 표시합니다. 그러나 뒤에&0;이 오거나 네 숫자가&0;이면 표시되지 않습니다.

1/10000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.

## <a name="the-fffff-custom-format-specifier"></a>"FFFFF" 사용자 지정 형식 지정자

"FFFFF" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&5;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/100000초까지 표시합니다. 그러나 뒤에&0;이 오거나 다섯 숫자가&0;이면 표시되지 않습니다.

1/100000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.

## <a name="the-ffffff-custom-format-specifier"></a>"FFFFFF" 사용자 지정 형식 지정자

"FFFFFF" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&6;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/1000000초까지 표시합니다. 그러나 뒤에&0;이 오거나 여섯 숫자가&0;이면 표시되지 않습니다.

1/1000000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.

## <a name="the-fffffff-custom-format-specifier"></a>"FFFFFFF" 사용자 지정 형식 지정자

"FFFFFFF" 사용자 지정 형식 지정자는 초의 소수 부분에 대한 최대 유효 자릿수&7;개를 나타냅니다. 즉, 날짜 및 시간 값에서&1;/10000000초까지 표시합니다. 그러나 뒤에&0;이 오거나 일곱 숫자가&0;이면 표시되지 않습니다.

1/10000000초까지 표시하는 것이 가능하기는 하지만 이 값은 의미가 없을 수도 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다.

## <a name="the-g-or-gg-custom-format-specifier"></a>"g" 또는 "gg" 사용자 지정 형식 지정자

"g" 또는 "gg" 사용자 지정 형식 지정자는 임의 개수의 추가 "g" 지정자와 함께 A.D. 같은 시대 또는 연대를 나타냅니다. 형식을 지정할 날짜에 연관된 시대 또는 연대 문자열이 없으면 이 지정자는 무시됩니다. 

다른 사용자 지정 형식 지정자 없이 "g" 형식 지정자만 사용되면 "g" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 사용자 지정 형식 문자열에 "g" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(70, 08, 04);

Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.InvariantCulture));
// Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));                         
// Displays 08/04/0070 ap. J.-C.
```

```vb
Dim date1 As Date = #08/04/0070#

Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.InvariantCulture))
' Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))                         
' Displays 08/04/0070 ap. J.-C.
```

## <a name="the-h-custom-format-specifier"></a>"h" 사용자 지정 형식 지정자

"h" 사용자 지정 형식 지정자는 시간을 1부터 12까지의 숫자로 나타냅니다. 즉, 자정 또는 정오 이후의 총 시간을 계산하는 12시간 형식으로 나타냅니다. 자정 이후의 시간과 정오 이후의 같은 시간을 구별할 수 없습니다. 시간은 반올림되지 않으며 한 자리 시간의 경우 앞에&0;이 표시되지 않습니다. 예를 들어, 시간이 오전 또는 오후 5:43일 경우 이 사용자 지정 형식 지정자는 "5"를 표시합니다. 

다른 사용자 지정 형식 지정자 없이 "h" 형식 지정자만 사용하면 표준 날짜 및 시간 형식 지정자로 해석되고 [FormatException](xref:System.FormatException)이 throw됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 사용자 지정 형식 문자열에 "h" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-hh-custom-format-specifier"></a>"hh" 사용자 지정 형식 지정자

"hh" 사용자 지정 형식 지정자는 임의 개수의 추가 "h" 지정자와 함께 시간을 1부터 12까지의 숫자로 나타냅니다. 즉, 자정 또는 정오 이후의 총 시간을 계산하는 12시간 형식으로 나타냅니다. 자정 이후의 시간과 정오 이후의 같은 시간을 구별할 수 없습니다. 시간은 반올림되지 않으며 한 자리 시간의 경우 앞에&0;이 표시됩니다. 예를 들어, 시간이 오전 또는 오후 5:43일 경우 이 형식 지정자는 "05"를 표시합니다.

다음 예제에서는 사용자 지정 형식 문자열에 "hh" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-h-custom-format-specifier"></a>"H" 사용자 지정 형식 지정자

"H" 사용자 지정 형식 지정자는 시간을 0부터 23까지의 숫자로 나타냅니다. 즉, 자정 이후의 시간을 계산하는 24시간(0부터 시작) 형식으로 나타냅니다. 한 자리 시간의 경우 앞에&0;이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "H" 형식 지정자만 사용하면 표준 날짜 및 시간 형식 지정자로 해석되고 [FormatException](xref:System.FormatException)이 throw됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 사용자 지정 형식 문자열에 "H" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("H:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 6:09:01 
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("H:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 6:09:01 
```

## <a name="the-hh-custom-format-specifier"></a>"HH" 사용자 지정 형식 지정자

"HH" 사용자 지정 형식 지정자는 임의 개수의 추가 "H" 지정자와 함께 시간을 00부터 23까지의 숫자로 나타냅니다. 즉, 자정 이후의 시간을 계산하는 24시간(0부터 시작) 형식으로 나타냅니다. 한 자리 시간의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "HH" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("HH:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01                        
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("HH:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01
```

## <a name="the-k-custom-format-specifier"></a>"K" 사용자 지정 형식 지정자

"K" 사용자 지정 형식 지정자는 날짜 및 시간 값의 표준 시간대 정보를 나타냅니다. 이 형식 지정자를 [DateTime](xref:System.DateTime) 값과 함께 사용할 경우 결과 문자열은 [DateTime.Kind](xref:System.DateTime.Kind) 속성 값으로 정의됩니다. 
 
* 현지 표준 시간대([DateTime.Kind](xref:System.DateTime.Kind) 속성 값이 [DateTimeKind.Local](xref:System.DateTimeKind.Local)임)의 경우 이 지정자는 "zzz" 지정자와 같으며 UTC(Coordinated Universal Time)에서의 로컬 오프셋(예: "-07:00")이 포함된 결과 문자열을 생성합니다. 

* UTC 시간([DateTime.Kind](xref:System.DateTime.Kind) 속성 값이 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)임)의 경우 결과 문자열에 UTC 날짜를 나타내는 "Z" 문자가 포함됩니다. 

* 지정되지 않은 표준 시간대 시간([DateTime.Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)인 시간)의 경우 결과는 [String.Empty](xref:System.String#System_String_Empty)와 같습니다. 

[DateTimeOffset](xref:System.DateTimeOffset) 값의 경우 "K" 형식 지정자는 "zz" 형식 지정자와 같으며 UTC에서의 [DateTimeOffset](xref:System.DateTimeOffset) 값 오프셋이 포함된 결과 문자열을 생성합니다. 

다른 사용자 지정 형식 지정자 없이 "K" 형식 지정자만 사용하면 표준 날짜 및 시간 형식 지정자로 해석되고 [FormatException](xref:System.FormatException)이 throw됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 미국 태평양 표준 시간대에 있는 시스템의 다양한 [DateTime](xref:System.DateTime) 및 [DateTimeOffset](xref:System.DateTimeOffset) 값에 "K" 사용자 지정 형식 지정자를 사용하여 생성된 문자열을 표시합니다.

```csharp
Console.WriteLine(DateTime.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTime.UtcNow.ToString("%K"));
// Displays Z      
Console.WriteLine("'{0}'", 
                  DateTime.SpecifyKind(DateTime.Now, 
                       DateTimeKind.Unspecified).ToString("%K"));
// Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"));
// Displays +00:00
Console.WriteLine(new DateTimeOffset(2008, 5, 1, 6, 30, 0, 
                      new TimeSpan(5, 0, 0)).ToString("%K"));
// Displays +05:00  
```

```vb
Console.WriteLine(Date.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(Date.UtcNow.ToString("%K"))
' Displays Z      
Console.WriteLine("'{0}'", _
                  Date.SpecifyKind(Date.Now, _
                                   DateTimeKind.Unspecified). _
                  ToString("%K"))
' Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"))
' Displays +00:00
Console.WriteLine(New DateTimeOffset(2008, 5, 1, 6, 30, 0, _
                                     New TimeSpan(5, 0, 0)). _
                  ToString("%K"))
' Displays +05:00 
```

## <a name="the-m-custom-format-specifier"></a>"m" 사용자 지정 형식 지정자

"m" 사용자 지정 형식 지정자는 분을 0부터 59까지의 숫자로 나타냅니다. 분은 마지막 시간 이후 경과한 총 분 수를 나타냅니다. 한 자리 분의 경우 앞에&0;이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "m" 형식 지정자만 사용되면 "m" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요. 

다음 예제에서는 사용자 지정 형식 문자열에 "m" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-mm-custom-format-specifier"></a>"mm" 사용자 지정 형식 지정자

"mm" 사용자 지정 형식 지정자는 임의 개수의 추가 "m" 지정자와 함께 분을 00부터 59까지의 숫자로 나타냅니다. 분은 마지막 시간 이후 경과한 총 분 수를 나타냅니다. 한 자리 분의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "mm" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-m-custom-format-specifier"></a>"M" 사용자 지정 형식 지정자

"M" 사용자 지정 형식 지정자는 월을 1부터 12까지의 숫자(또는 13월까지 있는 역법의 경우 1부터 13까지의 숫자)로 표현합니다. 한 자리 월의 경우 앞에&0;이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "M" 형식 지정자만 사용되면 "M" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 사용자 지정 형식 문자열에 "M" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 18);
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("nl-NL")));                       
// Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("lv-LV")));                        
// Displays (8) Aug, augusts
```

```vb
Dim date1 As Date = #8/18/2008#
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("nl-NL")))                        
' Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("lv-LV")))                        
' Displays (8) Aug, augusts 
```

## <a name="the-mm-custom-format-specifier"></a>"MM" 사용자 지정 형식 지정자

"MM" 사용자 지정 형식 지정자는 월을 01부터 12까지의 숫자(또는 13월까지 있는 역법의 경우 01부터 13까지의 숫자)로 표현합니다. 한 자리 월의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "MM" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-mmm-custom-format-specifier"></a>"MMM" 사용자 지정 형식 지정자

"MMM" 사용자 지정 형식 지정자는 월의 약식 이름을 나타냅니다. 지역화된 약식 월 이름은 현재 또는 지정된 문화권의 [DateTimeFormatInfo.AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames) 속성에서 검색됩니다.

다음 예제에서는 사용자 지정 형식 문자열에 "MMM" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-mmmm-custom-format-specifier"></a>"MMMM" 사용자 지정 형식 지정자

"MMMM" 사용자 지정 형식 지정자는 월의 전체 이름을 나타냅니다. 지역화된 월 이름은 현재 또는 지정된 문화권의 [DateTimeFormatInfo.MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) 속성에서 검색됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "MMMM" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto 
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto  
```

## <a name="the-s-custom-format-specifier"></a>"s" 사용자 지정 형식 지정자

"s" 사용자 지정 형식 지정자는 초를 0부터 59까지의 숫자로 나타냅니다. 결과는 마지막 분 이후 경과한 총 초 수를 나타냅니다. 한 자리 초의 경우 앞에&0;이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "s" 형식 지정자만 사용되면 "s" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요. 

다음 예제에서는 사용자 지정 형식 문자열에 "s" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-ss-custom-format-specifier"></a>"ss" 사용자 지정 형식 지정자

"ss" 사용자 지정 형식 지정자는 임의 개수의 추가 "s" 지정자와 함께 초를 00부터 59까지의 숫자로 나타냅니다. 결과는 마지막 분 이후 경과한 총 초 수를 나타냅니다. 한 자리 초의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "ss" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-t-custom-format-specifier"></a>"t" 사용자 지정 형식 지정자

"t" 사용자 지정 형식 지정자는 AM/PM 지정자의 첫 문자를 나타냅니다. 적절한 지역화된 지정자는 현재 또는 지정된 문화권의 [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) 또는 [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) 속성에서 검색됩니다. AM 지정자는 0:00:00(자정)부터 11:59:59.999까지의 모든 시간에 사용되고 PM 지정자는 12:00:00(정오)부터 23:59:59.999까지의 모든 시간에 사용됩니다. 

다른 사용자 지정 형식 지정자 없이 "t" 형식 지정자만 사용되면 "t" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 사용자 지정 형식 문자열에 "t" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-tt-custom-format-specifier"></a>"tt" 사용자 지정 형식 지정자

"tt" 사용자 지정 형식 지정자는 임의 개수의 추가 "t" 지정자와 함께 전체 AM/PM 지정자를 나타냅니다. 적절한 지역화된 지정자는 현재 또는 지정된 문화권의 [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) 또는 [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) 속성에서 검색됩니다. AM 지정자는 0:00:00(자정)부터 11:59:59.999까지의 모든 시간에 사용되고 PM 지정자는 12:00:00(정오)부터 23:59:59.999까지의 모든 시간에 사용됩니다.

"tt" 지정자는 AM과 PM을 구분해야 하는 언어에만 사용해야 합니다. 예를 들어, 일본어 AM/PM 지정자의 경우 첫 번째 문자가 아니라 두 번째 문자가 서로 다릅니다.

다음 예제에서는 사용자 지정 형식 문자열에 "tt" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-y-custom-format-specifier"></a>"y" 사용자 지정 형식 지정자

"y" 사용자 지정 형식 지정자는 연도를 한 자리 또는 두 자리 숫자로 나타냅니다. 연도가 두 자리를 넘으면 마지막 두 자리 숫자만 결과에 나타납니다. 2008과 같이 두 자리 연도의 첫 번째 숫자가 0으로 시작하면 앞에 0이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "y" 형식 지정자만 사용되면 "y" 표준 날짜 및 시간 형식 지정자로 해석됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

다음 예제에서는 사용자 지정 형식 문자열에 "y" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yy-custom-format-specifier"></a>"yy" 사용자 지정 형식 지정자

"yy" 사용자 지정 형식 지정자는 연도를 두 자리 숫자로 나타냅니다. 연도가 두 자리를 넘으면 마지막 두 자리 숫자만 결과에 나타납니다. 두 자리 연도의 유효 자릿수가 두 자리 미만인 경우 두 자리가 되도록 앞에&0;이 채워집니다.

구문 분석 작업에서 "yy" 사용자 지정 형식 지정자를 사용하여 구문 분석되는&2;자리 연도는 형식 공급자의 현재 달력에 대한 [Calendar.TwoDigitYearMax](xref:System.Globalization.Calendar.TwoDigitYearMax) 속성을 기준으로 해석됩니다. 다음 예제에서는 en-US 문화권(이 경우 현재 문화권)의 기본 양력을 사용하여 두 자리 년도를 갖는 날짜의 문자열 표현을 구문 분석합니다. 그런 다음 [TwoDigitYearMax](xref:System.Globalization.GregorianCalendar.TwoDigitYearMax) 속성이 수정된 [GregorianCalendar](xref:System.Globalization.GregorianCalendar) 개체를 사용하도록 현재 문화권의 [CultureInfo](xref:System.Globalization.CultureInfo) 개체를 변경합니다.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fmt = "dd-MMM-yy";
      string value = "24-Jan-49";

      Calendar cal = (Calendar) CultureInfo.CurrentCulture.Calendar.Clone();
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
      Console.WriteLine();

      cal.TwoDigitYearMax = 2099;
      CultureInfo culture = (CultureInfo) CultureInfo.CurrentCulture.Clone();
      culture.DateTimeFormat.Calendar = cal;
      Thread.CurrentThread.CurrentCulture = culture;

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
   }
}
// The example displays the following output:
//       Two Digit Year Range: 1930 - 2029
//       1/24/1949
//       
//       Two Digit Year Range: 2000 - 2099
//       1/24/2049
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fmt As String = "dd-MMM-yy"
      Dim value As String = "24-Jan-49"

      Dim cal As Calendar = CType(CultureInfo.CurrentCulture.Calendar.Clone(), Calendar)
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
      Console.WriteLine()

      cal.TwoDigitYearMax = 2099
      Dim culture As CultureInfo = CType(CultureInfo.CurrentCulture.Clone(), CultureInfo)
      culture.DateTimeFormat.Calendar = cal
      Thread.CurrentThread.CurrentCulture = culture

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Two Digit Year Range: 1930 - 2029
'       1/24/1949
'       
'       Two Digit Year Range: 2000 - 2099
'       1/24/2049
```

다음 예제에서는 사용자 지정 형식 문자열에 "yy" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyy-custom-format-specifier"></a>"yyy" 사용자 지정 형식 지정자

"yyy" 사용자 지정 형식 지정자는 연도를 최소 세 자리 숫자로 나타냅니다. 연도의 유효 자릿수가 세 자리보다 많더라도 결과 문자열에 포함됩니다. 연도가 세 자리 미만인 경우 세 자리가 되도록 앞에&0;이 채워집니다.

> [!NOTE]
> 연도를 다섯 자리까지 표시할 수 있는 태국 불교식 달력의 경우 이 형식 지정자는 유효 자릿수를 모두 표시합니다.

다음 예제에서는 사용자 지정 형식 문자열에 "yyy" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010      
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-yyyy-custom-format-specifier"></a>"yyyy" 사용자 지정 형식 지정자

"yyyy" 사용자 지정 형식 지정자는 연도를 최소 네 자리 숫자로 나타냅니다. 연도의 유효 자릿수가 네 자리보다 많더라도 결과 문자열에 포함됩니다. 연도가 네 자리 미만인 경우 네 자리가 되도록 앞에&0;이 채워집니다.

> [!NOTE]
> 연도를 다섯 자리까지 표시할 수 있는 태국 불교식 달력의 경우 이 형식 지정자는 유효 자릿수를 모두 표시합니다.

다음 예제에서는 사용자 지정 형식 문자열에 "yyyy" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyyyy-custom-format-specifier"></a>"yyyyy" 사용자 지정 형식 지정자

"yyyyy" 사용자 지정 형식 지정자는 임의 개수의 추가 "y" 지정자와 함께 연도를 최소 다섯 자리 숫자로 나타냅니다. 연도의 유효 자릿수가 다섯 자리보다 많더라도 결과 문자열에 포함됩니다. 연도가 다섯 자리 미만인 경우 다섯 자리가 되도록 앞에&0;이 채워집니다.

추가 "y" 지정자가 있는 경우 "y" 지정자의 수에 맞도록 앞에&0;이 필요한 만큼 채워집니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "yyyyy" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-z-custom-format-specifier"></a>"z" 사용자 지정 형식 지정자

[DateTime](xref:System.DateTime) 값에 사용할 경우 "z" 사용자 지정 형식 지정자는 시간 단위로 측정된 UTC(Coordinated Universal Time)에서 로컬 운영 체제의 부호 있는 표준 시간대 오프셋을 나타냅니다. 이 형식 지정자는 인스턴스의 [DateTime.Kind](xref:System.DateTime.Kind) 속성 값을 반영하지 않습니다. 따라서 [DateTime](xref:System.DateTime) 값에는 "z" 형식 지정자를 사용하지 않는 것이 좋습니다.

[DateTimeOffset](xref:System.DateTimeOffset) 값에 사용할 경우 이 형식 지정자는 시간 단위로 측정된 UTC에서의 [DateTimeOffset](xref:System.DateTimeOffset) 값 오프셋을 나타냅니다. 

오프셋은 항상 앞에 부호가 표시됩니다. 더하기 기호(+)는 UTC보다 앞선 시간을 나타내고 빼기 기호(-)는 UTC보다 늦은 시간을 나타냅니다. 한 자리 오프셋의 경우 앞에&0;이 표시되지 않습니다. 

다른 사용자 지정 형식 지정자 없이 "z" 형식 지정자만 사용하면 표준 날짜 및 시간 형식 지정자로 해석되고 [FormatException](xref:System.FormatException)이 throw됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요. 

다음 예제에서는 사용자 지정 형식 문자열에 "z" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zz-custom-format-specifier"></a>"zz" 사용자 지정 형식 지정자

[DateTime](xref:System.DateTime) 값에 사용할 경우 "zz" 사용자 지정 형식 지정자는 시간 단위로 측정된 UTC(Coordinated Universal Time)에서 로컬 운영 체제의 부호 있는 표준 시간대 오프셋을 나타냅니다. 이 형식 지정자는 인스턴스의 [DateTime.Kind](xref:System.DateTime.Kind) 속성 값을 반영하지 않습니다. 따라서 [DateTime](xref:System.DateTime) 값에는 "zz" 형식 지정자를 사용하지 않는 것이 좋습니다.

[DateTimeOffset](xref:System.DateTimeOffset) 값에 사용할 경우 이 형식 지정자는 시간 단위로 측정된 UTC에서의 [DateTimeOffset](xref:System.DateTimeOffset) 값 오프셋을 나타냅니다.

오프셋은 항상 앞에 부호가 표시됩니다. 더하기 기호(+)는 UTC보다 앞선 시간을 나타내고 빼기 기호(-)는 UTC보다 늦은 시간을 나타냅니다. 한 자리 오프셋의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "zz" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zzz-custom-format-specifier"></a>"zzz" 사용자 지정 형식 지정자

[DateTime](xref:System.DateTime) 값에 사용할 경우 "zzz" 사용자 지정 형식 지정자는 시간 단위로 측정된 UTC(Coordinated Universal Time)에서 로컬 운영 체제의 부호 있는 표준 시간대 오프셋을 나타냅니다. 이 형식 지정자는 인스턴스의 [DateTime.Kind](xref:System.DateTime.Kind) 속성 값을 반영하지 않습니다. 따라서 [DateTime](xref:System.DateTime) 값에는 "zzz" 형식 지정자를 사용하지 않는 것이 좋습니다.

[DateTimeOffset](xref:System.DateTimeOffset) 값에 사용할 경우 이 형식 지정자는 시간 단위로 측정된 UTC에서의 [DateTimeOffset](xref:System.DateTimeOffset) 값 오프셋을 나타냅니다.

오프셋은 항상 앞에 부호가 표시됩니다. 더하기 기호(+)는 UTC보다 앞선 시간을 나타내고 빼기 기호(-)는 UTC보다 늦은 시간을 나타냅니다. 한 자리 오프셋의 경우 앞에&0;이 표시됩니다. 

다음 예제에서는 사용자 지정 형식 문자열에 "zzz" 사용자 지정 형식 지정자를 포함합니다.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the--custom-format-specifier"></a>":" 사용자 지정 형식 지정자

":" 사용자 지정 형식 지정자는 시, 분, 초를 구분하는 데 사용되는 시간 구분 기호를 나타냅니다. 

다른 사용자 지정 형식 지정자 없이 ":" 형식 지정자만 사용하면 표준 날짜 및 시간 형식 지정자로 해석되고 [FormatException](xref:System.FormatException)이 throw됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

## <a name="the--custom-format-specifier"></a>"/" 사용자 지정 형식 지정자

"/" 사용자 지정 형식 지정자는 년, 월, 일을 구분하는 데 사용되는 날짜 구분 기호를 나타냅니다. 

다른 사용자 지정 형식 지정자 없이 "/" 형식 지정자만 사용하면 표준 날짜 및 시간 형식 지정자로 해석되고 [FormatException](xref:System.FormatException)이 throw됩니다. 단일 서식 지정자를 사용하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [단일 사용자 지정 서식 지정자 사용](#using-single-custom-format-specifiers)을 참조하세요.

## <a name="character-literals"></a>문자 리터럴

사용자 지정 날짜 및 시간 형식 문자열에서 다음 문자는 예약되었으며 항상 형식 지정 문자 또는 ", ', / 및 \,의 경우 특수 문자로 해석됩니다. 

  |   |   |   |      
- | - | - | - | -
F | H | K | M | 일
f | g | h | 분 | s
y | y | z | % | :
/ | " | ' | \ |
  |   |   |   |
  
다른 모든 문자는 항상 문자 리터럴로 해석되며, 형식 지정 작업에서 변경되지 않고 결과 문자열에 포함됩니다. 구문 분석 작업에서는 입력 문자열의 문자와 정확히 일치해야 하며, 비교 시 대/소문자를 구분합니다. 

다음 예제에는 형식 문자열에서 현지 표준 시간대를 나타내는 리터럴 문자 "PST"(태평양 표준시) 및 "PDT"(태평양 일광 절약 시간)가 포함되어 있습니다. 문자열이 결과 문자열에 포함되고, 현지 표준 시간대 문자열을 포함하는 문자열도 성공적으로 구문 분석되는 것을 확인합니다. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String[] formats = { "dd MMM yyyy hh:mm tt PST", 
                           "dd MMM yyyy hh:mm tt PDT" };
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(formats[1]));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm PST";
      DateTime newDate;
      if (DateTime.TryParseExact(value, formats, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim formats() As String = { "dd MMM yyyy hh:mm tt PST", 
                                  "dd MMM yyyy hh:mm tt PDT" }
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(formats(1)))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm PST"
      Dim newDate As Date
      If Date.TryParseExact(value, formats, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM PDT
'       12/25/2016 12:00:00 PM
```

문자가 결과 문자열에 포함되거나 입력 문자열에서 성공적으로 구문 분석될 수 있도록 하기 위해 문자를 예약 문자가 아니라 리터럴 문자로 해석되도록 지정하는 두 가지 방법이 있습니다.

* 각 예약된 문자를 이스케이프합니다. 자세한 내용은 [이스케이프 문자 사용](#using-the-escape-character)을 참조하세요. 
  
  다음 예제에는 형식 문자열에서 현지 표준 시간대를 나타내는 리터럴 문자 "pst"(태평양 표준시)가 포함되어 있습니다. "s"와 "t"는 둘 다 사용자 지정 형식 문자열이므로 두 문자를 문자 리터럴로 해석되도록 이스케이프해야 합니다. 
  
```csharp
using System;
using System.Globalization;

public class Example
{
  public static void Main()
  {
      String format = "dd MMM yyyy hh:mm tt p\\s\\t";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                  DateTimeStyles.None, out newDate)) 
          Console.WriteLine(newDate);
      else
          Console.WriteLine("Unable to parse '{0}'", value);
  }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt p\s\t" 
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```
  
* 전체 리터럴 문자열을 따옴표나 아포스트로피로 묶습니다. 다음 예제는 "pst"가 따옴표로 묶여 구분된 전체 문자열을 문자 리터럴로 해석해야 한다는 점을 제외하고 이전 예제와 같습니다. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String format = "dd MMM yyyy hh:mm tt \"pst\"";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt ""pst"""  
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```

## <a name="notes"></a>노트


### <a name="using-single-custom-format-specifiers"></a>단일 사용자 지정 형식 지정자 사용

사용자 지정 날짜 및 시간 형식 문자열은 둘 이상의 문자로 구성됩니다. 날짜 및 시간 형식 지정 메서드는 단일 문자 문자열을 표준 날짜 및 시간 형식 문자열로 해석합니다. 날짜 및 시간 형식 지정 메서드가 문자를 유효한 형식 지정자로 인식하지 못하면 [FormatException](xref:System.FormatException)이 throw됩니다. 예를 들어, "h" 지정자로만 구성된 형식 문자열은 표준 날짜 및 시간 형식 문자열로 해석됩니다. 그러나 이 경우 "h" 표준 날짜 및 시간 형식 지정자가 없으므로 예외가 throw됩니다. 

사용자 지정 날짜 및 시간 형식 지정자 중 하나를 형식 문자열의 유일한 지정자로 사용하려면(즉, "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" 또는 "/" 사용자 지정 형식 지정자를 단독으로 사용하려면) 지정자 앞이나 뒤에 공백을 포함하거나 단일 사용자 지정 날짜 및 시간 지정자 앞에 백분율("%") 형식 지정자를 포함합니다.

예를 들어 "`%h`"는 현재 날짜 및 시간 값이 나타내는 시간을 표시하는 사용자 지정 날짜 및 시간 형식 문자열로 해석됩니다. 결과 문자열에 시간 외에 공백이 포함되기는 하지만 " h" 또는 "h " 형식 지정자를 사용할 수도 있습니다. 다음 예제에서는 이러한 세 가지 형식 문자열을 보여 줍니다.


```csharp
DateTime dat1 = new DateTime(2009, 6, 15, 13, 45, 0);

Console.WriteLine("'{0:%h}'", dat1);
Console.WriteLine("'{0: h}'", dat1);
Console.WriteLine("'{0:h }'", dat1);
// The example displays the following output:
//       '1'
//       ' 1'
//       '1 '
```

```vb
Dim dat1 As Date = #6/15/2009 1:45PM#

Console.WriteLine("'{0:%h}'", dat1)
Console.WriteLine("'{0: h}'", dat1)
Console.WriteLine("'{0:h }'", dat1)
' The example displays the following output:
'       '1'
'       ' 1'
'       '1 '
```

### <a name="using-the-escape-character"></a>이스케이프 문자 사용

형식 문자열의 "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" 또는 "/" 문자는 리터럴 문자가 아닌 사용자 지정 형식 지정자로 해석됩니다. 문자가 형식 지정자로 해석되지 않도록 하려면 해당 문자 앞에 이스케이프 문자인 백슬래시(\))를 삽입하면 됩니다. 이스케이프 문자는 뒤에 오는 문자가 변경되지 않은 상태로 결과 문자열에 포함되어야 하는 문자 리터럴임을 나타냅니다.

결과 문자열에 백슬래시를 포함하려면 `\\`처럼 두 개의 백슬래시를 연속해서 입력해야 합니다.

> [!NOTE]
> C# 컴파일러 같은 일부 컴파일러에서는 하나의 백슬래시 문자가 이스케이프 문자로 해석될 수도 있습니다. 형식을 지정할 때 문자열이 올바로 해석되도록 하려면 해당 문자열 앞에 축자 문자열 리터럴 문자(@ 문자)를 사용하거나 각 백슬래시 앞에 또 다른 백슬래시 문자를 추가하면 됩니다. 다음 C# 예제에서는 이 두 가지 방법을 모두 보여 줍니다.

다음 예제에서는 이스케이프 문자를 사용하여 형식 지정 작업에서 "h" 및 "m" 문자가 형식 지정자로 해석되지 않도록 합니다. 

```csharp
DateTime date = new DateTime(2009, 06, 15, 13, 45, 30, 90);
string fmt1 = "h \\h m \\m";
string fmt2 = @"h \h m \m";

Console.WriteLine("{0} ({1}) -> {2}", date, fmt1, date.ToString(fmt1));
Console.WriteLine("{0} ({1}) -> {2}", date, fmt2, date.ToString(fmt2));
// The example displays the following output:
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
```

```vb
Dim date1 As Date = #6/15/2009 13:45#
Dim fmt As String = "h \h m \m"

Console.WriteLine("{0} ({1}) -> {2}", date1, fmt, date1.ToString(fmt))
' The example displays the following output:
'       6/15/2009 1:45:00 PM (h \h m \m) -> 1 h 45 m 
```

### <a name="datetimeformatinfo-properties"></a>DateTimeFormatInfo 속성

형식 지정은 현재 스레드 문화권에서 암시적으로 제공되거나 형식 지정을 호출하는 메서드의 [IFormatProvider](xref:System.IFormatProvider) 매개 변수를 통해 명시적으로 제공되는 현재 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체의 속성에 따라 영향을 받습니다. [IFormatProvider](xref:System.IFormatProvider) 매개 변수의 경우 문화권 또는 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체를 나타내는 [CultureInfo](xref:System.Globalization.CultureInfo) 개체를 지정해야 합니다. 

대부분의 사용자 지정 날짜 및 시간 형식 지정자로 생성되는 결과 문자열도 현재 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 개체의 속성에 따라 달라집니다. 따라서 응용 프로그램에서는 해당 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 속성을 변경하여 일부 사용자 지정 날짜 및 시간 형식 지정자에서 생성된 결과를 변경할 수 있습니다. 예를 들어, "ddd" 형식 지정자는 [AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) 문자열 배열에서 찾은 약식 요일 이름을 결과 문자열에 추가합니다. 마찬가지로 "MMMM" 형식 지정자는 [MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) 문자열 배열에서 찾은 전체 월 이름을 결과 문자열에 추가합니다.

## <a name="see-also"></a>참고 항목

[System.DateTime](xref:System.DateTime)

[System.IFormatProvider](xref:System.IFormatProvider)

[형식 서식 지정](formatting-types.md)

[표준 날짜 및 시간 서식 문자열](standard-datetime.md)


