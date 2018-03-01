---
title: "&lt;지우기&gt; NameValueSectionHandler 및 DictionarySectionHandler 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57ee634c987d344d81f1ca099fe55e633bfbf659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<지우기 > NameValueSectionHandler 및 DictionarySectionHandler 요소

섹션에서 이전에 정의 된 모든 설정을 지웁니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<지우기 >**

## <a name="syntax"></a>구문

```xml
<clear />
```

## <a name="attributes"></a>특성

없음

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ------------|
| [**\<sectionName >** 요소](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | 설정을 사용 하는 사용자 지정 구성 섹션에 대 한 정의 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

사용할 수 있습니다는  **\<지우기 >** 모든 설정이 구성 파일 계층 구조에서 더 높은 수준에서 정의 된 응용 프로그램에서 제거할 요소입니다.

## <a name="example"></a>예

이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다.는  **\<지우기 >** 에 이전에 정의 된 섹션을 정리 하는 응용 프로그램 구성 파일의 요소는 컴퓨터 구성 파일입니다.

다음 컴퓨터 구성 파일 코드 선언 섹션  **\<mySection >**:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

다음 응용 프로그램 구성 파일 코드에서 모든 설정이 제거  **\<mySection >**합니다. 응용 프로그램에 선언 된 설정을 검색할 수 없습니다는에  **\<mySection >** 컴퓨터 구성 파일의 섹션입니다.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고 항목

[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
