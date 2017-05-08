---
title: "Culture를 구분하지 않는 대/소문자 변경 수행 | Microsoft Docs"
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
  - "String.ToLower 메서드"
  - "문화권, 대/소문자 구분"
  - "Char.ToLower 메서드"
  - "대/소문자, 문화권을 구분하지 않는 문자열의 변경"
  - "Char.ToUpper 메서드"
  - "문화권을 구분하지 않는 문자열 작업, 대/소문자 변경"
  - "String.ToUpper 메서드"
  - "문화권 매개 변수"
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Culture를 구분하지 않는 대/소문자 변경 수행
<xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> 및 <xref:System.Char.ToLower%2A?displayProperty=fullName> 메서드는 매개 변수를 받지 않는 오버로드를 제공합니다.  기본적으로 매개 변수가 없는 이러한 오버로드는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 값에 따라 대\/소문자를 변경합니다.  이렇게 하면 문화권에 따라 다를 수 있는 대\/소문자를 구분하는 결과가 생성됩니다.  대\/소문자에서 문화권을 구분하도록 변경할지 또는 문화권을 구분하지 않도록 변경할지를 명확하게 하려면 이러한 메서드의 오버로드를 사용하여 `culture` 매개 변수를 명시적으로 지정해야 합니다.  문화권 구분으로 대\/소문자를 변경할 경우 `culture` 매개 변수에 `CultureInfo.CurrentCulture`를 지정합니다.  문화권을 구분하지 않음으로 대\/소문자를 변경할 경우 `culture` 매개 변수에 `CultureInfo.InvariantCulture`를 지정합니다.  
  
 주로 문자열은 나중에 보다 쉽게 조회할 수 있도록 표준 대\/소문자로 변환됩니다.  이러한 방식으로 문자열을 사용하는 경우 대\/소문자가 변경된 후 문자열이 조회되기 전에 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName> 값이 변경될 수 있으므로 `culture` 매개 변수에 `CultureInfo.InvariantCulture`를 지정해야 합니다.  
  
 대\/소문자 변경 작업에 따라 보안이 결정되는 경우 결과가 `CultureInfo.CurrentCulture` 값의 영향을 받지 않도록 작업에서 문화권을 구분하지 않아야 합니다.  문화권 문자열 작업으로 인해 일관되지 않은 결과가 나타날 수 있는 경우에 대한 예제를 보려면 [문자열 사용에 대한 유용한 정보](../../../docs/standard/base-types/best-practices-strings.md)의 "현재 문화권을 사용한 문자열 비교" 단원을 참조하십시오.  
  
## String.ToUpper 및 String.ToLower 메서드 사용  
 코드의 명확성을 위해 `culture` 매개 변수를 명시적으로 지정할 수 있게 해 주는 `String.ToUpper` 및 `String.ToLower` 메서드의 오버로드를 항상 사용하는 것이 좋습니다.  예를 들어, 다음 코드에서는 식별자 조회를 수행합니다.  `key.ToLower` 작업은 기본적으로 문화권 구분이 수행되지만 코드를 읽을 때는 이 동작이 명확하게 수행되지 않습니다.  
  
### 예제  
  
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
  
 `key.ToLower` 작업에서 문화권을 구분하지 않도록 하려면 대\/소문자를 변경할 때 명시적으로 `CultureInfo.InvariantCulture`를 사용하도록 앞의 예제를 다음과 같이 변경해야 합니다.  
  
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
  
## Char.ToUpper 및 Char.ToLower 메서드 사용  
 `Char.ToUpper` 및 `Char.ToLower`  메서드의 특징은 `String.ToUpper` 및 `String.ToLower` 메서드와 동일하며 터키어\(터키\) 및 아제리어\(라틴 문자, 아제르바이잔\) 문화권만 영향을 받습니다.  이 두 가지 문화권은 단일 문자의 대\/소문자 차이를 보이는 유일한 문화권입니다.  이러한 독특한 대\/소문자 매핑에 대한 자세한 내용은 <xref:System.String> 클래스 항목의 "대\/소문자 구분" 섹션을 참조 하세요.  코드의 명확성을 유지하고 일관된 결과를 얻으려면 이러한 메서드의 오버로드 중 항상 `culture` 매개 변수를 명시적으로 지정할 수 있는 오버로드를 사용하는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.String.ToUpper%2A?displayProperty=fullName>   
 <xref:System.String.ToLower%2A?displayProperty=fullName>   
 <xref:System.Char.ToUpper%2A?displayProperty=fullName>   
 <xref:System.Char.ToLower%2A?displayProperty=fullName>   
 [Culture의 영향을 받지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)