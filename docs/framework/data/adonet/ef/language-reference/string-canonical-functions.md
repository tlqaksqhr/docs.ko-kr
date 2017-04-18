---
title: "문자열 정식 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
ms.assetid: 5e2cbebd-5df3-47c7-b0e2-49a17ab22bfb
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 문자열 정식 함수
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에는 문자열 정식 함수가 포함되어 있습니다.  
  
## 설명  
 다음 표에서는 문자열 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수를 보여 줍니다.  
  
|함수|설명|  
|--------|--------|  
|`Concat (` `string1`, `string2``)`|`string1`에 `string2`가 추가된 문자열을 반환합니다.<br /><br /> **인수**<br /><br /> `string1`: `string2`가 추가되는 문자열입니다.<br /><br /> `string2`: `string1`에 추가되는 문자열입니다.<br /><br /> **반환 값**<br /><br /> `String` 반환 값 문자열의 길이가 허용되는 최대 길이보다 크면 오류가 발생합니다.<br /><br /> **예제**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Contains (` `string`, `target``)`|`target`이 `string`에 포함되어 있으면 `true`를 반환합니다.<br /><br /> **인수**<br /><br /> `string`: 검색되는 문자열입니다.<br /><br /> `target`: 검색되는 대상 문자열입니다.<br /><br /> **반환 값**<br /><br /> `target`이 `string`에 포함되어 있으면 `true`이고, 그렇지 않으면 `false`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns true.`<br /><br /> `Contains('abc', 'bc')`|  
|`EndsWith (` `string`, `target``)`|`target`이 `string`으로 끝나면 `true`를 반환합니다.<br /><br /> **인수**<br /><br /> `string`: 검색되는 문자열입니다.<br /><br /> `target`: `string`의 끝에서 검색되는 대상 문자열입니다.<br /><br /> **반환 값**<br /><br /> `string`이 `target`으로 끝나면 `True`를 반환하고, 그렇지 않으면 `false`를 반환합니다.<br /><br /> **예제**<br /><br /> `-- The following example returns true.`<br /><br /> `EndsWith('abc', 'bc')` **Note:**  [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 데이터 공급자를 사용하는 경우 이 함수는 문자열이 고정 길이 문자열 열에 저장되어 있고 `target`이 상수이면 `false`를 반환합니다.  이 경우 뒤쪽 채움 공백을 포함하여 전체 문자열이 검색됩니다.  `EndsWith(TRIM(string), target)` 예제에 나와 있는 대로 고정 길이 문자열의 데이터를 잘라내면 문제를 해결할 수 있습니다.|  
|`IndexOf(` `target`, `string``)`|`string` 내부의 `target` 위치를 반환하거나, 찾을 수 없는 경우 0을 반환합니다.  `string`의 시작 부분을 나타내려면 1을 반환합니다.  인덱스 번호는 1부터 시작합니다.<br /><br /> **인수**<br /><br /> `target`: 검색되는 대상 문자열입니다.<br /><br /> `string`: 검색되는 문자열입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 4.`<br /><br /> `IndexOf('xyz', 'abcxyz')`|  
|`Left (` `string`, `length``)`|`string` 왼쪽에서 처음 `length`개 문자를 반환합니다.  `string` 길이가 `length`보다 작으면 전체 문자열이 반환됩니다.<br /><br /> **인수**<br /><br /> `string`: `String`입니다.<br /><br /> `length`: `Int16`, `Int32`, `Int64` 또는 `Byte`입니다.  `length`는 0보다 작을 수 없습니다.<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns abc.`<br /><br /> `Left('abcxyz', 3)`|  
|`Length (` `string` `)`|문자열의 \(`Int32`\) 길이\(문자\)를 반환합니다.<br /><br /> **인수**<br /><br /> `string`: `String`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 6.`<br /><br /> `Legth('abcxyz')`|  
|`LTrim(` `string` `)`|선행 공백 없이 `string`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns abc.`<br /><br /> `LTrim('   abc')`|  
|`Replace (` `string1`, `string2`, `string3``)`|모든 `string2` 항목을 `string3`으로 대체하여 `string1`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Reverse (` `string` `)`|문자 순서를 반대로 하여 `string`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns dcba.`<br /><br /> `Reverse('abcd')`|  
|`Right (` `string`, `length``)`|`string`에서 마지막 `length`개 문자를 반환합니다.  `string` 길이가 `length`보다 작으면 전체 문자열이 반환됩니다.<br /><br /> **인수**<br /><br /> `string`: `String`입니다.<br /><br /> `length`: `Int16`, `Int32`, `Int64` 또는 `Byte`입니다.  `length`는 0보다 작을 수 없습니다.<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Right('abcxyz', 3)`|  
|`RTrim(` `string` `)`|후행 공백 없이 `string`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`|  
|`Substring (` `string`, `start`, `length``)`|문자열에서 `start` 위치부터 `length`개 문자 길이의 부분 문자열을 반환합니다.  시작 위치 1은 문자열의 첫 번째 문자를 나타냅니다.  인덱스 번호는 1부터 시작합니다.<br /><br /> **인수**<br /><br /> `string`: `String`입니다.<br /><br /> `start`: `Int16`, `Int32`, `Int64` 및 `Byte`입니다.  `start`는 1보다 작을 수 없습니다.<br /><br /> `length`: `Int16`, `Int32`, `Int64` 및 `Byte`입니다.  `length`는 0보다 작을 수 없습니다.<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Substring('abcxyz', 4, 3)`|  
|`StartsWith (` `string`, `target``)`|`string`이 `target`으로 시작하면 `true`를 반환합니다.<br /><br /> **인수**<br /><br /> `string`: 검색되는 문자열입니다.<br /><br /> `target`: `string`의 시작에서 검색되는 대상 문자열입니다.<br /><br /> **반환 값**<br /><br /> `string`이 `target`으로 시작하면 `True`를 반환하고, 그렇지 않으면 `false`를 반환합니다.<br /><br /> **예제**<br /><br /> `-- The following example returns true.`<br /><br /> `StartsWith('abc', 'ab')`|  
|`ToLower(` `string` `)`|대문자를 소문자로 변환하여 `string`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns abc.`<br /><br /> `ToLower('ABC')`|  
|`ToUpper(` `string` `)`|소문자를 대문자로 변환하여 `string`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns ABC.`<br /><br /> `ToUpper('abc')`|  
|`Trim(` `string` `)`|선행 및 후행 공백 없이 `string`을 반환합니다.<br /><br /> **인수**<br /><br /> `String`<br /><br /> **반환 값**<br /><br /> `String`<br /><br /> **예제**<br /><br /> `-- The following example returns abc.`<br /><br /> `Trim('      abc   ')`|  
  
 이러한 함수는 `null`이 입력되면 `null`을 반환합니다.  
  
 동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다.  자세한 내용은 [Entity Framework 함수용 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)을 참조하세요.  
  
## 참고 항목  
 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)