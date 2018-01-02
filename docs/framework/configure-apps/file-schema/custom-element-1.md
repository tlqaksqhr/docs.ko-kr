---
title: "SingleTagSectionHandler에 대 한 사용자 지정 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ee722c7d5db9d58ab1a91f4b1299912981510af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-element-for-singletagsectionhandler"></a>SingleTagSectionHandler에 대 한 사용자 지정 요소

정의한 사용자 지정 구성 섹션에 설정을 정의 <section> 사용 하 여 요소는 <xref:System.Configuration.SingleTagSectionHandler> 클래스입니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;*\<sectionName >*

## <a name="syntax"></a>구문

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>특성

사용자 정의 특성 및 특성 값입니다.

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

 **\<sectionName >** 정의한 사용자 지정 요소는 [  **\<섹션 >** ](~/docs/framework/configure-apps/file-schema/section-element.md) 태그는 [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) 요소입니다. 구성 시스템 반환는 <xref:System.Collections.IDictionary> 호출 하는 경우 개체 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>합니다.

## <a name="example"></a>예

다음 예에서는 라는 사용자 지정 요소 선언  **\<sampleSection >** 읽은 설정을 포함 하는 <xref:System.Configuration.SingleTagSectionHandler> 클래스:

```xml
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

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고 항목

[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
