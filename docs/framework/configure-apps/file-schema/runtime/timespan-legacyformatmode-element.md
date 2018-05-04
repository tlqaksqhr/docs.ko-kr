---
title: '&lt;TimeSpan_LegacyFormatMode&gt; 요소'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0faf2876680ef5ec3fc7373cae9f81eb091f47a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lttimespanlegacyformatmodegt-element"></a>&lt;TimeSpan_LegacyFormatMode&gt; 요소
런타임에서 사용 하는 작업 서식 지정에 레거시 동작을 유지할지 여부를 결정 <xref:System.TimeSpan?displayProperty=nameWithType> 값입니다.  
  
 \<configuration>  
\<runtime>  
< TimeSpan_LegacyFormatMode >  
  
## <a name="syntax"></a>구문  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 레거시 서식 지정 동작을 사용할지 여부 지정 <xref:System.TimeSpan?displayProperty=nameWithType> 값입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임이 레거시 서식 동작을 복원 하지 않습니다.|  
|`true`|런타임이 레거시 서식 동작을 복원합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> 구현 구조는 <xref:System.IFormattable> 인터페이스와 표준 및 사용자 지정 형식 문자열을 사용 하는 작업 서식 지정을 지원 합니다. Throw 구문 분석 방법을 지정 자가 지원 되지 않는 형식 또는 형식 문자열을에서 발생 한 <xref:System.FormatException>합니다.  
  
 이전 버전의.NET Framework에는 <xref:System.TimeSpan> 구조를 구현 하지 않았습니다 <xref:System.IFormattable> 및 형식 문자열을 지원 하지 않았습니다. 그러나 많은 개발자에 게 실수로 것으로 간주 <xref:System.TimeSpan> 형식 문자열 집합을 지원 않았습니다 고에 사용 되는 [합성 서식 지정 작업](../../../../../docs/standard/base-types/composite-formatting.md) 와 같은 메서드로 <xref:System.String.Format%2A?displayProperty=nameWithType>합니다. 일반적으로 해당 형식이 구현 하는 경우 <xref:System.IFormattable> 지원 형식 문자열, 문자열 일반적으로 throw 하는 지원 되지 않는 형식으로 서식 지정 메서드를 호출 하 고는 <xref:System.FormatException>합니다. 그러나 때문에 <xref:System.TimeSpan> 구현 하지 않았습니다. <xref:System.IFormattable>, 런타임에서 형식 문자열을 무시 하 고 대신 호출는 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 메서드. 즉, 즉, 형식 문자열 서식 지정 작업에 영향을 주지 않지만 있으면 발생 하지 않는 한 <xref:System.FormatException>합니다.  
  
 사용할 수 있는 레거시 코드는 합성 형식 지정 메서드와 잘못 된 형식 문자열을 전달 하 고 해당 코드를 다시 컴파일할 수 없는 경우에는 `<TimeSpan_LegacyFormatMode>` 레거시를 복원 하는 요소 <xref:System.TimeSpan> 동작 합니다. 설정 하는 경우는 `enabled` 이 요소의 특성 `true`, 복합 형식 지정 메서드를 호출 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 대신 <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, 및 <xref:System.FormatException> throw 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 <xref:System.TimeSpan> 개체와 사용 하 여 서식을 지정 하려는 시도 <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> 메서드는 지원 되지 않는 표준 형식 문자열을 사용 하 여 합니다.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 예제를 실행 하는 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] 하거나 이전 버전에는 다음과 같은 출력 표시:  
  
```  
12:30:45  
```  
  
 이는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력과 다르게 표시됩니다.  
  
```  
Invalid Format  
```  
  
 그러나 다음 구성 파일을 예제 디렉터리에 추가한 다음 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력은 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]에서 실행할 때 예제가 생성한 출력과 동일합니다.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
