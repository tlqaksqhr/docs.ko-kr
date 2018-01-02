---
title: "&lt;제거&gt; 요소에 대 한 &lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf2cb49fbeb01ad176a1d24d711cebc97ba14004
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="remove-element-for-configsections"></a>\<제거 > 요소에 대 한 \<configSections >

미리 정의 된 섹션 또는 섹션 그룹을 제거합니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<제거 >**

## <a name="syntax"></a>구문

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **name**  | 필수 특성입니다.<br><br>섹션 또는 제거할 섹션 그룹의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configSections >** 요소](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 구성 섹션 및 네임 스페이스 선언을 포함합니다. |

# <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

사용할 수는  **\<제거 >** 구성 파일 계층 구조에서 더 높은 수준에서 정의 된 응용 프로그램에서 섹션 및 섹션 그룹을 제거할 요소입니다.

## <a name="example"></a>예

사용 하는 방법을 보여 주는 다음 예제는  **\<제거 >** 컴퓨터 구성 파일에 이전에 정의 된 섹션을 제거할 응용 프로그램 구성 파일의 요소입니다.

다음 컴퓨터 구성 파일 코드 선언 섹션  **\<sampleSection >**:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

다음 응용 프로그램 구성 파일 코드 제거는  **\<sampleSection >** 섹션. 제거 하면 응용 프로그램의 설정을 검색할 수 없습니다  **\<sampleSection >**합니다.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고 항목

[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
