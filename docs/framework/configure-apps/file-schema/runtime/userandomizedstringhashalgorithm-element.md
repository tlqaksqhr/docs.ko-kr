---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; 요소'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a515c3011905c4f5c18ed9d3e8edf489428c04d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746087"
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a>&lt;UseRandomizedStringHashAlgorithm&gt; 요소
공용 언어 런타임에서 문자열에 대 한 해시 코드를 계산할지 여부를 결정 한 응용 프로그램 도메인 단위로.  
  
 \<configuration>  
\<runtime>  
\<UseRandomizedStringHashAlgorithm >  
  
## <a name="syntax"></a>구문  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 문자열에 대 한 해시 코드에서 계산 되 고 있는지 여부를 지정 된 응용 프로그램 도메인 단위로.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`0`|공용 언어 런타임에서 문자열에 대 한 해시 코드를 계산 하지 않습니다는 응용 프로그램 도메인 단위로; 문자열 해시 코드를 계산 하는 단일 알고리즘 사용 됩니다. 이 값이 기본값입니다.|  
|`1`|문자열에 대 한 해시 코드를 계산 하는 공용 언어 런타임에서 응용 프로그램 도메인 단위로. 서로 다른 프로세스와 다른 응용 프로그램 도메인에 동일한 문자열 다른 해시 코드를 갖습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로는 <xref:System.StringComparer> 클래스 및 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드에서 응용 프로그램 도메인 간에 일관 된 해시 코드를 생성 하는 단일 해시 알고리즘을 사용 합니다. 이 설정에 해당 하는 `enabled` 특성에는 `<UseRandomizedStringHashAlgorithm>` 요소를 `0`합니다. 이에서 사용 되는 해시 알고리즘의 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.  
  
 <xref:System.StringComparer> 클래스 및 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드에 해시 코드를 계산 하는 다른 해싱 알고리즘을 사용할 수도 있습니다는 응용 프로그램 도메인 단위로. 결과적으로, 해당 하는 문자열에 대 한 해시 코드는 응용 프로그램 도메인 간에 달라 집니다. 이 기능은 옵트인 기능이; 것을 활용 하려면 설정 해야 합니다는 `enabled` 특성에는 `<UseRandomizedStringHashAlgorithm>` 요소를 `1`합니다.  
  
 문자열 조회는 해시 테이블에서 일반적으로 o (1) 연산입니다. 그러나 많은 수의 충돌이 발생 하는 경우 조회 될 수 있습니다는 O (n<sup>2</sup>) 작업입니다. 사용할 수는 `<UseRandomizedStringHashAlgorithm>` 다시 해시 코드 계산 되는 키 데이터 입력에 기반 하는 경우에 특히 잠재적 충돌 수를 제한 하는 응용 프로그램 도메인, 임의의 해시 알고리즘을 생성 하는 구성 요소 사용자가 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `DisplayString` 개인 문자열 상수를 포함 하는 클래스 `s`, 해당 값은 "는 문자열입니다." 또한 포함는 `ShowStringHashCode` 문자열 값 및 메서드가 실행 되는 응용 프로그램 도메인의 이름과 함께 해시 코드를 표시 하는 메서드입니다.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 예제 구성 파일을 제공 하지 않고 실행 하면 다음과 유사한 출력이 표시 됩니다. 참고 두 응용 프로그램 도메인에서 문자열에 대 한 해시 코드는 동일 합니다.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 그러나 디렉터리의 예에 다음 구성 파일을 추가 하 고 다음 예제를 실행 하는 경우 동일한 문자열에 대 한 해시 코드 응용 프로그램 도메인 별로 달라 집니다.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 구성 파일에 있는 경우의 예제는 다음과 같은 출력을 표시 합니다.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
