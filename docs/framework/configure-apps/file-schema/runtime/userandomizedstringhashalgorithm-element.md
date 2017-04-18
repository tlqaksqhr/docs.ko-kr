---
title: "&lt;UseRandomizedStringHashAlgorithm&gt; 요소 | Microsoft Docs"
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
  - "<UseRandomizedStringHashAlgorithm> 요소"
  - "UseRandomizedStringHashAlgorithm 요소"
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# &lt;UseRandomizedStringHashAlgorithm&gt; 요소
공용 언어 런타임이 응용 프로그램 도메인당 기준으로 문자열의 해시 코드를 계산하는지 여부를 결정합니다.  
  
## 구문  
  
```  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`0`|공용 언어 런타임에서 응용 프로그램 도메인의 문자열에 대한 해시 코드를 계산 하지 않습니다. 단일 알고리즘은 문자열의 해시 코드를 계산하는 데 사용됩니다.  이 값이 기본값입니다.|  
|`1`|공용 언어 런타임은 응용 프로그램 도메인에 따라 문자열에 대한 해시 코드를 계산합니다.  다른 응용 프로그램 도메인 및 다른 프로세스에서 같은 문자열은 서로 다른 해시 코드를 갖습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 <xref:System.StringComparer> 클래스와 <xref:System.String.GetHashCode%2A?displayProperty=fullName> 메서드는 응용 프로그램 도메인 전반에 걸쳐 일관된 해시 코드를 생성하는 단일 해싱 알고리즘을 기본적으로 사용합니다.  이는 `<UseRandomizedStringHashAlgorithm>` 요소의 `enabled` 특성을 `0`로 설정하는 것과 같습니다.  이는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]에서 사용되는 해시 알고리즘입니다.  
  
 <xref:System.StringComparer> 클래스와 <xref:System.String.GetHashCode%2A?displayProperty=fullName> 메서드는 응용 프로그램 도메인에 따라 해시 코드를 계산하는 다른 해시 알고리즘도 사용할 수 있습니다.  따라서 동일한 문자열에 대한 해시 코드는 응용 프로그램 도메인 간에 다릅니다.  이는 옵트인 기능입니다. 이 기능을 사용하려면 `<UseRandomizedStringHashAlgorithm>` 요소의 `enabled` 특성을 `1`로 설정해야 합니다.  
  
 해시 테이블에서 문자열 조회는 일반적으로 O\(1\) 작업입니다.  그러나 많은 충돌이 발생하는 경우 조회는 O\(n<sup>2</sup>\) 작업이 될 수 있습니다.  `<UseRandomizedStringHashAlgorithm>` 구성 요소를 사용하여 응용 프로그램 도메인당 임의 해싱 알고리즘을 생성할 수 있습니다. 그럴 경우 특히 해시 코드가 계산되는 키가 사용자 데이터 입력을 기준으로 하는 경우 잠재적 충돌 수가 제한됩니다.  
  
## 예제  
 다음 예제에서는 그 값이 "This is a string"인 private 문자열 상수 `s`가 포함된 `DisplayString` 클래스를 정의합니다. 메서드를 실행하는 응용 프로그램 도메인의 이름과 함께 문자열 값 및 해시 코드를 표시하는 `ShowStringHashCode` 메서드도 포함합니다.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 구성 파일을 지정하지 않고 이 예제를 실행할 경우 다음과 유사한 출력이 표시됩니다.  문자열의 해시 코드는 두 응용 프로그램 도메인에서 동일합니다.  
  
```  
  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
  
```  
  
 하지만 샘플 디렉터리에 다음의 구성을 추가하고 샘플을 실행하는 경우 동일 문자열의 해시 코드는 응용 프로그램 도메인에 의해 달라집니다.  
  
```  
  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
  
```  
  
 구성 파일이 있는 경우 예제는 다음과 같은 출력을 표시합니다.  
  
```  
  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
  
```  
  
## 참고 항목  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.String.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>