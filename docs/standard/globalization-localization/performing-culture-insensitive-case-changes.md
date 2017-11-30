---
title: "Culture를 구분하지 않는 대/소문자 변경 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a>Culture를 구분하지 않는 대/소문자 변경 수행
<xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, 및 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 메서드 매개 변수를 받지 않는 오버 로드를 제공 합니다. 기본적으로 매개 변수 없이 이러한 오버 로드는 값에 따라 대/소문자 변경 수행는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>합니다. 문화권에서 다를 수 있는 대/소문자 구분 결과 생성 합니다. 명시적으로 지정 해야 하는 이러한 메서드의 오버 로드를 하 게 문화권 구분 또는 문화권을 구분 하지 않는 대/소문자 변경 여부를 명확 사용할지는 `culture` 매개 변수입니다. 문화권별 대/소문자 변경 지정 `CultureInfo.CurrentCulture` 에 대 한는 `culture` 매개 변수입니다. 문화권을 구분 하지 않는 대/소문자 변경 지정 `CultureInfo.InvariantCulture` 에 대 한는 `culture` 매개 변수입니다.  
  
 대개 문자열 나중에 보다 쉽게 조회할 수 있도록 하지만 일반적으로 변환 됩니다. 문자열은 이러한 방식으로 사용 되는 경우 지정 해야 `CultureInfo.InvariantCulture` 에 대 한는 `culture` 매개 변수를 때문에 값을 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 소문자가 변경 되는 시간과 조회 수행 될 때 변경 될 수 있습니다.  
  
 대/소문자 변경 작업에 따라 보안 결정을 수행 문화권을 구분 하지 않는 결과 값에 의해 영향을 받지 않도록 하려면 해야 `CultureInfo.CurrentCulture`합니다. "문자열 비교를 사용 하 여의 현재 문화권" 섹션을 참조는 [문자열 사용에 대 한 유용한](../../../docs/standard/base-types/best-practices-strings.md) 문화권 구분 문자열 작업을 보여 주는 예제는 일관 되지 않은 결과가 발생할 수 있습니다에 대 한 문서입니다.  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>String.ToUpper 및 String.ToLower 메서드를 사용 하 여  
 코드의 명확성에 대 한 것이 좋습니다 오버 로드를 항상 사용는 `String.ToUpper` 및 `String.ToLower` 지정할 수 있도록 하는 메서드는 `culture` 매개 변수가 명시적으로 합니다. 예를 들어 다음 코드에서는 식별자 조회를 수행합니다. `key.ToLower` 작업이이 동작 하지만 기본적으로 문화권 구분 코드를 읽을 명확 하지 않습니다.  
  
### <a name="example"></a>예제  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 원하는 경우는 `key.ToLower` 작업만을 문화권 비구분 앞의 예제를 명시적으로 사용 하려면 다음과 같이 변경 해야는 `CultureInfo.InvariantCulture` 대/소문자를 변경 하는 경우.  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>Char.ToUpper 및 Char.ToLower 메서드를 사용 하 여  
 하지만 `Char.ToUpper` 및 `Char.ToLower` 메서드에 동일한 특성을 사용할는 `String.ToUpper` 및 `String.ToLower` 터키어 (터키) 및 아제르바이잔어 (라틴 문자, 아제르바이잔) 문화권만 영향을 받는 메서드는 합니다. 이들은 단일 문자의 대/소문자 차이와 두 개의 문화권입니다. 이러한 독특한 대/소문자 매핑에 대한 자세한 내용은 <xref:System.String> 클래스 항목의 "대/소문자 구분" 섹션을 참조하십시오. 코드의 명확성에 대 한 고 일관 된 결과 얻으려면 것이 좋습니다 항상 명시적으로 지정할 수 있도록 하는 이러한 메서드의 오버 로드를 사용 하는 `culture` 매개 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [Culture의 영향을 받지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
