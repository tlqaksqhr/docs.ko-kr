---
title: '&lt;EnableAmPmParseAdjustment&gt; 요소'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752821"
---
# <a name="ltenableampmparseadjustmentgt-element"></a>&lt;EnableAmPmParseAdjustment&gt; 요소
날짜 및 시간 구문 분석 메서드에 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 하는 조정 된 규칙 집합을 사용 하는지 여부를 결정 합니다.  
  
 \<configuration>  
 \<runtime>  
\<EnableAmPmParseAdjustment >  
  
## <a name="syntax"></a>구문  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 날짜 및 시간 구문 분석 메서드에 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 하는 조정 된 규칙 집합을 사용 하는지 여부를 지정 합니다.|  
  
### <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|0|날짜 및 시간 구문 분석 메서드에 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석에 대 한 조정 된 규칙을 사용 하지 마십시오.|  
|1|날짜 및 시간 구문 분석 메서드에 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석에 대 한 조정 된 규칙을 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `<EnableAmPmParseAdjustment>` 요소는 다음 방법 날짜 및 시간과 (예: "4/10 6 AM")는 AM/PM 지정자는 그 다음을 포함 하는 날짜 문자열을 구문 분석 방법을 제어 합니다.  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 다른 패턴이 없습니다 영향을 받습니다.  
  
 `<EnableAmPmParseAdjustment>` 요소 아무런 영향을 주지에는 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, 및 <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> 메서드.  
  
> [!IMPORTANT]
>  .NET Core 및.NET 네이티브에서 조정 된 AM/PM 구문 분석 규칙은 기본적으로 활성화 됩니다.  
  
 구문 분석 조정 규칙을 사용 하지 않는 문자열의 첫 번째 숫자는 12 시간 형식의 시간으로 해석 되 고 AM/PM 지정자를 제외 하 고 문자열의 나머지는 무시 됩니다. 날짜 및 시간 구문 분석 메서드에 의해 반환 된 현재 날짜 및 날짜 문자열에서 추출 된 날의 시간으로 구성 됩니다.  
  
 구문 분석 조정 규칙을 사용 하는 경우 구문 분석 방법 일 및 월 현재 연도에 속하는 것으로 해석 하 고는 시간 12 시간 형식의 시간으로 해석 합니다.  
  
 다음 표에서 차이점을 보여 줍니다.는 <xref:System.DateTime> 경우이 값은 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 메서드는 문자열을 구문 분석 하는 데 사용 됩니다 "" 4/10 6 오전 "와 `<EnableAmPmParseAdjustment>` 요소의 `enabled` 속성이"0"또는"1"로 설정 합니다. 오늘 날짜 2017 년 1 월 5 이며 지정된 된 문화권의 "G" 형식 문자열을 사용 하 여 서식이 지정 하는 경우 날짜를 표시를 가정 합니다.  
  
|문화권 이름|사용 하도록 설정 "0" =|활성화 = "1"|  
|------------------|------------------|------------------|  
|ko-KR|2017 5/1/4시: 00 AM|2017 년 4/10/6시: 00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>참고 항목  
 [\<런타임 > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
