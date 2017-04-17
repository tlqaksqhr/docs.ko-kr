---
title: "&lt;TimeSpan_LegacyFormatMode&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<TimeSpan_LegacyFormatMode> 요소"
  - "TimeSpan_LegacyFormatMode 요소"
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;TimeSpan_LegacyFormatMode&gt; 요소
런타임에서 <xref:System.TimeSpan?displayProperty=fullName> 값을 사용하여 형식 지정 작업에서 레거시 동작을 유지할지 여부를 결정합니다.  
  
## 구문  
  
```  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임은 <xref:System.TimeSpan?displayProperty=fullName> 값을 사용하여 레거시 서식 동작을 사용할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|런타임은 레거시 서식 동작을 복원하지 않습니다.|  
|`true`|런타임은 레거시 서식 동작을 복원합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터 <xref:System.TimeSpan?displayProperty=fullName> 구조는 <xref:System.IFormattable> 인터페이스를 구현하고 표준 및 사용자 지정 형식 문자열을 사용하여 서식 지정 작업을 지원합니다.  구문 분석 메서드에 지원되지 않는 형식 지정자 또는 형식 문자열이 있는 경우 <xref:System.FormatException>을 throw합니다.  
  
 이전 버전의 .NET Framework에서는 <xref:System.TimeSpan> 구조가 <xref:System.IFormattable>을 구현하지 않았고 형식 문자열을 지원하지 않았습니다.  그러나 많은 개발자가 실수로 <xref:System.TimeSpan>가 형식 문자열 집합을 지원하고 <xref:System.String.Format%2A?displayProperty=fullName> 같은 메서드를 사용하여 [합성 형식 지정 작업](../../../../../docs/standard/base-types/composite-formatting.md)에서 사용한 것으로 간주했습니다.  일반적으로 형식이 <xref:System.IFormattable>을 구현하고 형식 문자열을 지원하는 경우 지원되지 않는 형식 문자열을 사용하여 서식 지정 메서드를 호출하면 대개 <xref:System.FormatException>이 throw됩니다.  그러나 <xref:System.TimeSpan>는 <xref:System.IFormattable>를 구현하지 않았기 때문에 런타임은 형식 문자열을 무시하고 대신 <xref:System.TimeSpan.ToString?displayProperty=fullName> 메서드를 호출했습니다.  이는 형식 문자열이 형식 지정 작업에 영향을 미치지 않지만 <xref:System.FormatException>를 발생시키지 않았음을 의미합니다.  
  
 레거시 코드가 합성 형식 지정 메서드와 잘못된 서식 문자열을 전달하고 코드를 다시 컴파일할 수 없는 경우 `<TimeSpan_LegacyFormatMode>` 요소를 사용하여 레거시 <xref:System.TimeSpan> 동작을 복원할 수 있습니다.  이 요소의 `enabled` 특성이 `true`로 설정되면 합성 형식 지정 메서드는 <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> 대신 <xref:System.TimeSpan.ToString?displayProperty=fullName>를 호출하고 <xref:System.FormatException>은 throw되지 않습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.TimeSpan> 개체를 인스턴스화하고 지원되지 않는 표준 형식 문자열을 사용하여 <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=fullName> 메서드로 서식 지정을 시도합니다.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] 또는 이전 버전에서 예제를 실행하면 다음 출력이 표시됩니다.  
  
```  
12:30:45  
```  
  
 이는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력과 다르게 표시됩니다.  
  
```  
Invalid Format  
```  
  
 그러나 다음 구성 파일을 예제 디렉터리에 추가한 다음 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력은 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]에서 실행할 때 예제가 생성한 출력과 동일합니다.  
  
```  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)